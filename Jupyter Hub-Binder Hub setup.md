# Jupyter Hub/Binder Hub setup

## Jupyter Hub

* Link to slides: https://docs.google.com/presentation/d/1loynWNwsv3lgK5DCe5Ai8GbCyjS2JviaefsygXEhlLU/edit
* Google cloud will be used for this because of their free tier
* console.cloud.google.com - add a credit card to your account.  This is required to set up Jupyter Hub on Google Cloud
* Go to API and services -> library -> search for 'container engine' -> click enable
* If you click on the top right a button that looks like a little terminal called "Activate google cloud shell" - it should give you a shell so you can type commands in (click start cloud shell)
* We are going to try to create a three node cluster for us to set up a Jupyter hub on
* In the shell, type: ``gcloud container clusters create workshop-cluster --zone=us-central1-b --num-nodes=3 --machine-type=n1-standard-2 --disk-size=100``
    * Zone is where it'll be (this one is in central US)
    * disk size is per machine
    * machine type is the size of each node so standard 2 is two cores, each core in a standard has like 3.5-4 gigs of ram, so standard 2 is like 8 gigs of ram.  This is Google specific.  
    * Num-nodes - You can resize this later - size it to 0 when you start and then change it to what you need so you don't need to pay for it when it's not active
    * workshop-cluster is the name of the project
* Jupyter hub is needed to run jupyter stuff.  We're creating a jupyter hub right now with this.  Binder hub requires the same things.
* We're going to create a basic YAML file to have our basic configuration.  To do that, we're going to use helm which is like debian packages. It's used to for installing on cloud packages
* Install helm, type in your terminal: ``curl -L https://bit.ly/install-helm | bash``
* Initialize helm by typing: ``helm init``
* So far: regardless of what cloud provider, we want to run jupyter hub.  You could do it on a bunch of different cloud platforms.  So far, you've created a Kubernetes cluster and now we're going to set up jupyer hub on top of that. When we set up binder hub, we'll be setting it up on top of Kubernetes and it'll be on the same level of jupyter hub, just pretend it's like installing another thing of software
* Add JupyterHub helm repo by typing in the command line: helm repo add jupyterhub https://jupyterhub.github.io/helm-chart
* Then type: ``helm repo update``
* Minimum thing you need to setup a jupyter hub is two secret values.
* If you want to use a terminal editor, you can do that or you can click on the pencil at the top to open a GUI editor
* ``openssl rand -hex 32`` (run this command twice and copy the contents and then put them in a config.yaml file like below)
* nano config.yaml
```
hub:
   cookie: "first secret"
proxy:
    secretToken: "second secret"
```

* Make a hub: ``helm install jupyterhub/jupyterhub --version=v0.4 --name=jhub --namespace=jhub -f config.yaml``
* Let's find our public Hub IP address: `kubectl --namespace=jhub get svc` (the proxy-public external IP is the one you need to use, you can put it in your browser and it should show you a login page, by default it has a dummy login page that doesn't actually care what you put in)
* Yay!  Now we have a public facing jupyter hub!

* If you need to upgrade because you changed your config file: ``helm upgrade jhub jupyterhub/jupyterhub --version=0.4 -f config.yaml``. If that doesn't fix the problem try: ``kubectl --namespace=jhub delete pod --all``

* Change the config file to specify an existing docker image 
```
single user:
    image:
        name: jupyter/datascience-notebook
        tag: 281505737f8a
```

* Then run ``helm upgrade jhub jupyterhub/jupyterhub --version=0.4 -f config.yaml``


## Binder Hub

* Instructions:
  - https://binderhub.readthedocs.io/en/latest/create-cloud-resources.html
  - https://binderhub.readthedocs.io/en/latest/setup-binderhub.html
* First thing, delete the jupyter hub. ``kubectl delete namespace jhub``
* If you want to see what namespaces you have ``kubectl get namespace``
* We are going to install binderhub.  We have to connect our google cloud account 
* Go to IAM and Admin (handles permissions on your account) -> click on service accounts -> create service account -> role is storage - storage admin -> click on furnish a new private key (this json file will be copied into config.yaml file, this should be private) -> create
* Click on API and services -> API Library -> search for google container registry API -> enable
* Generate a few pieces of info for the config file (``openssl rand -hex 32`` twice)
* Create a new folder called binderhub ``mkdir binderhub``
* create a file called secret.yaml: 
```
jupyterhub:
    hub:
      services:
        binder:
          apiToken: "<output of FIRST `openssl rand -hex 32` command>"
    proxy:
      secretToken: "<output of SECOND `openssl rand -hex 32` command>"
registry:
  password: |
    <contents of the JSON file for the container registry from Service Accounts>
hub:
  services:
    binder:
      apiToken: "<output of FIRST `openssl rand -hex 32` command>"
```
* Make sure your secret file is indented correctly
* Make a config.yaml file and fill in your google project id from the json file and the prefix with whatever you want to be appended to file names
```
registry:
  prefix:  gcr.io/<google-project-id>/<prefix>
  enabled: true

rbac:
   enabled: false
jupyterhub:
   hub:
      rbac:
         enabled: false
``` 
         
* copy and paste this to install helm chart: ``helm install jupyterhub/binderhub --version=v0.1.0-789e30a --name=binder --namespace=binder -f secret.yaml -f config.yaml``
* connect binderhub and jupyterhub: ``kubectl --namespace=binder get svc proxy-public``
* follow rest of instructions here: http://binderhub.readthedocs.io/en/latest/setup-binderhub.html
* You can type into your binder: binder-examples/latex and try to run it

Tearing it down!
* ``kubectl delete namespace binder`` - tear down binder
* ``gcloud container clusters list``  - show all the clusters that exist
* ``gcloud container clusters delete workshop-cluster --zone=us-central1-b``
         
