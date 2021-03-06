---
title: React Intro
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev javascript react
year: 2015
month: 06
day: 14
published: true
summary: a brief introduction to React
menu: react-intro
---

A quick introduction to the React JavaScript library. Further details are available at the [React](http://facebook.github.io/react/) website.

***

Contents |
-------------------------|
[Overview](#overview) |
[Speed](#speed) |
[State changes](#state) |
[Benefits](#benefits) |

***

<a id="overview"></a>
##### Overview
**React** began life as a port of a custom PHP framework called XHP, which was developed internally at Facebook. XHP, as a PHP framework, was designed to render the full page for each request. **React** developed from this concept, thereby creating a client-side implementation of loading the full page.

**React** can, therefore, be perceived as a type of *state machine*, thereby allowing a developer to control and manage the inherent complexity of state as it changes over time. It is able to achieve this by concentrating on a narrow scope for development,

* maintaining and updating the DOM
* responding to events

**React** is best perceived as a *view* library, and has no definite requirements or restrictions on storage, data structure, routing, and so on. This allows developers the freedom to incorporate **React** code into a broad scope of applications and frameworks.

<a id="speed"></a>
##### Speed
**React** leverages its built-in, powerful rendering system to produce quick, responsive rendering of the DOM in response to received state changes. It uses a virtual DOM, which enables **React** to maintain and update the DOM without the lag of reading it as well.

<a id="state"></a>
##### State Changes
As **React** is informed of a state change, it re-runs render functions. This enables it to determine a new representation of the page in its virtual DOM. This is then automatically translated into the necessary changes for the new DOM, which is reflected in the new rendering of the view. 

This may, at first glance, appear inherently slow. However, **React** uses an efficient algorithm to check and determine the differences between the current page in the virtual DOM and the new virtual one. From these differences it makes the minimal set of necessary updates to the rendered DOM.

This creates speed benefits and gains as it minimises the usual reflows and DOM manipulations. It also minimises the effect of cascading updates caused by frequent DOM changes and updates.

<a id="benefits"></a>
##### Benefits
One of the main benefits of this virtual approach is the avoidance of micro-managing any updates to the DOM. Instead, a developer simply informs **React** of any changes, such as user input, and it is able to process those passed changes and updates. 

**React** has the inherent benefit of delegating all events to a single event handler, which naturally gives **React** an associated performance boost.