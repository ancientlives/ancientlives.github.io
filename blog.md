---
title: Blog Posts
layout: default-vertical

categories:
- blog
- index

tags: index blog
published: true
summary: an index of site blog posts
---

{% for post in site.posts %}
* {{ post.date | date: "%d-%m-%Y" }} | [{{ post.title }}]({{ post.url }})
  
  {{ post.summary | replace: '<h3>','<h6>' | replace: '</h3>','</h6>' }}
  
  Tags: {% for tag in post.tags %} <a href="/tags/{{ tag }}">{{ tag }}</a>  | {% if forloop.last != true %} {% endif %} {% endfor %}
---
{% endfor %}
