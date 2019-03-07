---
title: HTML structure
category: beautiful-soup
order: 
permalink: "/beautiful-soup/basics-get-familiar-with-html"
last_modified_at: "January 27, 2017"
---

# HTML structure 

While performing web scarping, we deal with html tags. Thus, we must have good understanding of them. If you already know basics of HTML, you can skip this section.

Below is the basic syntax of HTML:

``` xml
<!DOCTYPE html>

<html>

    <body>

	<h1>My First Heading</h1>

	<p>My first paragraph.</p>

</body>

</html>
```

This syntax has various tags as elaborated below:

1.  `\<!DOCTYPE html\> `: HTML documents must start with a type declaration
2.  HTML document is contained between `\<html\>` and `\</html\>`
3.  The visible part of the HTML document is between `\<body\>` and `\</body\>`
4.  HTML headings are defined with the `\<h1\>` to `\<h6\>` tags
5.  HTML paragraphs are defined with the `<p\>` tag

Other useful HTML tags are:

1.  HTML links are defined with the `\<a\>` tag:  `<a href=“http://www.test.com”>This  is a link for test.com</a>`
2.  HTML list starts with `<ul\>` (unordered) and `<ol\>` (ordered).  Each item of list starts with `<li\>`
3.  HTML tables are defined with`<Table\>`, row as `<tr\>` and rows are divided into data as `<td\>`

``` xml
<table style="width: 100%">
	<tr>
		<td>Jill </td>
		<td>Smith </td>
		<td>50 </td>
    </tr>
    <tr>
		<td>Eve </td>
		<td>Smith </td>
		<td>20 </td>
    </tr>
</table>
```

For more examples, read W3's [HTML tutorial](http://www.w3schools.com/html/).
