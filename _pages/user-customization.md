---
layout: default
title: Customizing the Template
category: User Docs
permalink: /user/customization.html
---

# Customizing from a base install

The template has a few features - and makes some assumptions along the way.

## Setting Site Configuration

The first thing you'll want to do is set up your options in `_config.yaml`

    keep_files: ['css', 'js']
    include: ['_pages']
    relative_permalinks: false
    encoding: utf-8
    product: Docker
    keywords: docker charm, charm documentation, juju deploy containers
    analytics_id: UA-XXXX
    repository: chuckbutler/docker-charm
    forkme_enabled: true
    url: http://github.io/chuckbutler/docker-charm

## Jekyll Configuration Options

- keep_files: ['css', 'js']
- include: ['_pages']
- relative_permalinks: false
- encoding: utf-8

These options are safe defaults, and are directives to Jekyll that instruct it how to build the site. Its safe to ingore these settings unless you want to modify the underlying Jekyll behavior.

## User / Project Configuration Options

- **product**: Used to denote any third party product consumed (in the case of charms) and links to the documentation of that product (more on this in [Navigation](#navigation)
- **keywords**: Added to meta header for SEO
- **analytics_id**: Populate with your UA-XXX code from Google Analytics. Used to track statistics of your documentation. Can be safely removed, and as a byproduct the GA JS will not be included either.
- **repository**: username/project on github. Used in tandem with `forkme_enabled`
- **forkme_enabled**: Places a nifty ribbon on your site to link back to your github repository
- **url**: Base URL of your documentation location. Doesn't have to be github. **note:** its useful to set this to localhost:4000 during development.

## Adding Pages

There is no make target for generating new pages. The only requirement is that it's in a format that Jekyll understands, such as RST or Markdown.

Create the page in `_pages/`. for example: `_pages/user-getting-started.md`

You will need to front-load the markdown page with some metadata in order for Jekyll to parse it:

    ---
    layout: default
    title: Getting Started
    category: User Docs
    permalink: /user/getting-started.html
    ---

- **layout** Denotes the HTML layout to use. Presently only default is implemented.
- **title** Title of the page
- **category** Used in bread crumb generation, modified by converting to lower, spaces are interchanged with -'s and linked as /{{ modified }}.html
- **permalink** Location to render the docpage.

## Navigation

Navigation items are data driven in the scaffolding, and fed by YAML documents that are containers for array data. You can inspect this in the `_data` directory for examples.

#### Side Navigation

The sidebar navigation is composed of 2 files. `user_nav.yaml` and `dev_nav.yaml` both correlate to their respective locations in the sidebar. The format of adding links is

    - name: foobar
      url: /user/foobar.html

This is to enable page generation without being linked into the nav - for sub-topic pages.

#### Top Navigation

The topbar navigation is comprised of a few files

    - jujucharms_devnav.yaml
    - jujucharms_solutionnav.yaml
    - jujucharms_usernav.yaml
    - product_nav.yaml

Each of the respective data files correlates to the topbar navigation unit. and follows the same guide as Side Navigation

## Template Customization

All of the template code is included in `_layout` and `_includes/modules`. The template is broken down into logical components and re-assembled during doc building. Feel free to modify any of these files to suit your needs. All styling updates can be done in the `css` files, and `js` is for Javascript.

You will need to have a fair understanding of [Liquid Templates](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) to make modifications to the templates.

If you have any questions I'll do my best to answer them. I can be found on irc.freenode.net in #juju as lazyPower.

