---
title: Your first Django project!
category: django
order: 
permalink: "/django/your-first-project"
last_modified_at: "August 25, 2019"
---

We're going to create a simple blog!

The first step is to start a new Django project. Basically, this means that we'll run some scripts provided by Django that will create the skeleton of a Django project for us. This is just a bunch of directories and files that we will use later.

The names of some files and directories are very important for Django. You should not rename the files that we are about to create. Moving them to a different place is also not a good idea. Django needs to maintain a certain structure to be able to find important things.


Remember to run everything in the virtualenv or in your Anaconda environment. If you don't see a prefix `(myvenv)` (or whatever name you chose) in your console, you need to activate your environment. We explained how to do that [here](http://www.dsmcode.com/django/setting-up-your-environment#).

A quick recap:

1. You first need to create a directory for your project. Here we use `djangogirls`, but you can use whatever you want. From the command line you can use `mkdir djangogirls`.

2. Go the newly created folder.

3. Activate your environment ( see [here](http://www.dsmcode.com/django/setting-up-your-environment#) to create an environment). Here we call the environment `myvenv`. If you are using Anaconda type `source activate myvenv` if you are using virtualenv type  `myvenv\Scripts\activate` on Windows or `source myvenv/bin/activate` on Mac OS X or Linux will do this for you.

Now you can start Django!

## Start django

Run the following command. Don't forget to add the period (or dot) `.` at the end!

From your command-line
> (myvenv) ~/djangogirls$ django-admin startproject mysite .

The period `.` is crucial because it tells the script to install Django in your current directory (for which the period `.` is a short-hand reference).

Note: When typing the command above, remember that you only type the part which starts by `django-admin`. The `(myvenv) ~/djangogirls$` part shown here is just example of the prompt that will be inviting your input on your command line.

Check it to see what has been created by typing `ls` (on OSX) or `dir` (on Windows).
