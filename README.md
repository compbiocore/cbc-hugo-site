# Brown Computational Biology Core Hugo Site

[![Travis](https://img.shields.io/travis/compbiocore/cbc-hugo-site.svg?style=flat-square)](https://travis-ci.org/compbiocore/cbc-hugo-site)


## Overview

This repository contains the Hugo project for Brown's Computational Biology Core website. It's set up as a node project in order to retrieve data for the **Genomics in the news** section using Embed.rocks.

## Requirements

- [Hugo](https://gohugo.io/)
- [Node](https://nodejs.org/en/)
- [NPM](https://nodejs.org/en/)

## Install Dependencies

```bash
npm install
```

## Set up `.env` file with Embed.rocks API key
Sensitive environment variables are stored in the .env file. This file is included in .gitignore intentionally, so that it is never committed.
- Create a `.env` file and copy into it the contents of `.env.template`
- Create an account at [Embed.rocks](https://embed.rocks/)
- Go to the dashboard, copy the key and add that to your `.env` file

## Local Development

```bash
npm start
```

When you run `npm start`, a Gulp pipeline will start. That will collect the embeds based on the list of urls listed in Hugo's
`config.yml` and dump the data into `data/embeds.json` so it can be used in Hugo templates. CSS will be compiled and a Hugo server will start.
To see the site, navigate to `localhost:1313`.

## Build

Build site into `public/`:

```bash
npm run build
```


## Adding posts to Blog section

Posts are divided in three sub categories:
- **Events**: we include events that have a long description. Ex. [DSCoV workshops](https://datasci.brown.edu/ccv-dev/2019/01/data-science-computing-and-visualization-workshops/). Other events, go directly on CCV's calendar (more on this later).
- **Posts**: Any blog post you want.
- **Projects**: Student projects, or projects you want to showcase that doesn't have a standalone website.

`.md` files in the Blog post section have the following front-matter:

```yaml
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: false
types: ["events", "posts", "projects"] # keep only one of the categories
tags: [""] # add keywords here, be consistent with other posts.
authors: [""]
---
```

To create a new file:
```shell
hugo new content/english/news/posts/post.md
```
Hugo will create a new `.md` file with the front-matter. If you don't use Hugo's cli, make sure to add the front-matter to your file.
