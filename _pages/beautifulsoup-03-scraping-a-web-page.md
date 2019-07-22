---
title: Scraping a web page
category: web-scraping-with-python
permalink: "/web-scraping-with-python/scraping-a-web-page"
last_modified_at: "July 15, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/web-scraping-with-python/beautifulsoup-03-scraping-a-web-page.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 


## 1. Import necessary libraries


```python
#import the libraries used to query a website
from bs4 import BeautifulSoup
import urllib.request

#specify the url
wiki = "https://en.wikipedia.org/wiki/List_of_state_and_union_territory_capitals_in_India"

#Query the website and return the html to the variable 'page'
page = urllib.request.urlopen(wiki)

#import the Beautiful soup functions to parse the data returned from the website
from bs4 import BeautifulSoup

#Parse the html in the 'page' variable, and store it in Beautiful Soup format
soup = BeautifulSoup(page)
```

## 2. Use function "prettify" to look at nested structure of HTML page


```python
print(soup.prettify())
```

Here you will see the structure of the HTML tags. This will help you to know about different available tags and how can you play with these to extract information.

## 3.  Work with HTML tags

a. `soup.<tag>`: Return content between opening and closing tag including tag.


```python
soup.title
```

b. `soup.<tag>.string`: Return string within given tag


```python
soup.title.string
```

c. Find all the links within page's `<a>` tags: We know that, we can tag a link using tag `<a>`. So, we should go with option `soup.a` and it should return the links available in the web page. Let's do it.


```python
soup.a
```

Above, you can see that, we have only one output. Now to extract all the links within `<a\>`, we will use `find_all()`. Doing this will show all links including titles, links and other information.

To show only links, we need to iterate over each a tag and then return the link using attribute "href" with get.

## 4. Find the right table

As we are seeking a table to extract information about state capitals, we should identify the right table first. Let's write the command to extract information within all `table` tags.


```python
all_tables = soup.find_all('table')
```

Now to identify the right table, we will use attribute "class" of table and use it to filter the right table. In chrome, you can check the class name by right click on the required table of web page, then "Inspect element", and "Copy" the class name OR go through the output of above command find the class name of right table.


```python
right_table = soup.find('table', attrs={'class':'wikitable sortable plainrowheaders'})
right_table
```

Above, we are able to identify the right table.

## 5. Extract the information to DataFrame

Here, we need to iterate through each row (`tr`) and then assign each element of `tr` (`td`) to a variable and append it to a list. Let's first look at the HTML structure of the table (I am not going to extract information for table heading `<th>`)

Above, you can notice that second element of `<tr>` is within tag `<th>` not `<td>` so we need to take care for this. Now to access value of each element, we will use `find(text=True)` option with each element.  Let's look at the code:


```python
#Generate lists
A=[]
B=[]
C=[]
D=[]
E=[]
F=[]
G=[]
for row in right_table.findAll("tr"):
    cells = row.findAll('td')
    states=row.findAll('th') #To store second column data
    if len(cells)==6: #Only extract table body not heading
        A.append(cells[0].find(text=True))
        B.append(states[0].find(text=True))
        C.append(cells[1].find(text=True))
        D.append(cells[2].find(text=True))
        E.append(cells[3].find(text=True))
        F.append(cells[4].find(text=True))
        G.append(cells[5].find(text=True))

#import pandas to convert list to data frame
import pandas as pd
df=pd.DataFrame(A,columns=['Number'])
df['State/UT']=B
df['Admin_Capital']=C
df['Legislative_Capital']=D
df['Judiciary_Capital']=E
df['Year_Capital']=F
df['Former_Capital']=G
df
```
