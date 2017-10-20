# Creating a binder on github

## Super quick start

1. Create a new repository with a README file in it.

2. Copy the base URL of the repository into the form at [beta.mybinder.org](http://beta.mybinder.org)

3. Done!

Note that getting the URL is kind of tricky at the moment due to a UI bug in beta.mybinder.org.

## Adding Python software install requirements

Here is an example `requirements.txt`: [ctb/2017-sourmash-binder-demo](https://github.com/ctb/2017-sourmash-binder-demo/blob/master/requirements.txt)

1. Put a `requirements.txt` file in the top directory of your repository - this is a list of Python packages you want installed.  [(full documentation on format)](https://pip.readthedocs.io/en/1.1/requirements.html)

2. Copy the base URL of the repository into the form at [beta.mybinder.org](http://beta.mybinder.org)

3. Done!

You will now have a binder with that software installed.

## Miscellaneous important notes

### you are in a git repository!

Since `git clone` is used to create the binder, the binder itself knows what the originating git repository is.  So you can run git commands to push/pull changes.
