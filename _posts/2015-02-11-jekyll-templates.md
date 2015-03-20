---
title: Jekyll Templates
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 02
day: 11
published: true
summary: an overview of Jekyll templates
menu: jekyll-templates
---

A brief overview of the options for templates in [Jekyll](http://jekyllrb.com/docs/)

***

Contents |
-----------|
[Introduction](#intro) |
[Filters](#filters) |
[Tags - Includes](#includes) |
[Tags - Code highlighting](#code) |
[Tags - Post URL](#post) |
[Tags - Gist](#gist) |

***

<a id="intro"></a>
##### Introduction
Jekyll uses the *Liquid* temple engine to process templates. Liquid's standard tags and filters are supports, and there are a few useful filters
and tags added by Jekyll itself. These are primarily for common tasks.

<a id="filters"></a>
##### Filters
Template filters include date manipulation and formatting, array usage and manipulation, string manipulation and formatting, url formatting, and
basic JSON usage. A full list is available at [Jekyll](http://jekyllrb.com/docs/templates/). 

<a id="includes"></a>
##### Tags - Includes
This allows a developer to ember small code fragments in a file. It works in a similar fashion to PHP's `include`. For example,

```
{% raw %}
{% include footer.html %}
{% endraw %}
```

All include files need to be stored in the `_includes` directory in Jekyll.

Jekyll includes can also include parameters, 

```
{% raw %}
{% include footer.html param="copyright_year" %}
{% endraw %}
```

which are then accessible via Liquid

```
{% raw %}
{{ include.param }}
{% endraw %}
```

We can also use `include_relative` to store an include file relative to the current file's path. However, this include will then only be available
from that local directory. For example, if a file stored at `_posts/2014-12-31-file.md` uses the `include_relative` tag, the include file must be 
in the same directory of a sub-directory.

<a id="code"></a>
##### Tags - Code highlighting
Jekyll supports syntax highlighting using *Pygments*, which supports over 100 languages. You can also use *Rouge*, if preferred. We can also force
the highlighter to include line numbers for the highlighted code block.

<a id="post"></a>
##### Tags - Post URL
It is possible to included a link to a post on your site, which includes the correct permalink URL for the post. This `post_url` tag can also be
used to create a link to a site post in Markdown.

<a id="gist"></a>
##### Tags - Gist
We can also embed GitHub Gists on a Jekyll site using the `gist` tag.