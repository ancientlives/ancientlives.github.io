---
title: Jekyll Directory Structure
author: ancientlives
layout: post-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 02
day: 06
published: true
summary: an overview of Jekyll directory structure
menu: jekyll-directory
---

A basic guide to using and modifying the directory structure of Jekyll. Please see the [Jekyll Documentation](http://jekyllrb.com/docs/structure/) 
for more information.

***

Contents |
-----------|
[Introduction](#intro) |
[Basic layout](#basic) |

***

<a id="intro"></a>
##### Introduction
In essence, Jekyll is a tool for processing text into a given format. For example, [Markdown](http://daringfireball.net/projects/markdown/), [Textile](http://redcloth.org/textile), or plain HTML
processing.

Jekyll enables you to modify how site URLs appear, the display of data in the layout, and much more. By modifying layout files, 
designers and developers can change how these files are processed.

<a id="basic"></a>
##### Basic layout
Jekyll uses the following basic site layout,

```
.
|- _config.yml
|- _drafts
|   |- draft1.md
|   |- draft2.md
|- _includes
|   |- header.html
|   |- footer.html
|- _layouts
|   |- default.html
|   |- post.html
|- _posts
|   |- 2014-02-24-post-1.md
|   |- 2014-03-19-post-2.md
|- _data
|   |- members.yml
|- _site
|- index.html
```

The above perform the following function in creating a Jekyll site,

* _config.yml = saves configuration data
* _drafts = unpublished posts, and the format does not include a date.
* _includes = sections of the site and pages, which can be reused.
* _layouts = templates that wrap posts. They are selected on an individual post bases, which is specified in the YAML front
matter.
* _posts = content that is regularly updated, such as blog posts. A naming convention for these files exists, and it must
follow the convention,
	* `Year-Month-Day-title.markup eg: 2014-02-24-post.md`
* _data = well-formed site data may be stored in this directory. Jekyll will autoload *YAML* files.
* _site = this is the default directory for our Jekyll generated site
* index.html = must include a *YAML* front section for Jekyll transformation, and includes `.html`, `.md`, `.markdown` or `.textile` files in the site's root directory or other non-default directories. 

