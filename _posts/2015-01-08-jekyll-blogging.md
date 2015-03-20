---
title: Jekyll Blogging
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev site-building jekyll
year: 2015
month: 01
day: 08
published: true
summary: an introduction to Jekyll
menu: jekyll-blogging
---

A brief overview of how to set up blog posts with [Jekyll](http://jekyllrb.com).

***

Contents |
-----------|
[Introduction](#intro) |
[Saving](#saving) |
[Post slug](#slug) |
[Formats](#formats) |
[Images and resources](#images) |
[Index of posts](#index) |
[Post filters](#filters) |
[Post excerpts](#excerpts) |
[Pagination](#pagination) |
[Code highlighting](#code) |
[Drafts](#drafts) |

***

<a id="intro"></a>
##### Introduction
Blogging with Jekyll is similar to Wordpress, for example, in the general concepts required to build a blog. For example, Jekyll posts use a 
similar *looping* concept. 

A *post loop* is simply a way of ensuring that a blogging platform returns a certain list of posts. This will often be as simple as requesting 
posts one to ten, and then an overflow onto the second page, and so on. This example request uses an iterator to output the same HTML content for
each block of ten posts. Therefore, the same code to output as many posts as needed, each in blocks of ten.

<a id="saving"></a>
##### Saving
Jekyll supports posts written in Markdown and Textile.

Each blog post is an individual file, which is saved in the `_posts` folder. These posts must be saved, however, using the following naming format

`YYYY-MM-DD-title.md`

Obviously, the file extension needs to match the markup employed for each file. Also, each word in a title needs to be separated with a dash. An 
example post file might be saved as follows,

`2014-06-21-first-day-of-summer.md`

<a id="slug"></a>
##### Post slug

The above type of URL is often referred to as a *post slug*, which is URL friendly format for a post's name. A few conventions apply,

* no spaces, unusual characters, or anything not normally permitted in a URL
* standard convention suggests lower case letters, and dashes instead of spaces
* keep the slug relatively short

<a id="formats"></a>
##### Formats
All post files must begin with *YAML Front Matter*. The post itself is simply a matter of writing your content in your preferred format.

<a id="images"></a>
##### Images and resources
Images, and other media resources, can be stored within Jekyll's directory structure. It is common practice to include these files in a directory
such as `assets`, `media` etc, which is stored in the root directory.

Images etc can be added to posts and pages using the site's root as the path for the `assets` directory. For example, 

`![image title...]({{ site.url }}/assets/screenshot.jpg)`

Without `site.url`, there is the inherent assumption that a site will be stored in the root directory of a domain. If this assumption is correct, 
then it is not necessary to include `site.url`.

<a id="index"></a>
##### Index of posts
We can also create an index of existing posts using the [Liquid](http://docs.shopify.com/themes/liquid-documentation/basics) template engine.
For example, we can output a list of posts using a simple for loop,

```
{% raw %}
{% for post in site.posts %}
<a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
{% endraw %}
```

We can, of course, add this output to an unordered list etc, and style the output HTML as required.

We can also restrict the number of posts output, for example to create a most recent list, using the following

`{% raw %}{% for post in site.posts limit: 5 %}{% endraw %}`

We can use this structure on any page etc where we want output blog posts. We simply modify the `for loop` to match each requirement.

<a id="filters"></a>
##### Post filters
Filters are snippets of Ruby code, which we can use to modify the content output. For example,

`{% raw %}{{ post.title | truncatewords: 10 | capitalize }}{% endraw %}`

which truncates a post's title and then capitalises. We could also manipulate a post's data to a different format, for example

`{% raw %}{{ post.date | date: "%d-%m-%Y  }}{% endraw %}` or `{% raw %}{{ post.date | date_to_long_string }}{% endraw %}`

<a id="excerpts"></a>
##### Post excerpts
Excerpts will show a defined snippet of a post, for example within an index of posts. This can be added to post loop using the following code,

`{% raw %}{{ post.excerpt }}{% endraw %}`

To set the end point for an excerpt, we simply add `<!--more-->` to the required cut-off point in our post. We can also override this auto-generated 
excerpt by setting `excerpt_separator` to `""` in the YAML Front Matter of a given post.

This generated excerpt can also be overridden by setting this  

<a id="pagination"></a>
##### Pagination
To enable pagination in Jekyll, for example with our lists of posts, we need to use the `paginator` option.

<a id="code"></a>
##### Code highlighting
Highlighting of code snippets is also supported in Jekyll using either *Pygments* or *Rouge*. Simply add the *Liquid* tag,

```
{% raw %}
{% highlight ruby %}
...
...
{% endhighlight %}
{% endraw %}
```

specifying your chosen language.

<a id="highlighting"></a>
##### Drafts
Within Jekyll, drafts are unfinished posts that do not yet include a date. They should be stored in the `_drafts` directory. These drafts can be 
previewed within a site by running the following command,

`jekyll build --drafts` or `jekyll serve --drafts`

This will build and render a current site, and populate posts with the current drafts. This allows a developer to test the rendering and layout of 
draft posts.
