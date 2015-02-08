---
title: Jekyll Semantic Options
author: ancientlives
layout: post-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 02
day: 08
published: true
summary: an overview of Jekyll semantic options
menu: jekyll-semantic
---

A brief overview of the options for semantic organisation of data in [Jekyll](http://jekyllrb.com/docs/)

***

Contents |
-----------|
[Introduction](#intro) |
[Tagging](#tagging) |
[Categorisation](#cats) |

***

<a id="intro"></a>
##### Introduction
Jekyll offers a few basic options for creating a site's categories, and adding a folksonomy through tagging. Related information, such as posts,
can also be determined from this categorisation.

<a id="tagging"></a>
##### Tagging
In the YAML front matter, we can add custom defined tags for a page, post etc. These can be called for the page itself when it is loaded. For
example,

```
tags:
- index
- semantics
- folksonomy
```

and so on. We can then output these tags as follows,

`{{ page.tags }}`

We can also list all posts for a given tag. For example,

`site.tags.tag`

<a id="cats"></a>
##### Categorisation
Defining categories for a page, post etc follows the same pattern as tagging.



