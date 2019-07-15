---
title: Writing your scraping script
last_modified_at: "October 5, 2017"
--- 

Now that we know where our data is, we can start coding our web scraper. **Open your text editor now!**

First, we need to import all the libraries that we are going to use.

``` python
# import libraries
import urllib.request from bs4 import BeautifulSoup 
```

Next, declare a variable for the url of the page.

``` python
# specify the url
quote_page = 'http://www.bloomberg.com/quote/SPX:IND'
```

Then, make use of the **Python urllib2** to get the HTML page of the url declared.

``` python
# query the website and return the html to the variable 'page'
page = urllib.request.urlopen(quote_page)
``` 

Finally, parse the page into BeautifulSoup format so we can use **BeautifulSoup** to work on it

```
# parse the html using beautiful soap and store in variable `soup`
soup = BeautifulSoup(page, 'html.parser')
```

Now we have a variable `soup` containing the HTML of the page. Here's where we can start coding the part that extracts the data.

Remember the unique layers of our data? **BeautifulSoup** can help us get into these layers and extract the content out easily by using`find()`. In this case, since the HTML tag of name is very unique on this page, we can simple query `<div class="name">`

``` python
# Take out the <div> of name and get its value
name_box = soup.find('h1', attrs={'class': 'name'})
```

After we have the tag, we can get the data by getting its `text`.

``` python
name = name_box.text.strip() # strip() is used to remove starting and trailing  
print name
```

Similarly, we can get the price too.

``` python
# get the index price
price_box = soup.find('div', attrs={'class':'price'})
price = price_box.text
print price
```

When you run the program, you should be able to see that it prints out the current price of the S&P 500 Index in your command line.

If you run into trouble, here's one [I prepared earlier](../code/bs-bloomberg.py).
