---
title: Writing your scrape script
category: web-scraping-with-python
permalink: "/web-scraping-with-python/writing-your-scrape-script"
last_modified_at: "July 15, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/web-scraping-with-python/beautifulsoup-02-writing-your-scrape-script.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 


Now that we know where our data is, we can start coding our web scraper. You can follow this tutorial either in Jupyter or by executing the code on your own computer.

First, we need to import all the libraries that we are going to use.


```python
from bs4 import BeautifulSoup
import urllib.request
```

If you get an error, make sure you have:
1. Correctly installed `BeautifulSoup`: see [here](http://www.dsmcode.com/web-scraping-with-python/getting-started),
2. Restarted the Kernel after completing the installation with "Kernel" -> "Restart".

Next, declare a variable for the url of the page of Apocalypse Now on the *Internet Movie Database* (IMDb).


```python
# specify the url
imdb_page = 'https://www.imdb.com/title/tt0078788/'
```

Then, make use of the **Python urllib** to get the HTML page of the url declared.


```python
# query the website and return the html to the variable 'page'
page = urllib.request.urlopen(imdb_page)
```

Finally, parse the page into BeautifulSoup format so we can use `BeautifulSoup()` to work on it


```python
# parse the html using beautiful soap and store in variable `soup`
soup = BeautifulSoup(page, 'html.parser')
```

Now we have a variable `soup` containing the HTML of the page. Here's where we can start coding the part that extracts the data.

Remember the unique layers of our data? `BeautifulSoup()` can help us get into these layers and extract the content out easily by using `find()`. In this case, since the HTML tag containing the title of the movie (`h1`) is very unique on this page, we can simple query `<h1>`:

![](https://cloudstor.aarnet.edu.au/plus/s/kwhmcCROYRayye5/download)


```python
# Take out the <div> of name and get its value
movie_title = soup.find('h1')
```

After we have the tag, we can get the data by getting its `text`.


```python
movie_title = movie_title.text.strip() # strip() is used to remove starting and trailing  
print(movie_title)
```

Similarly, we can get the movie score too. Still, in this case we want to be more precise, instead of just searching for the the tag `span`, we also want to specifiy that the attribute `itemprop` has value `ratingValue`. 
![](https://cloudstor.aarnet.edu.au/plus/s/1tGYxebthzgTjHd/download)


```python
# get the score
score_box = soup.find('span', attrs={'itemprop':'ratingValue'})
score = score_box.text
print(score)
```

## Exercise

How would you get the duration of the movie?

![](https://cloudstor.aarnet.edu.au/plus/s/WaqoM0wrJtlMHQ2/download)


```python
duration_box = soup.find('_____')
duration = duration_box._____.strip()
print(score)
```
