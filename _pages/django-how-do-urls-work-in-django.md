---
title: How do URLs work in Django?
category: django
order: 
permalink: "/django/how-do-urls-work-in-django"
last_modified_at: "January 11, 2017"
---

Let's open up the `mysite/urls.py` file in your code editor of choice and see what it looks like:


``` python
# mysite/urls.py
"""mysite URL Configuration

[...]
"""
from django.conf.urls import url
from django.contrib import admin

urlpatterns = [url(r'^admin/', admin.site.urls),]
```

As you can see, Django has already put something here for us.

Lines between triple quotes (`'''` or `"""`) are called docstrings -- you can write them at the top of a file, class or method to describe what it does. They won't be run by Python.

The admin URL, which you visited in previous chapter, is already here:

``` python
# mysite/urls.py
url(r'^admin/', admin.site.urls),
```

This line means that for every URL that starts with `admin/`, Django will find a corresponding *view*. In this case we're including a lot of admin URLs so it isn't all packed into this small file -- it's more readable and cleaner.
