---
title: D3 Data Basic
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev javascript d3
year: 2015
month: 03
day: 31
published: true
summary: a brief overview of data usage in D3
menu: d3-data-basic
---

A brief introduction to the basic concepts of working with data in the [D3](http://d3js.org) Javascript library.

***

Contents |
--------------|
[Introduction](#intro) |
[Enter-Update-Exit pattern](#eue-pattern) |
[Binding an array as data](#binding-array) |
[Binding object literals as data](#binding-object) |
[Binding functions as data](#binding-functions) |
[Working with arrays](#arrays) |

***

<a id="intro"></a>
##### Introduction
When we consider data relative to D3, we need to know how data can be represented both in programming constructs and its associated visual metaphor.

So, as a brief segue, what is the basic difference between data and information,

*"Data are raw facts. The word raw indicates that the facts have not yet been processed to reveal their meaning...Information is the result of processing raw data to reveal its meaning."*

(*Rob, Morris, and Coronel. 2009*)


However, this is the general concept of data and information. If we consider them relative to visualisation, we necessarily impart a richer interpretation. Information, in this context, is no longer the simple result of processed raw data or facts. Instead, it becomes a visual metaphor of the facts.

The same data set can generate any number of visualisations. These may lay equal claim in terms of its validity. In effect, visualisation becomes more about communicating the creator's insight into data than anything else. 
<a id="eue-pattern"></a>
##### Enter-Update-Exit Pattern
In D3, the connection between data and its visual representation is usually referred to as the **enter-update-exit** pattern.

This concept is starkly different from the standard imperative programming style.

###### Enter mode
The *enter()* function returns all of the specified data that has not yet been represented in the visual domain. This standard modifier function can then be chained to a selection method to create new visual elements representing the given data elements.

ie: we can keep updating the array, and outputting the new data bound to elements.

###### Update mode
*selection.data(data)* function, on a given selection, establishes the connection between the data domain and the visual domain. The returned result of this intersection of data and visual will be a *data-bound* selection. We can now invoke a modifier function on this newly created selection to update all existing elements. This is what we mean by an *update* mode.

ie: as soon as this connection is established we can update the selections in many different ways.

###### Exit mode
If we invoke *selection.data(data).exit* function on a data-bound selection, the function will compute a new selection which contains all visual elements that are no longer associated with any valid data element. 

For example, if we created a bar chart with 25 data points, and then updated it to 20, we would now have 5 left over. With this *exit mode*, we can now remove the excess elements for the 5 spare data points.

<a id="binding-array"></a>
##### Binding an array as data
Whilst we can iterate through the array, and then bind the data to an element, the most common option in D3 is to use the *enter-update-exit* pattern.

<a id="binding-object"></a>
##### Binding object literals as data
Same basic methodology as an array, except our array is now filled with objects. So, to access our data we call the required attribute of the supplied data. For example,

```
var data = [
	{height: 10, width: 20},
	{height: 15, width: 25}
];

function (d) {
	return (d.width) + "px";
}
```

We can obviously access the *height* attribute per object in the same manner.

<a id="binding-functions"></a>
##### Binding functions as data
D3 allows functions to be treated as data as well. This allows us to create data dynamically, or modify existing data before being bound to elements, and so on. There is a lot we can do if we consider data as a function, and vice-versa.

<a id="arrays"></a>
##### Working with arrays
D3 provides a particularly rich set of functions and utilities for working with arrays, which makes the task of manipulating array data considerably easier.

A few of the options are as follows,

* min and max = return the min and max values in the passed array

```
d3.select("#output").text(d3.min(ourArray));
d3.select("#output").text(d3.max(ourArray));
```

* extent = retrieves both the smallest and largest values in the the passed array

```
d3.select("#output").text(d3.extent(ourArray));
```

* sum

```
d3.select("#output").text(d3.sum(ourArray));
```

* median

```
d3.select("#output").text(d3.median(ourArray));
```

* mean 

```
d3.select("#output").text(d3.mean(ourArray));
```

* asc and desc

```
d3.select("#output").text(ourArray.sort(d3.ascending));
d3.select("#output").text(ourArray.sort(d3.descending));
```

* quantile

```
d3.select("#output").text(
	d3.quantile(ourArray.sort(d3.ascending), 0.25)
);
```

* bisect

```
d3.select("#output").text (
	d3.bisect(ourArray.sort(d3.ascending), 6)
);
```

* nest

D3's nest function can be used to build an algorithm to transform a flat array data structure into a hierarchical nested structure. This function can be configured using the key function chained to *nest*.

In effect, nesting allows elements in an array to be grouped into a hierarchical tree structure. It's similar in concept to the *group by* option in SQL. The main difference is that *nest* in D3 allows multiple levels of grouping and, of course, the result is a tree rather than a flat table.

The levels in the tree are defined by the *key* function, and the leaf nodes of the tree can be sorted by value. The internal nodes of the tree can be sorted by key.