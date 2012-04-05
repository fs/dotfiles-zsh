FS dotfiles (based on thoughtbot's dotfiles repo)
===================

Install
-------

First, [fork this repo](https://github.com/fs/dotfiles#fork_box) on Github.

Then, clone your Github fork (replace "your-github-name" with your Github name) onto your laptop and install it:

    git clone --recurse-submodules git@github.com:your-github-name/dotfiles.git
    cd dotfiles
    ./install.sh

This will create symlinks for all config files in your home directory. You can
safely run this file multiple times to update.

There is configuration for `zsh` so switch your shell from the default `bash` to `zsh` on OS X:

    chsh -s /bin/zsh

Why fork?
---------

dotfiles are fairly personal. You should be able to modify your dotfiles, and save them in version control in your fork.

However, the fs folks are often tweaking these dotfiles and you want to be able to get those updates.

So, your master branch is meant for your customizations and use the `upstream` branch to get fs's updates.

Set up the upstream branch
--------------------------

You only have to do this once:

    git remote add upstream git@github.com:fs/dotfiles.git
    git fetch upstream
    git checkout -b upstream upstream/master

Update fs's changes into your customizations
----------------------------------------------------

You will want to customize your environment. We suggest making changes in files that are not in fs's files.

Commit those kinds of things in your master branch.

Then, each time you want to update thoughtbot's changes.

    git checkout upstream
    git pull
    git checkout master
    git rebase upstream
