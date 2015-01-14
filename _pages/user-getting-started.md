---
layout: default
title: Getting Started
category: User Docs
permalink: /user/getting-started.html
---

# Embedding in your current repository

#### Step 1 - Create an orphan branch

Take your existing charm repository, and build an orphan branch like so:

    git checkout --orphan gh-pages

You can call this branch anything - but to have github-pages run hosting for your docs and do the build process, we'll need to call it gh-pages.

#### Step 2 -  Prep the directory for Doc Scaffolding

As this orphan branch has a completely separate history, we'll need to clean up the code thats left around.

    rm -rf *

This will clean out the repository of any leftover code from building the orphan branch.

#### Step 3 - Put the scaffolding in the directory

We can now populate it with the Kubrick template for generating our docs. Grab the latest
tag [from the releases page](https://github.com/chuckbutler/Kubrick-Documentation-Scaffolding/releases)

    wget https://github.com/chuckbutler/Kubrick-Documentation-Scaffolding/archive/0.0.1.tar.gz
    tar xvfz -C . 0.0.1.tar.gz
    rm 0.0.1.tar.gz
    git add .
    git commit -m 'Imported Kubrick Scaffolding'

#### Step 4 - Push to remote repository
You're now able to push to your remote gh-pages branch

    git push origin gh-pages

#### Step 5 - View Initial Template and hack on docs

Your documentation will be available at the github.io url associated with your repository nearly instantly.

![Github Settings for page generation](/images/gh_settings.png)

# Create a Documentation Repository

#### Step 1 - Create a new repository on github and clone

Create a new repository for your Documentation project, initialize it with a README and clone it

    git clone git@github.com:username/my-awesome-doc-project.git

#### Step 2 - Create gh-pages branch

To have Github run the page generation, we'll add a gh-pages branch:

    git checkout -b gh-pages

#### Step 3 - Put the scaffolding in the directory

We can now populate it with the Kubrick template for generating our docs. Grab the latest
tag [from the releases page](https://github.com/chuckbutler/Kubrick-Documentation-Scaffolding/releases)

    wget https://github.com/chuckbutler/Kubrick-Documentation-Scaffolding/archive/0.0.1.tar.gz
    tar xvfz -C . 0.0.1.tar.gz
    rm 0.0.1.tar.gz
    git add .
    git commit -m 'Imported Kubrick Scaffolding'

#### Step 4 - Push to remote repository
You're now able to push to your remote gh-pages branch

    git push origin gh-pages

#### Step 5 - View Initial Template and hack on docs

Your documentation will be available at the github.io url associated with your repository nearly instantly.

![Github Settings for page generation](/images/gh_settings.png)


