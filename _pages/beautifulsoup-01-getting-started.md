---
title: Getting started
category: web-scraping-with-python
order: 1
permalink: "/web-scraping-with-python/getting-started"
last_modified_at: "July 15, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/web-scraping-with-python/beautifulsoup-01-getting-started.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

In this tutorial we will use a very popular Python package: [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/). If you plan to run the code on your own computer (see [Getting started with Anaconda](http://www.dsmcode.com/getting-started/anaconda)), you will need to install the package with 

```bash
# DON'T RUN this code from Jupyter!
conda install bs4
```

Instead if you want to run this code interactively using Jupyter Notebook and SWAN (see [Getting started with Jupyter](http://www.dsmcode.com/getting-started/jupyter-notebook)) you need to run the following cell at least once:


```python
# DON'T RUN this code from your computer!
import sys
!{sys.executable} -m pip install --user bs4
```

If you are using Jupyter, make sure you restart the Kernel after the installation with "Kernel" -> "Restart".

## Beautiful Soup: A working example

Let's now try to run the following example code to check that everything is properly installed on our computer or on Jupyter. The code is taken from the official documentation of the package (if you want have a look [here](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)). 

Let's first create a string variable called `html_doc` with some HTML code. 


```python
html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>

<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>

<p class="story">...</p>
"""
```

As you can appreciated, the HTML code is made of different tags identified by angle brackets `<` and `>`. The `title` item is open lby this tag: `<title>` and closed by this tag: `</title>`. Tags are disposed following a hierarchical structure; items are nested within other items. Now let's see what we can do with Beautiful Soup:


```python
from bs4 import BeautifulSoup
soup = BeautifulSoup(html_doc, 'html.parser')
```

In the first line of the previous cell, we import the Beautiful Soup module with `from bs4 import BeautifulSoup` (if you get an error here, it's because you haven't installed correctly the package, don't despair, share your problem [here](https://teams.microsoft.com/l/channel/19%3a769484749865406984d5d97a4bf7d25c%40thread.skype/Coding%2520issues?groupId=6b2b6609-a95b-40a2-8570-91455f3f78ba&tenantId=e8911c26-cf9f-4a9c-878e-527807be8791) by copying and pasting the error message you got).

In the second line `soup = BeautifulSoup(html_doc, 'html.parser')` we see `BeautifulSoup()` in action for the first time. This is the core function of the module and in this case takes our HTML document `html_doc` and *parse* it in its individual items, identified by the HTML tags.  

Once we have parse an HTML document, we can navigate the data structure simply like this:


```python
soup.title
```

Will print the `title` item (including the two tags). If we only want the strings framed by the opening and closing tag we can 


```python
soup.title.string
```

But obviously we can also do more interesting stuff. For example, if we want to find all items containing a hyperlink (framed by the `a` tags) we can


```python
soup.find_all('a')
```

which should return three items. Or if we are only interested in the actual string of the URL, we can loop through the object return by `find_all()`, which is a list with three (in this case) items, we can


```python
for link in soup.find_all('a'):
    print(link.get('href'))
```
## Exercise

How would print our the text contained in the three `<a>` tags?

```python
for ____ in soup.find_all('a'):
    print(____.string)
```
