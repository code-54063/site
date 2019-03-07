---
title: Getting started
layout: default
category: beautiful-soup
order: 2
permalink: "/beautiful-soup/getting-started"
last_modified_at: "October 5, 2017"
---

# Getting started

Hey everyone,

Today we're going to do some basic data scraping with Python 3. This is a really powerful skill that allows you to scrape data from sites and do cool things with it.

But first we need to create new virtual environments for a new project!

Go to your `C:/` (Windows) or Desktop (Mac) and create a folder called scraping then go into it.

```
mkdir scraping
cd scraping
```

Once you're in the folder, set up a new virtual environment. Go to our [existing guide](setting-up-your-environment.html) if you're having trouble. Once you've done that [set up your environment](working-with-virtualenv.html).

**If you are having trouble doing this you can either troubleshoot individually (or as a group) or just look on to the person next to you.**

## Installing packages and modules in the virtual environment

Once you've entered your virtual environment install Pip, Beautiful Soup and Requests. Run each command **after** the previous install has finished:

```
python3 -m pip install --upgrade pip
python3 -m pip install BeautifulSoup4
python3 -m pip install requests
```

