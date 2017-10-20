# Binder Integration w/ Other Services

What services to integrate with, and how

* Dataverse
* OSF
* Cyverse
* Locally-served folders?


How:

* Versions of Repo2Docker for non-GH services? -- Dataverse2Docker, OSF2Docker, etc.
    * Subclasses of [RepoProvider](https://github.com/jupyterhub/binderhub/blob/master/binderhub/repoproviders.py)


Use Cases:

1) Import data from services other than Github
    * This often requires authorization to access private datasets
2) Send changes back upstream after notebooks are modified
3) Cross-platform binder persistence
    * Ability to execute mybinders in arbitrary compute environments?


Auth:

How to inject credentials into Jupyterhub context?

* Environment vars passed to containers?
* Currently, only access public Github repos
* Typical security concerns related to passing creds around in a multi-tenant environment
* Security should happen at a VM level, higher than Binder
