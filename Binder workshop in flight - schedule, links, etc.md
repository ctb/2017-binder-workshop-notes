# Binder workshop in flight - schedule, links, etc

[See master schedule](https://hackmd.io/KwTgxmAMBsBmBMBaA7AE1QDkQFmAQwEZEMBmeLA+SWE4VSEkEZIA?both)

## Wed schedule, in brief

10am: Welcome!

* Pamela Reynolds - welcome to the DSI!
* Titus Brown - welcome & goals.
* Tim - tech demos and discussion
* Yuvi and/or Chris - what could be better?

11am: Introductions and icebreaking!

Noon-ish: lunch

Afternoon: ad hoc breakout groups, sticky-noting, etc.

Some possible activities:
* trying it out!
* gathering the documentation, trying it out, updating it
* brainstorming demos
* writing up use cases
* asking the hard questions ("hmm, how could we do..."?)
* economics and geopolitical landscape of binder
* making it all work better at a coding level

5pm: end => Wed market or downtime

6:15pm: pizzas will be ready for consumption at Village Pizza!

(all non-alcoholic stuff is covered by workshop)

Thursday start at 9am!!

## Linkfoo for during the workshop

[Tim Head's binder demo](https://beta.mybinder.org/v2/gh/wildtreetech/epfl-osip-2017/master) - and [github source](https://github.com/wildtreetech/epfl-osip-2017/).

Yuvi's demo: http://data8.org/

## Long lists of ideas:

List from workshop organization:

* plan for a sustainable binder setup?
* support for R?
* how to get more people using binder for their science?
* how to integrate with a journal?
* Get more people hacking on binder
* thebe like libraries that are actively maintained
* Tim collecting knowledge from https://nteract.io/ people
    * no one knows of an active project. However using the react components from nteract this should be simple, some people have tried, but nothing conclusive yet. Hardest part is how to provide a secure backend (tmpnb is tricky security wise, but works)
    * technicalities of bring your own compute (BYOC), 
* custom remote kernels (how to hook up a kernel on a remote machine to my blog, or desktop, or ...)
* "single user notebook servers" that aren't a jupyter notebook server, how to integrate RStudio like things or not exclude them (technically possible (see everware or Yuvi's binder demo), how to spread the word?
* we should make the work by Yuvi more public and find some people who actually use R/RStudio to help us out pulling data into the container (this is getting a lot of love)
* how to make it easier to create these bundles of container + code + while continuing to use the tools I already use (like emacs and my terminal) 
* singularity compatibility -> HPCs
* documentation and tutorials and lessons and integration with education
* how to setup your own jupyterhub/binder like instance at home/on your own laptop
* integration with Open Science Framework/osfclient

Deliverables from the original grant:

* hack on binder and develop APIs and tools to connect binder to other hosting platforms, both commercial (AWS, Azure, etc.) and academic (e.g. XSEDE/TACC);
* connect binder to other versioning sites, including bitbucket and gitlab.
* brainstorm and hack on ways to connect credentials to binder to support private repositories and for-pay compute.
* identify missing links and technologies that are needed to more fully realize the promise of binder and Jupyter notebook;
* identify overlaps and complementarity with existing projects that we can make use of;
* more integrated support for docker hub (and private hub) based images;
* brainstorm around blockers that prevent binder from being used for more data-intensive workflows;
* brainstorm around how to specify required compute resources (disk, memory, CPU) for executing binders;
* develop single-command script to execute binders via docker-machine.

Chris Holdgraf's list:
* To share knowledge of the existing architecture/tech behind Binder
* To disambiguate where the code for Binder lives, as well as the difference between BinderHub tech vs. individual Binder deployments
* To brainstorm current usecases for Binder deployments
* To brainstorm future usecases that would require new development on the core BinderHub tech
* To discuss sustainable funding models for Binder deployment time (e.g. paying google cloud)
* To discuss ways to grow the network of deployed BinderHubs
* To discuss more "far-reaching" ideas for how this could be integrated into academic and publishing workflows .

## Reading material

[Project Jupyter: Computational Narratives as the Engine of Collaborative Data Science](https://blog.jupyter.org/project-jupyter-computational-narratives-as-the-engine-of-collaborative-data-science-2b5fb94c3c58)

[Binder workshop grant proposal](http://ivory.idyll.org/blog/2016-mybinder-workshop-proposal.html)

[Is mybinder 95% of the way to next-gen computational science publishing, or only 90%?](http://ivory.idyll.org/blog/2016-mybinder.html)

[An Introduction to Rocker: Docker Containers for R](https://arxiv.org/abs/1710.03675)

[Setting up your own BinderHub](https://binderhub.readthedocs.io/en/latest/)

## Notes and links from workshop attendees

**please link in your own musings *here*** for posterity!

Titus's outline from opening:
* jupyter notebook blew me away back when, but it was tricky to deploy
* been teaching in the cloud for over 7 years, always a 30-60 minute spinup time at the least
* binder solves these problems (show oslo diagram)
* first really viable solution to just getting on with things
* use cases in teaching, training, publishing, journalism, ??
* lots of universities/MOOCs are doing something similar, but typically ad hoc
* Jupyter team is committed to Doing It Right
* ecosystem is still young
* this workshop is about getting together techies and other thoughtful people to:
    - brainstorm ways to use binder
    - expose thoughtful people to binder to impress the possibilities upon them
    - socialize tech
* expected outputs: none, really. writing stuff down would be good; do that in the "binder in flight" hackmd.
(demo that)
* https://2016-oslo-repeatability.readthedocs.io/en/latest/overview-and-agenda.html

- Plan for future load on mybinder.org (added by Carol)
    - service level and expectation for users
    - handling peak demand and overflow
    - incentives for setting up your own binderhub over mybinder.org
    - long-term: how to encourage a federated network of binder instances
- How to capture technical discussions at this workshop to share with other Binder/Jupyter/JupyterHub team members (Min, M, Kyle, Peter, etc.)

### Olga's notes from the morning

- Nice Demo of Jupyter notebooks with Zurich bike data
    - https://github.com/wildtreetech/epfl-osip-2017
    - Can run with binder: https://beta.mybinder.org/v2/gh/wildtreetech/epfl-osip-2017/master
- Data8 - Foundations of data science course at Berkeley
http://data8.org/
    - Course at UC Berkeley
    - Don’t need to know Python
    - Yuvi Panda - Wikimedia
    - Want to make sure they don’t spend a day installing conda on their computers
    - http://data8.org/fa17/
        - If logged in with berkeley.edu account, can click any of the assignments and it jumps you to your own Jupyter Notebook with your own storage
        - Very useful for workshops
        - Uses JupyterHub
            - Have to spin up the instances in the morning, then spin down in the evening to make sure you don’t get charged a ton
    - Set up a JupyterHub “Zero to JupyterHub”
        - https://zero-to-jupyterhub.readthedocs.io/en/latest/
        - This was used on classes up to 1000 people, or 8-9 people or 2 day workshops
    - Create a Jupyter notebook to docker image: `jupyter-repo2docker`
        - Need to install `repo2docker` first: http://repo2docker.readthedocs.io/en/latest/ 
        - https://github.com/jupyter/repo2docker

### Notes from break-out sessions

Day 1:

- [Got Data?](https://hackmd.io/CwNgDAnAjAHApgVgLQCYDMBDAJk4aBmwSEcAxqUjKRAEYhRTAQpT5A)
- [Integration w/ other services](https://hackmd.io/KYVhDYCMAYCYGYC08DsATAHIgLCgxlgJzB6yIYaHR4ip4CG2sQA)
- [Intro to Binder](https://hackmd.io/AwdgJgpgzAnATAIwLQEZgBYAcT0ENMxIzABmJSu0IucwAxpiDHUA#)
- [provenance/legal/authorship](https://hackmd.io/MwRgnA7AHAxmBGBaATPMAGRAWAJlriAhsjoYjssmDDtVgKbARA==)
- [Use cases](https://hackmd.io/BwFgzA7ArAJmCmBaATARngY0SARq1iwAZhgGyIRgwCGADNQ9cAJw5A==)

Day 2:
- [Sustainability and growing a community](https://hackmd.io/MwEwnAHBYIwGwFoAsBDCJkFMBMwEQCMAzTBAgdhAGNgU5ICYBWIA#)
- [Best Practices](https://hackmd.io/EwQw7AzApiAmYFooE4oGMEBYRwQIzQEZCEAGPTYYZADgDZD60g==)

## Misc timeline, and discussion: 

- dicussion about  DOI publisher on reproducibility, mention of code ocean, globus, and Dataverse. How does binder hook into this. And how to put Data into your Binder. 

- (11:07) Titus try to set the mentality of the workshop: Try to think that the buisness we care about or work with is going to disapear in three years. 

- Chris: Benefit of using Open-Source : Produce vs Technology. People could use a product using the binder tech. Hopefully there won't be a single point of failure and we should encourage people to do whatver they like. 

- 11:08 Yuvi is presenting Data 8 (data8.org), sho use JupyterHub for 100-thousand students. Yuvi demo'ed a number of tech that are related to binder. Yuvin comes from the Wikimedia world, and will show also how wikimedia deals with large amount of data; and what else you can do with binder. 
In data 8 we don't want people to spend a day setign up everything, ence why they developped the following workshop 

    Yuvi demos a JupyterHUb used at berkeley with 2500 users and currently 450 active user. .It is running on Azure this year, but can move to any other cloud. 
    
    Yuvi then demoed a deployment of JupyterhUb on wikimedia which automatically authentify users w/ their wikimedia credential and let them access directly the database (readonly) on the wikimedia server and automatize their edit using python or basj notebooks. 
    
    
## Titus deploying a binder 

* Go to binder repository, https://hub.beta.mybinder.org/user/wildtreetech-epfl-osip-2017-pm9zihak/tree
* Launch one of the notebooks by clicking on it, for example, bikes-over-the-years.ipynb
* Go to the tab "Cell" and run cells to see the program run --- Note: it will take a while for the data to load when everyone is in the room is doing that at the same time.
* While running the notebook, change something in the notebook and rerun the cell.
* These changes will not be preserved in Tim's binder, you need to create your own version of the binder to save changes.

---

* Go to the tab "File", save as ".ipynb" to download binder to laptop
* Go to github for existing binder https://github.com/wildtreetech/epfl-osip-2017/ and fork the repository (you should have a github account for this)
* Go to your forked version of the repository on github, and upload your changed file from your laptop
* Open the uploaded file to make sure your changes showed up.  Note that you cannot run the code, there are no tabs for running the cells.  This is just a static document.
* Copy the url for your github repo and paste it into https://beta.mybinder.org and click "launch"
* This is now a binder that is dynamic and changeable (to you).  You can run your uploaded version of the ipython notebook as a binder at mybinder.org.

- Here's an example organization of Jupyter Notebooks for a scientific project:
    - https://github.com/yeolab/singlecell_pnm#notebook-organization

RElevant images:

![](https://github.com/YeoLab/singlecell_pnm/raw/master/folder_organization/folder_descriptions@2x.png)


![](https://github.com/YeoLab/singlecell_pnm/raw/master/folder_organization/data_flow@2x.png)

- Jessica Hamrick: Reproducible, one-button workflows with jupyter notebook
    - https://github.com/jhamrick/nbflow
    - https://www.youtube.com/watch?v=Fc2W930NJs8
- Dataflow notebook extension
    - https://github.com/dataflownb/dfkernel


# Use-cases for Binder
* ~~Mining bitcoin~~
* Easing collaborative environments for teams.
* Group projects that have both closed and open components
* Jupyter templates to demonstrate best practices in making notebooks
* Connect pre-existing collections of notebooks to online computation (e.g. courses with collections of notebooks already online)
* Dissertations as interactive online publications
* Use-cases that are specific to a discipline. E.g., notebooks that perform specific visualizations
* Hosting workshops with Binder
* Having "template notebooks" 
* Continuous integration to make sure that notebooks don't break over time
* Self assessment and feedback
* Interactive slideshows
* Platform for interactive widgets
* Journalism and data visualizations
* Gateway into programming and data analysis
* Step by step explanation of how an algorithm works.
* Laptop-independent computing when you can't assume a laptop
    * Under-represented groups
    * Younger audiences
* Publications as interactive notebooks
* Discoverability of repositories that use a particular package
* Using Binderable repositories in order to investigate which packages people are using.
* A browser plugin that automatically tries to launch a binder from the current page
* "Bring this data to Binder"
* Button to download the current state of the binder (e.g. all files w/ edits inside them)
* "Data takeout" feature more generally. Maybe a commit to your fork of a github repo.
* "Fix one thing" collection of notebooks as a debugging guide / quiz.
* 