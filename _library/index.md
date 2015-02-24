---
title: Library
layout: default-vertical

categories:
- library
- notes
- research

tags: library notes research reading
published: true
summary: a personal collection of notes, research, and other media
---

Welcome to the *ancientlives* library. 

This is a collection of personal notes and other media, and is guided by current and past research, reading, and 
personal interests.

#### Latest Content

{% for post in site.categories.library limit: 5 %}
  <li>
    {{ post.date | date_to_string }} | <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
{% endfor %}

***

Please consult the following categories for further information and available sub-categories.

#### Contents
* [Notes](notes)
  * [Dev](notes/dev)
  


