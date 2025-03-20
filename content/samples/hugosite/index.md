+++
date = '2025-03-04T10:38:42-08:00'
draft = false
title = 'Procedure: Building a Site with Hugo and GitHub Pages'
type = 'post'
description = 'This site was built with Hugo, a static site generator. This sample documents how I created and deployed this site.'
tags = ['Hugo','Git','SSG','procedure']
weight = 9
showTableOfContents = true
+++

## About This Sample

The sample below was created to document my own process of creating this site. This is written primarily for other content developers moving from a traditional content management system into a static site generator.

The sample begins below the line.

---

This portfolio site was built using Hugo, [a static site generator (SSG)](https://idratherbewriting.com/learnapidoc/pubapis_static_site_generators.html). SSGs are becoming increasingly common as a publishing tool, particularly for API documentation and other docs-as-code scenarios. Unlike a traditional content management system (CMS) like Wordpress, SSGs don't have databases. This enables them to build websites more quickly. They are also more secure because without a database, there is no threat of database hacks.

Hugo is one of the most popular SSGs available. For content developers interested in creating a portfolio site, follow this guide to create a Hugo site and deploy it to GitHub Pages.

## Tools

- command line interface (CLI) tool
	- [Powershell](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5): Windows users must use Powershell as their CLI tool. Not to be confused with Windows Powershell, which should not be used.
- [Notepad++](https://notepad-plus-plus.org/), or text editor of your choice

## Installation

Install the following. Note that the Dart Sass and Hugo installations require you to add new directories to your computer's `PATH` environment variable. [See instructions here.](https://katiek2.github.io/path-doc/)

- Prerequisites for Hugo
	- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
	- [Go](https://go.dev/doc/install)
	- [Dart Sass](https://sass-lang.com/install/)
- [Hugo](https://gohugo.io/installation/)

## Creating a Site

1. [Select a theme](https://themes.gohugo.io/). Consider whether you need a single- or multi-page theme for your site. It's also worth noting each theme's documentation. This site uses [the Gokarna theme](https://github.com/gokarna-theme/gokarna-hugo?tab=readme-ov-file), which provides [extensive](https://gokarna-hugo.netlify.app/posts/theme-documentation-basics/) [documentation](https://gokarna-hugo.netlify.app/posts/theme-documentation-advanced/). This makes it easier to configure compared to themes with sparse documentation.
2. Follow [Hugo's quick start tutorial](https://gohugo.io/getting-started/quick-start/) to create a site and a new page.
3. Enable embedded link and image render hooks: Open the site configuration file, `hugo.toml`, in your text editor. Add the following into the file.

```toml
[markup]
  [markup.goldmark]
    [markup.goldmark.renderHooks]
      [markup.goldmark.renderHooks.link]
        enableDefault = true
      [markup.goldmark.renderHooks.image]
        enableDefault = true
```

4. Create additional site content. To ensure proper image processing, site content should be organized in the structure below with global resources in `assets/images` and page resources bundled into separate `content` folders.

```bash
assets/
└── images/
    ├── a.jpg			<-- global resource, accessible sitewide
    └── b.jpg
content/
├── samples/
│   ├── sample1/
│   │   ├── c.jpg 		<-- page resource, accessible by sample1/index.md only
│   │   └── index.md  	<-- contents of sample1 page (without underscore)
│   ├── sample2/
│   │   ├── d.jpg
│   │   └── index.md
│   └── _index.md		<-- samples section list page (with underscore)
├── posts/
│   ├── post1/
│   │   ├── e.jpg
│   │   └── index.md
│   └── _index.md
└── _index.md			<-- site homepage (with underscore)
```

## Deploying to GitHub Pages

Follow [Hugo's instructions for hosting on GitHub Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/). Note that for Powershell users, the `touch filename.txt` command is replaced by `"" > filename.txt`.

In addition, remove your public directory from source control using these steps.

1. Create a `.gitignore` file using this command.

```bash
touch .gitignore
```

For Powershell users, the command uses this syntax.

```bash
"" > .gitignore
```

2. Open the `.gitignore` file in your text editor. Add the following:

```bash
.hugo_build.lock
/public/
/resources/
```

3. Remove the public directory from source control.

```bash
git rm -rf public/
```

4. Commit and push your changes.

```bash
git add -A
git commit -m "Remove public directory from source control"
git push
```