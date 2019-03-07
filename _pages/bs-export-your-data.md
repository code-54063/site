---
title: Export your data 
layout: default
category: beautiful-soup
order: 6
permalink: "/beautiful-soup/export-your-data"
---


# Export your data

## Export to Excel CSV

Now that we have the data, it is time to save it. The Excel Comma Separated Format is a nice choice, as it can be opened in Excel so you can see the data and process it easily.

But first, we have to import the **Python csv module** and the **datetime module** to get the record date. Insert these lines to your code in the import section.

``` python
import csv
from datetime import datetime
```

At the bottom of your code, add the code for writing data to a csv file.

``` python
# open a csv file with append, so old data will not be erased
with open('index.csv', 'a') as csv_file:
	writer = csv.writer(csv_file)
	writer.writerow([name, price, datetime.now()])
```

Now if you run your program, you should able to export a `index.csv` file, which you can then open with Excel, where you should see a line of data.

Here is the [code if needed](../code/bs-bloomberg.py).

Updated on October 5, 2017
