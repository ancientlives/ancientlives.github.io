---
title: Liquid Tips and Tricks
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev site-building liquid
year: 2015
month: 01
day: 06
update: 08 Jan 2015
published: true
summary: tips and tricks for using Liquid
menu: liquid-tricks
---

A collection of tips and tricks for getting the most out of the [Liquid](https://github.com/Shopify/liquid/wiki) template engine. These are predominantly used with [Jekyll](http://jekyllrb.com). 

***

Contents  |
----------- |
[Category and tags](#cat-tags) |
[Unique values](#uniq-val) |
[Breadcrumbs](#breadcrumbs) |

***

<a id="cat-tags"></a>
##### Category and tags

* The following logic allows us to retrieve post tags for the site.
  * capture all items
  * loop through site tags
    * get the string representation of the tag
  * capture number of words per tag list per post
    * split, sort, join, and save words
  * loop through each item in words
    * output each tag

Code example,

```
{% raw %}
{% capture get_items %}
 {% for tag in site.tags %}
   {{ tag | first }}
 {% endfor %}
{% endcapture %}
{% capture num_words %}
 {{ get_items | split:' ' |  sort | join:' ' | number_of_words }}
{% endcapture %}
{% for item in (1..num_words) %}
 <li><a href="/tags/{{ get_items | split:' ' |  sort | join:' ' | truncatewords:item | remove:'...' |    split:' ' | last }}">{{ get_items | split:' ' |  sort | join:' ' | truncatewords:item | remove:'...' |    split:' ' | last }}</a></li>
{% endfor %}
{% endraw %}
```

* The following logic enables filtering of post tags for a specified site category.
  * capture all tag items
  * loop through posts for a defined site category, eg: blog
    * loop through each tag per post and record the tag
  * assign tag items and split as necessary
  * assign the first index of the assigned tag items
    * loop through each item and check if item already exists in tags (this allows us to output unique tags)
    * capture these tags
  * assign these tags, split, and then sort to correct order for strings (if applicable)
  * loop through assigned tags and output each tag

Code example,

```
{% raw %}
{% capture tag_items %}
 {% for post in site.categories.library %}
 {% for tag in post.tags %}
  {{ tag }}
 {% endfor %}
 {% endfor %}
{% endcapture %}
{% assign array = tag_items | split: ' ' %}
{% assign tags = array[1] %}
{% for item in array %}
 {% unless tags contains item %}
  {% capture tags %}{{ tags }}|{{ item }}{% endcapture %}
 {% endunless %}
{% endfor %}
 
{% assign tag_array = tags | split: '|' | sort %}
 
{% for tag in tag_array %}
<li><a href="/tags/{{ tag }}">{{ tag }}</a></li>
{% endfor %}
{% endraw %}
```

<a id="uniq-val"></a>
##### Unique values

The following trick allows us to filter an array for unique values. Hat-tip to a [Gist](https://gist.github.com/pepelsbey/9334494) by *pepelsbey*

Code example,

```
{% raw %}
{% assign array = 'c|c|b|b|a|a' | split: '|' %}
{% assign tags = array[1] %}

{% for item in array %}
    {% unless tags contains item %}
        {% capture tags %}{{ tags }}|{{ item }}{% endcapture %}
    {% endunless %}
{% endfor %}
{% endraw %}
```

<a id="breadcrumbs"></a>
##### Breadcrumbs

The following allows us to split a page URL to create an array of items for a page's breadcrumb listing.

Code example,

```
{% raw %}
{% assign url_array = page.url | remove_first:'/' | split: '/' %}
{% endraw %}
```



