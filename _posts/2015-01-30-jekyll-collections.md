---
title: Jekyll Collections
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 01
day: 30
published: true
summary: an overview of Jekyll collections
menu: jekyll-collections
---

An overview of using collections with Jekyll. Further information can be found on the [Jekyll](http://jekyllrb.com/docs/collections/) website.

***

Contents |
-----------|
[Introduction](#intro) |
[Using collections](#using) |
[Creating collections](#creating) |
[Permalinks](#permalinks) |
[Liquid integration](#liquid) |

***

<a id="intro"></a>
##### Introduction
*NB:* Collections are currently listed as *unstable*, and the following API references may change.

Collections allow the organisation of content not necessarily suitable for *pages* or *posts*. They allow a developer/designer 
to define a new type of document, which can augment the standard functionality of *pages* and *posts*.

<a id="using"></a>
##### Using collections
Jekyll requires explicit listing of collections in a site's `_config.yml` file. For example,

	collections:
	- learning_collection

We can also add metadata to this record,

	collections:
 	learning_collection:
  	output: true

<a id="creating"></a>
##### Creating collections
Each collection requires its own directory, for example

`my_site/_learning_collection`

The directory's name must match the collection name specified in the `_config.yml` file with the addition of a preceding underscore character.

Jekyll will read a file's *YAML* front matter, if it exists, otherwise it will add all content to the document's `content` attribute.

Files can be rendered as child documents to the parent collection by setting `output: true` for a given collection in the site's `_config.yml` 
file. This allows developers / designers to create a specific directory structure for collection documents and files. For example,

`my_site/learning_collection/notes/overview.md`

The child document is rendered as `overview.html`, and the directory hierarchy is maintained. URL would be as follows,

`http://www.mysite.com/learning_collection/notes/overview.html`

<a id="permalinks"></a>
##### Permalinks
A collection's *Permalink* can also be customised in the `_config.yml` file. This allows a developer / designer to customise their site's URLs. A
number of variables are available for this option, including

* collection
* name
* output_ext
* path
* title

<a id="liquid"></a>
##### Liquid integration
The `site` Liquid variable can be used to access a collection. For example, we could access the `_learning_collection` using the following,

`site.learning_collection`

We can also use `site.collections` to access a collection's metadata, as specified in the `_config.yaml` file. We can access the following

* directory (full path)
* docs (array of collection documents)
* label (name of the collection)
* output (output setting)
* relative_directory (path to collection's source directory relative to site)

	NB: This is currently one feature that is not working as expected. A quick fix is as follows,

```
{% raw %}
{% for collection in site.collections %}
{{ collection[1] }}
{{ collection[1].directory }}
{% endfor %}
{% endraw %}
```

```
{% raw %}
{{ collection[1] }}
{% endraw %}
```
	
outputs the content of the current loop counter's collection array, and 
 	
 ```
 {% raw %}	
 {{ collection[1].directory }}
 {% endraw %}
 ```
 
outputs the directory. This can be used to output attributes for each collection.

Each document, in addition to the standard *YAML* front matter, can use the following attributes

* collection (document's collection)
* content (unrendered content of the document following the *YAML* front matter)
* output (rendered content)
* path (full path to document's source)
* relative_path (path to document's source relative to site source)
* url (url of the rendered collection)
