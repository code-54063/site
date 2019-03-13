---
title: Data scraping
category: beautiful-soup
order: 
permalink: "/beautiful-soup/data-scraping"
last_modified_at: "September 27, 2017"
---

Hey everyone,

Today we're going to do some basic data scraping with Python 3. This is a really powerful skill that allows you to scrape data from sites and do cool things with it.

We're going to be guided by some existing resources shared by Lisa Tagliaferri.

But first we need to create new virtual environments for a new project!

Go to your `C:/` (Windows) or Desktop (Mac) and create a folder called scraping then go into it.

```
mkdir scraping
cd scraping
```
 

Once you're in the folder, set up a new virtual environment. Go to our existing guide if you're
having trouble. Once you've done that set up
your environment.

**If you are having trouble doing this you can either troubleshoot individually (or as a group) or just look on to the person next to you. **

## Installing packages and modules in the virtual environment

Once you've entered your virtual environment install Pip, Beautiful Soup and Requests. Run each command **after** the previous install has finished:

``` 
python -m pip install --upgrade pip 
pip install BeautifulSoup4
pip install requests
```

Once you've done that, let's move on to [the introductory guide](https://www.digitalocean.com/community/tutorials/how-to-work-with-web-data-using-requests-and-beautiful-soup-with-python-3) that Lisa has prepared. We will start from the section, 'Collecting a Web Page with Requests'.

Once we've completed these basics, we'll start properly scraping data with the [formal tutorial](https://www.digitalocean.com/community/tutorials/how-to-scrape-web-pages-with-beautiful-soup-and-python-3).

**Important: In the formal tutorial, Lisa creates files using a program called nano. Instead of doing this, create a file using sublime text and save it in the scraping folder (e.g. c:/scraping). **
