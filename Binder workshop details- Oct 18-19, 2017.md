# Binder workshop details: Oct 18-19, 2017

Where: UC Davis, Davis, CA. Nearest airports: SMF, OAK, SFO.
Times: 9am-5pm, plus optional evening sessions.

The core days are Wed, Oct 18th and Th, Oct 19th; the lights will be on from the 17th-20th, and participants are welcome to come for those days to prep and wind down, but core activities will be concentrated on 18/19th.

## What is this?

binder (mybinder.org) was a service to run Jupyter Notebooks from GitHub repositories, with only one click.  ([read more](http://ivory.idyll.org/blog/2016-mybinder.html)). It's original core group has moved on, and it is now being revived by the Jupyter team, who have nearly finished a re-write of the binder backend. This meeting is part of a binder 2.0 reboot to keep the momentum moving forward and explore new ideas for the binder ecosystem!

In 2016, Titus Brown wrote a [proposal to fund a workshop on binder](https://github.com/dib-lab/2016-binder-proposal-to-sloan) to the Sloan Foundation and it was funded!! We are (finally :) ) running this workshop, with an organizing committee that includes:

* [Abby Cabunoc Mayes](https://twitter.com/abbycabs?lang=en), Mozilla.
* [Tim Head](https://twitter.com/betatim), everware
* [Chris Holdgraf](https://twitter.com/choldgraf), UC Berkeley/Jupyter team
* [Yuvi Panda](https://twitter.com/yuvipanda?lang=en), UC Berkeley/Jupyter team.

## What will we work on?

Oooooh, we have a laundry list, below, but! We are inviting YOU because we want you to help figure that out!

A brief high-level summary (again - laundry list below) -

We expect three main streams of activities:
* how to set up binder yourself.
* get more people up to speed with the code for binder.
* exploring use cases and make cool examples.

but we are open to more ideas!

Note: there will be free punch and pie and cupcakes. Apparently, everybody shows up for punch and pie and cupcakes...

## How exactly will this all work?

We plan to run this like a ["birds of a feather"](https://en.wikipedia.org/wiki/Birds_of_a_feather_(computing)) or [unconference](https://en.wikipedia.org/wiki/Unconference), if you've ever been to one of those.  We'll do a few presentations at the beginning to showcase existing binder features and highlight deficits that we think could usefully be addressed. We'll do a schedule-building activity using sticky notes to gather questions and ideas from the audience throughout, and then at the end we'll define loose groups based on the sticky notes and ask everyone to choose their group of interest.  We will encourage moving between groups and solo endeavors, and we'll be sure to have several points of contact for open questions and brainstorming help.

## What skills are needed?

No one skill is necessary! Curiousity about or interest in the general area of portable notebook computing for research, education, and the betterment of humanity is all you need! We're inviting a mix of people - programmers (some of whom know all about Jupyter and some of whom don't), librarians, research scientists and data scientists, a journalist or two, educators and trainers, and more. Because of this mix we hope to have a pretty collaborative meeting with a bunch of attendees who communicate well with others.

## Who is invited?

You are! At least, you are if you received an invitation; if someone just forwarded this on to you, you should contact [Titus Brown](mailto:ctbrown@ucdavis.edu) and introduce yourself :)

That having been said, we may not be able to cover costs for everyone - it depends on how many people can come, and how far they're traveling.  But don't worry! If you've filled out the google form that you should have received with your invite, we've got your name and we'll put you on the list for future workshops (we expect there to be at least one).

(If you can self-fund your attendance, then you are certainly welcome to join us!)

## Is there anything else we should know?

This workshop will be under a Code of Conduct, probably the one that [the Carpentries use](https://software-carpentry.org/conduct/).

## Laundry list of workshop topics

Basically we think the idea of ~single-click Jupyter (and RStudio) is awesome, and we want to build out the ecosystem, which necessarily includes documentation, use cases, etc! This is a non-inclusive list...

1. Platform integration and hacking
    * the usual stuff :)
    * onboarding for people who want to know where the major integration points are
    * people from various platforms
    * IPFS, dat, osf for data integration
    * other ideas go here!!

2. Technical docs and installation and examples (example repositories)
    * example repositories / "best use cases"
    * run through tech docs in person
    * Set up R studio / R dependencies installation easily
    * Get time to set up a new binder to under 20 mins
    * Decide on a glossary (does 'binder' refer to a repo or an installation of binderhub)
    * other ideas go here!!

3. Brainstorming use cases and roughing out storyboards 

    * Here is where especially want to gather input from teachers, librarians, etc!


Some more ideas for what we want to get out of this:
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
* how to setup your own jupyterhub/binder like instance at home
* integration with Open Science Framework/osfcli

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
