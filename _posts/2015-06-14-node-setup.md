---
title: Node.js Setup
author: ancientlives
layout: library-article-vertical

categories:
- library
- notes

tags: library notes dev javascript node
year: 2015
month: 06
day: 14
published: true
summary: a brief introduction to node.js setup
menu: node-intro
---

Some brief notes on install, configuring, and running basic node.js.

***

Contents |
-------------------------|
[Introduction](#intro) |
[Install node.js - Linux](#install) |
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Distro-stable version](#distro) |
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[cURL and GitHub](#curl) |
[Install node.js - Mac OS X](#osx) |
[Install Express](#installexpress) |
[Using Express](#usingexpress) |

***

<a id="intro"></a>
##### Introduction
There are a number of different ways to install *node.js*, *npm*, and the lightweight web server *express*.

<a id="install"></a>
##### Install node.js - Linux
To install node.js we can use a distro-stable version, cURL, and GitHub.

<a id="distro"></a>
###### Distro-stable version
There is a version of node.js in the default repositories of Ubuntu 14.04. It will not be the latest version, but it will make it easier to provision a consistent experience across multiple servers. It should also be quite stable for day to day use.

```
sudo apt-get update
sudo apt-get install nodejs
```

You should also install *npm*

```
sudo apt-get install npm
```

*NB:* the executable will be *nodejs* instead of the customary *node*. This is due to a conflict with another package.

<a id="curl"></a>
###### cURL and Git
An alternative, and more recent version, can be installed from GitHub.

Check that *curl* and *git* are installed,

```
sudo apt-get install curl git
```

Then run the following script to install *NVM*,

```
curl https://raw.githubusercontent.com/creationix/nvm/v0.20.0/install.sh | bash
```

*NB:*you'll need to modify *v.0.20.0* to match the latest version.
*NB:*you'll also need to logut of *ssh* and then reconnect before continuing.

Further details can be found at the [NVM GitHub Repository](https://github.com/creationix/nvm).

You can then use *nvm* (Node Version Manager) to install and maintain node.js. For example,

```
nvm install 0.10.33
```

will install that version of node.js. It's also possible to install by branch,

```
nvm install stable
```

and so on.

<a id="osx"></a>
##### Install node.js - Mac OS X

To run and test node.js on a local Mac OS X machine, simply download and install the following file,

  * [NodeJS - Mac OS X](https://nodejs.org/download/)

<a id="installexpress"></a>
##### Install Express
Express is a framework for web applications built upon node.js, and is minimal and flexible.

We can use *npm* to install the *express* module. The `-g` option set a Express to global instead of a limited local install.

```
npm install -g express
```

This installs the *express* command line tool, which allows us to start building our basic web application. It is now 
also necessary to install the *Express* application generator,

```
npm install -g express-generator
```

<a id="usingexpress"></a>
##### Using express
We can now use *express* to start building our initial basic web application.

Express creates a basic shell for our web application with the following command,

```
express /node/test-project
```

This command makes a new directory, and populates with the required basic web application directories and files.

We then cd to this directory and install any required dependencies,

```
npm install
```

We can then run our new app,

```
npm start
```



