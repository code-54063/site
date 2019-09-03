---
title: Setup your Django environment from the command line
category: django
order: 
permalink: "/django/anaconda-env-from-command-line"
last_modified_at: "September 1, 2019"
author: Francesco Bailo
---

You will need to enter these commands using **terminal** (Mac OSX) or **Anaconda Prompt** (Windows).


### 0. Before you start, it is suggested that you create a folder on your computer to store all the project files

The command to create a directory is `mkdir` followed by the name of your directory. After opening your terminal/prompt do

```
mkdir djangogirls
```

(`djangogirls` is the name used in dsmcode.com, but you can use whatever name you want!)

then move into the directory with

```
cd djangogirls
```


###  1. With the following command we are creating an environment called `djangoenv` specifying we want to install Python 3.6 

```
conda create -n djangoenv python=3.6
```

###  2. Activate your environment

```
conda activate djangoenv
```

Note: I get an error here (on a Mac, due to a [known issue](https://github.com/conda/conda/issues/7403)) and instead used `source activate djangoenv`.

### 3. Install Django (within your newly created environment)


```
conda install django
```

### 4. Install sqlparse (a required Python package)

```
conda install sqlparse 
```

### 5. Set up a Django project (in the current directory)

```
django-admin startproject website
```

You have now created all the files required by Django. Check what do you have with `ls` on Mac OSX or `dir` on Windows. I have two folders: `3.7` and `website`.

### 6. Launch your website

Move to the directory with the website file with

```
cd website
```

then, run your server

```
python manage.py runserver
```

I get this output

>Watching for file changes with StatReloader
>Performing system checks...
>
>System check identified no issues (0 silenced).
>
>You have 17 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
>Run 'python manage.py migrate' to apply them.
>
>August 31, 2019 - 22:41:45
>Django version 2.2.1, using settings 'website.settings'
>Starting development server at http://127.0.0.1:8000/
>Quit the server with CONTROL-C.

Now your server is running. Visit `http://127.0.0.1:8000/` with your web browser by copying/pasting it your address bar.

You should stop the server as soon as you close the terminal/prompt window.

## Possible issues

> CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.

then use `source activate djangoenv` instead of `conda activate djangoenv`. It worked for me.
