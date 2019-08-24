---
title: Setting up your environment
category: django
order: 
permalink: "/django/setting-up-your-environment"
last_modified_at: "August 25, 2019"
---

## Virtual environment

Before we install Django we will get you to install an extremely useful tool to help keep your **coding environment** tidy on your computer. It's possible to skip this step, but it's highly recommended. Starting with the best possible setup will save you a lot of trouble in the future!

You can create your environment in Anaconda (recommended if you are using Anaconda) o with *virtualenv*.

### Managing environments with Anaconda

Creating a new environment in Anaconda is very easy. Just open the Anaconda Navigator.

![anaconda-navigator-environments-1](https://cloudstor.aarnet.edu.au/plus/s/BkIshsGzQq6QPKy/download)

#### Creating an environment 

1. At the bottom of the environments list, click the "Create" button.
2. In the Create Environment dialog box, type a descriptive name for your new environment.
3. Select "Python" and choose a Python version (just do not choose Python 2!).
4. Click the Create button.

#### Installing optional packages

Your new environment will already have a few essential packages installed. Probably, Django is not among them. To install Django in you environment you will need to

1. Select your environment, which in the example is named "my-environment"
2. Select in the right-hand pannel the list of "Non-installed" packages.
3. The list is long so you can simply enter "Django" in the search box.

![anaconda-navigator-environments-2](https://cloudstor.aarnet.edu.au/plus/s/61RTBMsmtlE1fXJ/download)

4. Click on the little box on the right of the package name to show a green down arrow.
5. Click on "Apply".

![anaconda-navigator-environments-3]https://cloudstor.aarnet.edu.au/plus/s/61RTBMsmtlE1fXJ/download)

6. Possibly, you will need to click "Apply" a second time on a popup that will inform you of the list of packages you are going to install.

Your package is now installed!

#### Using an environment

If you go back to your Anaconda Navigator "Home", you will see that your new environment is available. Just select it, reinstall the application that you plan to use (maybe Spyder?) and launch it.

![anaconda-navigator-environments-4](https://cloudstor.aarnet.edu.au/plus/s/rd64ZlxYJZUC6gF/download)


### Creating environments with virtualenv

So, let's create a virtual environment (also called a *virtualenv*). Virtualenv will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing. Neat, right?

All you need to do is find a directory in which you want to create the `virtualenv`; your home directory, for example. On Windows it might look like `C:\Users\Name\` (where `Name` is the name of your login).

For Windows, the easiest thing to do is just make a new folder in your `C:/` through Windows Explorer. Mac users will make a directory through the set up process.

*This example uses 'djangogirls' to name it's directory but you might want to call it something more relevant like 'dsmcode'.*

Here, we'll use a package manager called `pip`. For more information, [see this page.](https://en.wikipedia.org/wiki/Pip_(package_manager)).

#### Setting up your environment: OSX

*Please refer to command line basics for an introduction to navigating files using the command line.*

Open up your terminal (for example, press Apple Key + Space and type `terminal`).

Find out where your terminal is located by typing `ls`.

Go to your Desktop by entering `cd Desktop`.

Create a folder by typing `mkdir djangogirls`.

Look at your desktop- is the folder there?

Enter the folder: `cd djangogirls`.

Firstly, install virtualenv: `pip install virtualenv`.

Check that it installed by running: `virtualenv --version`.

In this location, create a virtual environment (the folder will be called `myvenv`): `python3 -m venv myvenv`.

#### Setting up your environment: Windows

##### Your username 

On Windows, make sure that this directory (which uses your username) does not contain accented or special characters (even just a space). If your Windows PC or **username** contains special characters, use a different directory, for example `C:\uts`.

#### Get started

Firstly navigate to `C:/`

Then create a new directory with `mkdir djangogirls`

Then navigate to that folder

> C:\djangogirls

Once you're in the folder create a new virtualenv.

To create a new `virtualenv`, you need to open the command line and run `C:\Python35\python -m venv myvenv`. It will look like this:

where `C:\Python35\python` *is the directory in which you previously installed Python* and `myvenv`is the name of your `virtualenv`. You can use any other name, but stick to lowercase and use no spaces, accents or special characters. It is also good idea to keep the name short -- you'll be referencing it a lot!

*Please refer to command line basics for an introduction to navigating files using the command line.*


