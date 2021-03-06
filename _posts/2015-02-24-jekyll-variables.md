---
title: Jekyll Variables
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 02
day: 24
published: true
summary: an overview of Jekyll variables
menu: jekyll-variables
---

An overview of using variables within Jekyll. This data is available using the [Liquid](https://github.com/Shopify/liquid/wiki) templating engine.

***

Contents |
-----------|
[Introduction](#intro) |
[Global](#global) |
[Site](#site) |
[Page](#page) |

***

<a id="intro"></a>
#### Introduction
Jekyll uses the [Liquid](https://github.com/Shopify/liquid/wiki) template engine to access data within global, site, page, and paginator. Further
information can be found in the [Jekyll Documentation](http://jekyllrb.com/docs/variables/)

<a id="global"></a>
##### Global
There are four global variables for use with Jekyll,

* site
* page
* content
* paginator

Each of the above can be extended with options to enable more detailed retrieval of site data and information.

<a id="site"></a>
##### Site
The `site` variable allows us to retrieve data related to pages, posts, static files, html pages, collections etc. 

<a id="page"></a>
##### Page
The `page` variable enables us to drill down through page titles, metadata, categories, tags etc.


