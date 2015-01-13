# ![](http://blog.dasroot.net.s3-website-us-east-1.amazonaws.com/images/kubrick-logo.png) Kubrick Charm Documentation Scaffolding

This charm template scaffolding is a tribute to film director, screenwriter, producer, editor, and cinematographer Stanley Kubrick. You might be asking what's the correlation? You wont find it. I just enjoy his work and wanted to attribute something to his name.

### Why?

Because charms are full-fledged software projects, leaving them at just a README file really seemed wrong to me. I wanted a quick way to generate documentation about a charm in lock-step verions with my code. A really quick way to do this would be to embed the documentation in the charm (or in a branch in the charm) and keep that in lock-step with the charm code. As revisions are tagged - tag the documentation as a complimentary tag and you're cooking with gas without breaking your workflow. Jekyll makes this super simple, and kind of fun!

### Getting Started

> If you don't want to run any local build process to verify settings - simply skip down to "Docs in my Github Repository"

##### The Ruby Path
If you want to run your docs locally for development purposes, and to tweak the theme/content - these are the instructions for a vanilla ubuntu 14.04 machine:


    apt-get install ruby1.9.3 build-essential
    gem install github-pages

##### The Python Path

> TBD (but I hear HYDE is what you're looking for)

##### Docs in my Github Repository

Take your existing charm repository, and build an orphan branch like so:

    git checkout --orphan gh-pages

In reality you can call this branch anything - but to have github-pages run hosting for your docs and do the build process, we'll need to call it gh-pages. You'll notice you have all your existing charm code lying around... and at this point. you need to do something scary.

    rm -rf *

This will clean out the repository of any leftover code from building the orphan branch. We can now populate it with the Kubrick template for generating our docs. Grab the latest tag [from the releases page](https://github.com/chuckbutler/Kubrick-Documentation-Scaffolding/releases)

   

