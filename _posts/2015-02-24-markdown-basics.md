---
title: Markdown Basics
author: ancientlives
layout: post-vertical

categories:
- library
- notes

tags: library notes dev markdown
year: 2015
month: 02
day: 24
published: true
summary: an overview of Markdown basics
menu: markdown-basics
---

An overview of the basic syntax for Markdown. 

***

Contents |
-----------|
[Introduction](#intro) |
[Basic Writing](#toc-bw) |
[Headings](#toc-headings) |
[Lists](#toc-lists) |
[Code Formatting](#toc-cf) |
[Links](#toc-links) |

***

<a id="intro"></a>
##### Introduction
Markdown was created to be easy to read, write, and publish.

Markdown is simply a text-to-HTML conversion tool for online, web writers. It allows writers to format their 
plain text documents with a simple syntax, and then convert it to structurally valid XHTML (or HTML4 if required).
Further details can be found at the following site,

  * [Daring Fireball](http://daringfireball.net/projects/markdown/)

<a id="toc-bw"></a>
#### Basic-Writing

##### Paragraphs
No specific syntax in Markdown for paragraphs. They are simply one or more lines of consecutive text, which 
is followed by one or more blank lines.

<a id="toc-headings"></a>
#### Headings
Following the example of HTML syntax, Markdown permits headings equivalent to h1 through h6.
A simple hash character `#` is used to indicate the heading number, incrementing from one to six.
This is equivalent to h1 through h6 in HTML.

* Blockquotes

Markdown indicates blockquotes with a greater than sign `>`

* Styling Text

Text can be marked as bold or italic. A single asterisk or underscore marks italic markup, and 
a set of double asterisks or underscores marks bold markup.

<a id="toc-lists"></a>
#### Lists

* Unordered lists

Unordered lists can be written using either a single asterisk or dash preceding the list item.

* Ordered lists

Simply precede list items with the required, ordered number.

* Nested lists

List items can be nested by indenting each list item by two spaces.

<a id="toc-cf"></a>
#### Code Formatting

* Inline formats

Markdown syntax allows code etc to be marked without processing. To mark any special text, simply
use a single backtick (`) to wrap the special text.

* Multiple lines

You can also format multiple lines as a distinct block of text by wrapping in
triple backticks (```).

<a id="toc-links"></a>
#### Links
Links in Markdown are created as a pair indicating link title and link reference.
The link title is wrapped in brackets `[]`, and the link reference is in parenthesis `()`.
