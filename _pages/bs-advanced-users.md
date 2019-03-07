---
title: Advanced users
category: beautiful-soup
order: 7
permalink: "/beautiful-soup/advanced-users"
last_modified_at: "January 27, 2017"
toc: true
---

## Multiple indexes to scrape?

So scraping one index is not enough for you, right? We can try to extract multiple indices at the same time. First, modify the `quote_page` into an array of URLs.

```
quote_page = ['http://www.bloomberg.com/quote/SPX:IND', 'http://www.bloomberg.com/quote/CCMP:IND']  
```

Then we change the data extraction code into a 'for loop', which will process the URLs one by one and store all the data into a variable `data` in tuples.

``` python
data = []

# for loop
for pg in quote_page:

# query the website and return the html to the variable 'page'
    page = urllib2.urlopen(pg)

# parse the html using beautiful soap and store in variable `soup`
    soup = BeautifulSoup(page, 'html.parser')

# Take out the <div> of name and get its value
    name_box = soup.find('h1', attrs={'class': 'name'})
    name = name_box.text.strip() # strip() is used to remove starting and trailing

# get the index price
    price_box = soup.find('div', attrs={'class':'price'})
    price = price_box.text

# save the data in tuple
    data.append((name, price))
```

Also, modify the saving section to save data row by row.

``` python
# open a csv file with append, so old data will not be erased
with open('index.csv', 'a') as csv_file:
	writer = csv.writer(csv_file)
# The for loop
	for name, price in data:
		writer.writerow([name, price, datetime.now()])
```

Rerun the program and you should be able to extract two indices at the same time!
