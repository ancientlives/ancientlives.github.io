---
title: Welcome
layout: default-vertical

categories:
- general
- site

tags: general site home
published: true
summary: ancientlives is a personal collection of data, including notes, tutorials, and other media
---

#### Recent Updates
{% for post in site.posts limit: 5 %}
* {{ post.date | date: "%d-%m-%Y" }} | [{{ post.title }}]({{ post.url }})

  {{ post.summary }}
{% endfor %}




