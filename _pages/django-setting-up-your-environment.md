---
title: Setting up your environment
category: django
order: 
permalink: "/django/setting-up-your-environment"
last_modified_at: "July 25, 2017"
---

## Virtual environment

Before we install Django we will get you to install an extremely useful tool to help keep your coding environment tidy on your computer. It's possible to skip this step, but it's highly recommended. Starting with the best possible setup will save you a lot of trouble in the future!

So, let's create a virtual environment (also called a *virtualenv*). Virtualenv will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing. Neat, right?

All you need to do is find a directory in which you want to create the `virtualenv`; your home directory, for example. On Windows it might look like `C:\Users\Name\` (where `Name` is the name of your login).

For Windows, the easiest thing to do is just make a new folder in your `C:/` through Windows Explorer. Mac users will make a directory through the set up process.

*This example uses 'djangogirls' to name it's directory but you might want to call it something more relevant like 'dsmcode'.*

Here, we'll use a package manager called `pip`. For more information, [see this page.](https://en.wikipedia.org/wiki/Pip_(package_manager)).
