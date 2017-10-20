# Got Data?

Problem: How get data into Binder dockers?

* curl/wget? No.
* Torrents / IPFS
* Fuse FS (fuse mount in other container, then docker volume)
* Docker mount
* What about data you *can't* move, e.g. sensitive information?
* [postBuild](https://github.com/jupyter/repo2docker/#postbuild) of `repo2docker` to bake data into the image


Use Cases:

1. Sequencing data from single cells. Primary data is 100s of megs per cell. Millions of cell, so gigs/terabytes. Data you finally get into notebook is a few gigs. Where is this stored? It's on S3 that you can read in. Where is compute happening? Local laptop, but with multiple people - they need to get access to S3 links. Unclear how to link code, config versions to specific data.
2. Repository system (using dataverse). All data is mounted on a local Unix file system. API that you can access data through. IRODS has API that lets you get large files in there. HTTP API similar to S3.
3. OSF - Designed to give scientists to manage workflow + store their data. Connects multiple other services (Dataverse, S3, Dropbox, etc) allowing researches to collaborate.
4. Data on order of hundreds of gigs. Want to give access to students in a class, but hard to without giving them full cases.
5. Datasets with 3-4 100GB sets of sensitive data, how to connect the parts that require massive amounts of storage/RAM to that parts that don't. Ways to make this shareable in a narrative way that doesn't violate HIPAA compliancy. Stricter permissions for JHub?
6. Main processing pipeline happens outside of Binder / notebook, how do I make it easier to load that into notebooks / binder?
7. Cyverse - primary datastore is iRODS, users access data from wherever, own object stores locally / GDrive / elsewhere. Best ways of normalizing data access and authorization
8. Accessing data that sortof lives randomly on the web - such as CKAN based data about bicycling data. How do we make sure this ends up at appropriate spaces?
    - "a glorified wget": http://www.xrootd.org/
9. Provenance related to interactions between datasets / notebooks and users interacting with them

Workflow case

1. Simulation of star formation of galaxies. Dataset is 5-6TB. Would love to do is create ipython widgets that perform simple visualization of data. When this paper was published there was a temp notebook that had direct access to data via a docker mount, ideally on the archive of the publication - go see to binder. It'll launch binder - there's data locally, compute locally, would be great to have a binder there.
2. Globus endpoint - they're fetching data when user demands. Using a FUSE filesystem, starts when user wants to use the filesystem.


Concrete steps

1. I have a read only large dataset I want to provide access to it for untrusted users who can do whatever they want but in a safe way.
2. Have some sort of specification that specifies where data is coming from and where it should be mounted into. Binderfile spec for data mounting? This should make the file 'magically' appear.


None of the things we build should be binder specific. Maybe there's a 'get my data' widget that gets me my data wherever it is.

FUSE is great when it works. The view for remote and local data for the user is the same! How to specify what gets injected.

Do you move the data to the compute, or do you move the compute to the data?

* streaming isn't always the bottleneck (if you have access to internet2)
