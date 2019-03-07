---
title: Understanding HTML
category: beautiful-soup
order: 3
permalink: "/beautiful-soup/understanding-html"
last_modified_at: "January 27, 2017"
---

Before we start jumping into the code, let's understand the basics of HTML and some rules of scraping.

## HTML tags

If you already know the basics of HTML tags, feel free to skip this part.

``` xml
<!DOCTYPE html>
<html>
	<head>
    </head>
	<body>
		<h1> First Scraping </h1>
        <p> Hello World </p>
    <body>
</html>
```

This is the basic syntax of a HTML webpage. Every `<tag>` serves a block inside the webpage:
1. `<!DOCTYPE html>`: HTML documents must start with a type declaration.
2. The HTML document is contained between `<html>` and `</html>`.
3. The meta and script declaration of the HTML document is between `<head>` and`</head>`.
4. The visible part of the HTML document is between `<body>` and `</body>`.
5. Title headings are defined with the `<h1>` to `<h6>` tags.
6. Paragraphs are defined with the `<p>` tag.

There are other useful tags like `<a>` for hyperlinks, `<table>` for tables, with `<tr>` for rows and `<td>` for columns.

Also, HTML tags sometimes come with `id` and `class` as attributes. The `id` attribute specifies a unique id for an HTML tag and the value must be unique within the HTML document. The `class` attribute is used to define equal styles for HTML tags with same class. We can make use of these ids and classes to help us locate the data we want.

For more information on HTML [tags](http://www.w3schools.com/html/), [id](http://www.w3schools.com/tags/att_global_id.asp) and [class](http://www.w3schools.com/html/html_classes.asp), please refer to [W3Schools Tutorials](http://www.w3schools.com/).

## Scraping Rules

1. You should check a website's **Terms and Conditions** before you scrape them. Be careful to read the statements about legal use of data, as usually, the data you scrape should not be used for commercial purposes.
2. Do not request data from the website too aggressively with your program (also known as spamming), as this may break the website. Make sure your program behaves in a reasonable manner (i.e. acts like a human), one request for one webpage per second is good practice.
3. The layout of a website may change from time to time, so make sure to revisit the site and rewrite your code as needed.

