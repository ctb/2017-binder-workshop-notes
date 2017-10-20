# Titus's demo of Binder



We'll need to links, the link to Tim's binder and the repository:
    https://beta.mybinder.org/v2/gh/wildtreetech/epfl-osip-2017/master
    https://github.com/wildtreetech/epfl-osip-2017/


Open https://beta.mybinder.org/v2/gh/wildtreetech/epfl-osip-2017/master

After opening the binder you'll see that the URL ends with a couple of random characters for me `-uvug8s8f`: `wildtreetech-epfl-osip-2017-uvug8s8f`; 

## Jupyter notebook

Open Bikes over the years

`Cell` - `Run all`
Takes a little bit to download the data, we are all running the same notebook on diff computers, and it’s downloading all of the same data.  It’s downloading to the remote computer that the notebook is running on. (Q - how do people get it on their local machine?)

No authentication going on, publicly accessible data.  This would run just fine on your laptop if you have all of the necessary stuff installed.  The dependencies are all in the cloud environment. For this particular repository the author did add a `requirement.txt` to the repository. Binder infered from this file that the repository should be using Python and have the libraries listed in `requirements.txt`.

The data is good and run when you see that cell 5 has a plot.  It’s live - if you change location on cell 5 to “upper right” and rerun the cell, you’ll see the plot change.  You can run the cell by hitting the play button.  You can add or remove data or change how you display the data live.

One other change — click on the top cell and click insert and insert a cell above.  Here I’m going to type ‘hello this is Titus’s blah blah blah thing’ and I’m also going to change the cell type to markdown (cell -> cell type -> markdown (makes it a documentation cell)). If I push a play on that cell, it renders as plain text.

Fundamental use case: document stuff and interactive display of data in one place.

We have Tim's repo that we opened our binder from.  We can open up as many binder instances from that.  If we fork Tim's repo, we can change our binder project and it's automatically compatible for binder.  You can't automatically update Tim's repo with the stuff you changed in your binder instance that we just opened.

Let's go to `file` -> `download as` -> `notebook`.  This exports the notebook that we modified.  This is the clunky step - it's saved on your laptop.  You can close the binder windows.  If you hadn't downloaded the notebook, the binders stuff would be gone.

If you go to github source (https://github.com/wildtreetech/epfl-osip-2017/) - click on fork in the upper right.  It makes a static copy of Tim's repository under your github user name.  Requirements.txt has two lines - pandas and matplotlib. We need training on how to write your requirements.txt file (this is also the only thing that binderizes your repo).  R is not installed by default on a binder.

If you run a notebook and save it, all of the output will be saved.  You trust that the person who ran the notebook and has the output uploaded it correctly and didn't change anything.  Github does not run the notebook itself and then show you the output.

From the root of the repository on github; click on upload files and then find the notebook file that you changed (bikes-over-the-years.ipynb). Here we've done it through the GitHub interface, we could also use git via the command line but we'll no cover this step as this is not a Git tutorial. You can click on this new uploaded notebook and GitHub should show you the rendered version with the Legend on the right place.

How do we run this as binder ?

We're going to copy the URL (which should look like `https://github.com/<yourusername>/epfl-osip-2017/`).

Let's head to https://beta.mybinder.org (in a few weeks you should be able to forget about the `beta` prefix) and paste the url in the first field.  Then click launch.  It takes all of the files and builds this virtual machine image and saves it.  You should see that it is your copy of the Jupyter notebook.  You should only have to do this once -- it should pick up your github changes.

While it was creating the binder -- it was creating a Docker image.  You go from a static repo to some kind of computer configuration - Docker is the environment, like a virtual machine.  It's like making a cd or a dvd that you can put in a computer and boot off of.  Docker is similar to that.  Binder image is a subset of a Docker image.  Binders now how to start them.  When you run binder, it connects to a web interface, but not all docker images do that.  Binder is a subset of a docker image.  All binder images are docker images.

This process of installing all of the software and whatever is slow.  You only want to do that once so you can have a bunch of people use the same binder image that is already configured. If you're doing this for a class, you would put a lot of time and effort into the setup so that the class attendees would only have to click once to have everything up and running in a short amount of time.

For an individual researcher - why is it good? Let's pretend that the researcher is an impeccable scientist.  In that relatively rare case, if I wanted to convey this cool thing with some cool data visualization, I could share it very easily with the environment and the data and the documentation. It's a collaboration not a training.  It can be a source of conflict of which version of which software you have installed.  If you're working on a team, this is helpful for collaboration to keep people in sync.


URL interpretation:
https://beta.mybinder.org/v2/gh/wildtreetech/epfl-osip-2017/master
gh - github
wildreetech - your github username / organization
epfl-osip-2017 - the repo name
master - the branch

Suppose that I want to share my binder - how do I generate that?  Change the url to match those three things.


Let's create a new repo and put it into binder.  Go to github, click the plus for a new repo, click button to initialize it with a readme file.  Titus thinks that this will be a 100% compatible repo for binder.  If you paste the repo link to the binder website and launch it, it should open up an empty jupyter notebook.  (but no one has gotten it to work!)

There's no way to save it from your binder to github -- you always have to save it to your desktop and upload it back to github.  Anyone can create a binder of any public repo, but not everyone can write back to the repo.  When you launch a binder, it doesn't know that you're the owner which is why it doesn't allow you to save to github.

If you don't need to install anything, then there's nothing special to make it compatible with binder.

If your internet connection goes down and you haven't saved it yet, are you screwed? Yes.  Jupyter hub is for repeat connections and authentication and infrastructure underneath and long running stuff.  Binder is for here's a public notebook and I want to experiment and it's okay for it to go away.

Real time collaboration is in the works but you can right now share using google drive to edit the same notebook by multiple people at the same time.  

This fits certain models really well if you want to run the data analysis of published papers.  It's not great for long running things.

If you are in a jupyter notebook and you click on new, you can run whatever is configured.  You can make a folder, text file, or terminal.  Terminal gives you a shell prompt on your remote computer. You can teach shell workshops here.

A cool integration would be to have CI that shows if your notebook runs properly.