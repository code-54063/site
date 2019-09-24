---
title: CSS : Make it pretty!
category: django
order: 
permalink: "/django/css"
last_modified_at: "September 13, 2018"
---

Our blog still looks pretty ugly, right? Time to make it nice! We will use CSS for that.

## What is CSS?

Cascading Style Sheets (CSS) is a language used for describing the look and formatting of a website written in a markup language (like HTML). Treat it as make-up for our web page. 😉

But we don't want to start from scratch again, right? Once more, we'll use something that programmers released on the Internet for free. Reinventing the wheel is no fun, you know.

## Let's use Bootstrap!

Bootstrap is one of the most popular HTML and CSS frameworks for developing beautiful websites: <https://getbootstrap.com/>

It was written by programmers who worked for Twitter. Now it's developed by volunteers from all over the world!

## Install Bootstrap

To install Bootstrap, open up your `.html` file in the code editor and add this to the `<head>` section:

``` html
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
```

This doesn't add any files to your project. It just points to files that exist on the Internet. So go ahead, open your website and refresh the page. Here it is!

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/bootstrap1.png)

Looking nicer already!
