---
title: Inspecting the page
category: beautiful-soup
order: 4
permalink: "/beautiful-soup/inspecting-the-page"
last_modified_at: "January 27, 2017"
---

## Looking into the HTML

Let's take one page from the [Bloomberg Quote](http://www.bloomberg.com/quote/SPX:IND) website as an example.

As someone following the stock market, we would like to get the index name (S&P 500) and its price from this page. First **right-click** and open your browser's **inspector** to inspect the webpage. A reminder, you'll need to be using Google Chrome for this part.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.37.12-pm.jpg)

Try hovering your cursor on the price and you should be able to see a blue box surrounding it. Click and the related HTML will be selected in the browser console.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.38.23-pm.jpg)

From the result, we can see that the price is inside a few levels of HTML tags, which is `<div class="basic-quote">` → `<div class="price-container up">` → `<div class="price">`.

Similarly, if you hover and click the name "S&P 500 Index", it is inside `<div class="basic-quote">` and `<h1 class="name">`.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-27-at-5.38.57-pm.jpg)

Now we know the unique location of our data with the help of `id` and `class` (though in this case, Bloomberg do not use `id`).
