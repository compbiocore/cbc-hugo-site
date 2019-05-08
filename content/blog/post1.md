---
title: "Post1"
date: 2019-05-08T10:11:47-04:00
draft: false
types: ["posts"] # keep only one of the categories
tags: ["documentation", "markdown"] # add keywords here, be consistent with other posts.
authors: ["Fernando Gelin"]
---

# Introduction

Welcome to the Brown University JupyterHub Documentation & Quickstart Guide.
This document is designed to help you get started using Jupyter notebooks served
by Google Cloud for use by the Brown University community. The implementation is
supported by Brown CIS, and for any questions/comments/concerns regarding
this service, please contact the Brown CIS JupyterHub team by emailing
jupyter-help@brown.edu.


The file marked with 2, contains the data used to create the navigation for the
particular project, and should contain all subsections of the document, where `ref`
is the name of the file in lowercase, separated by hyphens and followed by a
forward slash. This is important so the site navigation gets set-up correctly.
It's also important to include this file in all subsections folders, but with
a **different weight**. The weight value will define the order of the sections
in the navigation menu.

```yaml
---
Title: "Getting Started"
type: "JupyterHub"
section: "JupyterHub"
version: "beta"
weight: 1
subitems:
  - subsection: "Step 1: Sign In"
    ref: "sign-in/"
  - subsection: "Step 2: Sync Google Drive"
    ref: "sync-g-drive/"
  - subsection: "Step 3: Import Notebooks"
    ref: "import-notebooks/"
  - subsection: "Step 4: Launch a Notebook"
    ref: "launch-notebook/"
---
```

Once again, the content goes under the `---` with Markdown syntax. **In the
documentation content use level 1 headings for the main sections**. Level 1
headings are used on a right sidebar navigation for each page.


# Shortcodes

Shortcodes are snippets that you add to the content files with the rest of the
markdown. This allows us to add complex HTML to the content without having to
write raw HTML.

## Lead

The lead shortcode is used in the beginning of blog posts. You may notice that
the first paragraph in this post has a different font size then the rest of the
content. All posts should have a preface with a bigger font-size, and to accomplish
that we use the `lead` shortcode. Just wrap your text between the shortcode tags:
