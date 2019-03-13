---
title: URLs
category: django
order: 
permalink: "/django/urls"
last_modified_at: "May 17, 2017"
---

We're about to build our first webpage: a homepage for your blog! But first, let's learn a little bit about Django URLs.

## What is a URL?

A URL is simply a web address. You can see a URL every time you visit a website -- it is visible in your browser's address bar. (Yes! `127.0.0.1:8000` is a URL! And `https://dsmcode.com` is also a URL.)

Every page on the Internet needs its own URL. This way your application knows what it should show to a user who opens that URL. In Django we use something called `URLconf` (URL configuration). URLconf is a set of patterns that Django will try to match with the requested URL to find the correct view.
