# Brown Computational Biology Core Hugo Site

[![Travis](https://img.shields.io/travis/compbiocore/cbc-hugo-site.svg?style=flat-square)](https://travis-ci.org/compbiocore/cbc-hugo-site)


## Overview

This repository contains the Hugo project for Brown's Computational Biology Core website. It's set up as a node project in order to retrieve data for the **Genomics in the news** section using Embed.rocks.

## Requirements

- [Hugo](https://gohugo.io/)
- [Node](https://nodejs.org/en/)
- [NPM](https://nodejs.org/en/)
- [Gulp](https://gulpjs.com)


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
gulp sass embeds && hugo
```

## Deployment

A build will be triggered and deployed into a S3 bucket whenever changes are pushed to master **and** the Travis build passes. Currently, the website can be accessed at [http://cbc-website-dev.s3-website-us-east-1.amazonaws.com](http://cbc-website-dev.s3-website-us-east-1.amazonaws.com).
