---
title: Inspecting the page
category: web-scraping-with-python
permalink: "/web-scraping-with-python/inspecting-the-page"
last_modified_at: "July 15, 2018"
---

## Looking into the HTML

Let's take one page from the [Bloomberg Quote](http://www.bloomberg.com/quote/SPX:IND) website as an example.

As someone following the stock market, we would like to get the index name (S&P 500) and its price from this page. First **right-click** and open your browser's **inspector** to inspect the webpage. A reminder, we'll be using Google Chrome in this part but you can also get the same page structure information with other browsers.

* Firefox: Right-click and *Inspect Element*
* Chrome: Right-click and *Inspect*
* Safari: 
  1. Enable "Show Developer Menu" in Safari's Preferences, *Advanced tab*.
  2. Right-click and *Inspect Element*

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.37.12-pm.jpg)

Try hovering your cursor on the price and you should be able to see a blue box surrounding it. Click and the related HTML will be selected in the browser console.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.38.23-pm.jpg)

From the result, we can see that the price is inside a few levels of HTML tags, which is `<div class="basic-quote">` → `<div class="price-container up">` → `<div class="price">`.

Similarly, if you hover and click the name "S&P 500 Index", it is inside `<div class="basic-quote">` and `<h1 class="name">`.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.38.57-pm.jpg)

Now we know the unique location of our data with the help of `id` and `class` (though in this case, Bloomberg do not use `id`).
