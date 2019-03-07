---
title: Extracting the data
category: beautiful-soup
order:
permalink: "/beautiful-soup/extracting-the-data"
last_modified_at: " January 27, 2017"
---

### Extract the information to DataFrame

Here, we need to iterate through each row (`tr`) and then assign each element of `tr` (`td`) to a variable and append it to a list. Let's first look at the HTML structure of the table (I am not going to extract information for table heading `<th/>`)


<img src="{{ site.baseurl }}/img/2017-01-27-at-5.20.11-pm.jpg" max-width: 100%>

Above, you can notice that second element of `<tr\>` is within tag `<th\>` not `<td\>` so we need to take care for this. Now to access value of each element, we will use `find(text=True)` option with each element.  Let's look at the code:

``` python
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
