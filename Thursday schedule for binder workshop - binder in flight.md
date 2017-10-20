# Thursday schedule for binder workshop / binder in flight

[Master workshop schedule](https://hackmd.io/KwTgxmAMBsBmBMBaA7AE1QDkQFmAQwEZEMBmeLA+SWE4VSEkEZIA?both)

## Suggested schedule

9-9:30am - sticky note activity <- posting questions/ideas
9:30-9:45 - sticky note resolution

We should have at least two hacky sessions, one for
JupyterHub-interested folk and one for people who
are interested in putting together their own binders.

## Hacky sessions

### Session notes

- [Sustainability](https://hackmd.io/GYdgnAxqBMDMC0AOAjANgQFmBsSCmY08oArBMiWLCGnkA===?edit)
- [Best practices](https://hackmd.io/EwQw7AzApiAmYFooE4oGMEBYRwQIzQEZCEAGPTYYZADgDZD60g)
- [ Setting up jupyterhub/binderhub](https://hackmd.io/JwFghsBGDsDGAmBaAzPOiQEYAMAORYAbJksoSLpsPGLJiCEA)

### non-trivial binder repository creation

[Creating a binder on github](https://hackmd.io/KwZgRg7AxgTAjAMwLQAYCmCxICwgBxRJgAm6SEcAnMWFMTAsFJUA)

### Getting JupyterHub up and running

and/or BinderHub

Notes on BinderHub doc walkthrough:
* starting from an empty GCE container service, have to create a project.  Must be done before enabling Container Engine API.

### Customizing JupyterHub deployments

## Pleas for documentation

Things to add:
* when would you use JupHub vs BinderHub?
* quick start documentation guide - direct links
* glossary

[JupyterHub](https://jupyterhub.readthedocs.io/en/latest/) - JupyterHub manages multiple instances of the single-user Jupyter notebook server. JupyterHub can be used to serve notebooks to a class of students, a corporate data science group, or a scientific research group.

[Zero-to-JupyterHub](https://zero-to-jupyterhub.readthedocs.io/) - Zero to JupyterHub with Kubernetes is a tutorial to help install and manage JupyterHub.

[BinderHub](https://binderhub.readthedocs.io/en/latest/) - BinderHub builds "binders" containing data+code from GitHub repos and then serves the binders in a custom computing environment. [beta.mybinder.org](http://beta.mybinder.org) is a public BinderHub.

[repo2docker](https://repo2docker.readthedocs.io/en/latest/) - repo2docker builds, runs, and pushes Docker images from source code repositories.
