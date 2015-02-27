---
title: Git Commands
author: ancientlives
layout: post-vertical

categories:
- library
- notes

tags: library notes dev git
year: 2015
month: 02
day: 27
published: true
summary: some useful Git commands
menu: git-commands
---

A collection of useful commands for the version control software [Git](http://git-scm.com).

***

Contents |
-----------|
[Introduction](#intro) |
[Basic](#basic) |
[Fork](#fork) |

***

<a id="intro"></a>
##### Introduction
These commands are not meant as an exhaustive list but simply reference for regular use.

<a id="basic"></a>
##### Basic
* clone a repository
	
```
git clone https://repositoryurl
```

* add files from local repository

```
git add *
```

* commit changes with message

```
git commit -m "your commit message..."
```

* push changes to specified branch

```
git push -u origin master
```

* delete a directory from repository

```
git rm -r directory_name
```

* reset git after unwanted add, commit etc

```
git reset
```

* status update relative to current repository

```
git status
```

<a id="fork"></a>
##### Fork - GitHub Repository
* Fork a chosen repository on GitHub to your user account
* Clone forked repository on your remote account to a local copy
* configure `git` to sync with the original forked repo
  * cd to local cloned copy of forked repo
  * check the current configured remote repository for your fork.
  
```
git remote -v
```
  
  * set the new upstream repository for the defined fork
  
```
git remote add upstream https://github.com/user_account/original_forked_repo...
```
  
  * then verify new upstream directory

```
git remote -v
```

* fetch the branches and commits from the remote repository
  * create a new local branch @ upstream/master

```
git fetch upstream
```

  * merge changes from upstream/master into local master branch

```
git merge upstream/master
```

* ensure up-to-date remote copy on your own forked repository

```
git pull
```

* show current local working branch

```
git branch
```
