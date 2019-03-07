---
title: Setting up your environment: Windows
category: django
order: 
permalink: "/django/setting-up-your-environment-windows"
last_modified_at: "July 25, 2017"
---

## Your username 

On Windows, make sure that this directory (which uses your username) does not contain accented or special characters (even just a space). If your Windows PC or **username** contains special characters, use a different directory, for example `C:\uts`.

## Get started


Firstly navigate to `C:/`

Then create a new directory with `mkdir djangogirls`

Then navigate to that folder

> C:\djangogirls

Once you're in the folder create a new virtualenv.

To create a new `virtualenv`, you need to open the command line and run `C:\Python35\python -m venv myvenv`. It will look like this:

where `C:\Python35\python` *is the directory in which you previously installed Python* and `myvenv`is the name of your `virtualenv`. You can use any other name, but stick to lowercase and use no spaces, accents or special characters. It is also good idea to keep the name short -- you'll be referencing it a lot!

*Please refer to command line basics for an introduction to navigating files using the command line.*
