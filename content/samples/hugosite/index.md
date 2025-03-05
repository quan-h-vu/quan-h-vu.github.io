+++
date = '2025-03-04T10:38:42-08:00'
draft = false
title = 'Building a Portfolio with Hugo and GitHub Pages'
type = 'post'
description = 'This site was built with Hugo, a static site generator. This sample documents how I created and deployed this site.'
tags = ['Hugo','Git','SSG']
weight = 15
+++

## About This Sample

The sample below was created to document my own process of creating this site. This is written primarily for other content creators moving from a traditional content management system (CMS) into a static site generator for the first time.

The sample begins below the line.

---

This portfolio site was built using Hugo, a static site generator (SSG). SSGs are becoming increasingly common as a publishing tool, particularly for API documentation and other docs-as-code scenarios. Unlike traditional content management systems like Wordpress, SSGs don't have databases. This enables SSGs to build websites more quickly. They are also more secure because without a database, there is no threat of database hacks.

Follow this guide to create and deploy a Hugo site to GitHub Pages.

## Tools Overview

For users coming from a traditional CMS background, it's useful to review the tools you'll use.

- command line interface (CLI) tool: Used for installation, creating new content files, publishing and deploying files to your site. This includes applications such as Powershell and VSCode.
- text editor: Used to edit content files, configuration files, and templates. This includes applications such as Notepad++.
- GitHub web UI: Used to monitor processes when changes are deployed to the site.

## Installation

- Prerequisites for Hugo
	- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
	- [Go](https://go.dev/doc/install)
	- [Dart Sass](https://sass-lang.com/install/)
- [Hugo](https://gohugo.io/installation/)
- Other tools
	- [Powershell](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5): For Windows users only. Not to be confused with Windows Powershell, which should not be used.
	- [Notepad++](https://notepad-plus-plus.org/), or your text editor of choice.

The Dart Sass and Hugo installations require you to add new directories to your computer's `PATH` environment variable. [See instructions here.](https://katiek2.github.io/path-doc/)

## Creating a Site

1. [Select a theme](https://themes.gohugo.io/). Consider whether you need a single- or multi-page theme for your site. It's also worth noting each theme's documentation. Some themes have sparse documentation, which can make it more difficult to configure the theme to your needs.
2. Follow [Hugo's quick start tutorial](https://gohugo.io/getting-started/quick-start/) to create a site and a new page.
3. Enable embedded link and image render hooks. Open the site configuration file, `hugo.toml`, in your text editor. Add the following into the file.

```
[markup]
  [markup.goldmark]
    [markup.goldmark.renderHooks]
      [markup.goldmark.renderHooks.link]
        enableDefault = true
      [markup.goldmark.renderHooks.image]
        enableDefault = true
```

4. Create additional site content. To ensure proper image processing, site content should be organized in the structure below.

```
assets/
└── images/
    ├── a.jpg  <-- global resource, accessible sitewide
    └── b.jpg
content/
├── posts/
│   ├── postname1/
│   │   ├── c.jpg  <-- page resource, accessible by postname1/index.md only
│   │   └── index.md  <-- contents of postname1 page
│   ├── postname2/
│   │   ├── d.jpg
│   │   └── index.md
│   └── _index.md  <-- list page for posts section
└── _index.md  <-- site homepage
```

## Deploying a Site to GitHub Pages

Follow [Hugo's instructions for hosting on GitHub Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/). Note that for Powershell users, the `touch filename.txt` command is replaced by `"" > filename.txt`.

In addition, I had to remove my public directory from source control using these steps.

1. Create a `.gitignore` file.

```
touch .gitignore
```

For Powershell users, the command uses this syntax.

```
"" > .gitignore
```

2. Open the `.gitignore` file in your text editor. Add the following:

```
.hugo_build.lock
/public/
/resources/
```

3. Remove the public directory from source control. Commit and push your changes:

```
git rm -rf public/
git add -A
git commit -m "Remove public directory from source control"
git push
```