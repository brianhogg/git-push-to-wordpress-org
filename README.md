# wporg-git-svn

Handy scripts so can update your plugin hosted on wordpress.org using git without remembering those annoying svn commands.

These assume you are, or want to, [tag your releases](https://wordpress.org/plugins/about/svn/#task-3) (which you should be)

## Installation

This works by setting up a git bare repository on your local machine which can be pushed to.  This will verify the version number is new (since you need to change it to do an update), and do all the svn stuff to commit and tag your release.

You need command line git and svn on your local machine.  These instructions are for MacOSX, if you run windows and can help with those instructions let me know.

`cd <your wp.org svn repo folder>
mkdir git-remote
cd git-remote
git init --bare`

then copy the `update` and `post-receive` files to the hooks/ folder (in git-remote)

`chmod a+x update
chmod a+x post-receive`

## Pushing a new version

Just do:

`git push wporg master`

No more (expletive) svn!

## Updating just the readme.txt

For example you want to update the 'tested to' version but not tagging a new release
