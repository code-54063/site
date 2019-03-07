---
title: Models
category: django
order: 
permalink: "/django/models"
last_modified_at: "January 11, 2017"
---

Knowing what an object is, we can create a Django model for our blog post.

A model in Django is a special kind of object -- it is saved in the `database`. A database is a collection of data. This is a place in which you will store information about users, your blog posts, etc. We will be using a SQLite database to store our data. This is the default Django database adapter -- it'll be enough for us right now.

You can think of a model in the database as a spreadsheet with columns (fields) and rows (data).
