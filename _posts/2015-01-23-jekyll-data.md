---
title: Jekyll Data Files
author: ancientlives
layout: post-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 01
day: 23
published: true
summary: an overview of Jekyll data
menu: jekyll-config
---

An overview of data files in Jekyll. Further information can be found on the [Jekyll](http://jekyllrb.com/docs/datafiles/) website.

***

Contents |
-----------|
[Introduction](#intro) |
[Data folder](#folder) |
[Example usage](#usage) |

<a id="intro"></a>
##### Introduction
Jekyll accepts custom data, which is accessed via the *Liquid* template engine. It supports loading data from *YAML*, *JSON*, and *CSV* files,
which are stored in `_data` directory. 

*NB:* *CSV* files must contain a header row.

<a id="folder"></a>
##### Data folder
In Jekyll, the `_data` folder is used to store additional data for processing during the site build. These data files must be *YAML* compliant, 
and a `.yml, .yaml, .json or csv` file extension is supported. These data files are also accessible via `site.data`.

<a id="usage"></a>
##### Example usage
A data file might be used to store repetitive data, such as a group or member list, to avoid tedious duplication throughout a site. For example,
a list can be stored in `_data/members.yml`, and then accessed via `site.data.members`. The filename determines the variable name.

We could then access this data as follows,

```
{% raw %}
{% for member in site.data.members %}
{{ member.name }}
{% endfor %}
{% endraw %}
```

Data files can also be stored in sub-folders of the `_data` folder. Each hierarchical level is then added to the variable's namespace.