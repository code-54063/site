---
title: Your first URL
category: django
order: 
permalink: "/django/your-first-url"
last_modified_at: "January 11, 2017"
---

Time to create our first URL! We want '<http://127.0.0.1:8000/>' to be the home page of our blog and to display a list of posts.

We also want to keep the `mysite/urls.py` file clean, so we will import URLs from our `blog`application to the main `mysite/urls.py` file.

Go ahead, add a line that will import `blog.urls`. Note that we are using the `include` function here so you will need to add that to the import on the first line of the file.

Your `mysite/urls.py` file should now look like this:

``` python
# mysite/urls.py
from django.conf.urls import include, url
from django.contrib import admin

urlpatterns = [url(r'^admin/', admin.site.urls), url(r'', include('blog.urls')),]
```

Django will now redirect everything that comes into `<http://127.0.0.1:8000/>` to `blog.urls` and look for further instructions there.

Writing regular expressions in Python is always done with`r` in front of the string. This is a helpful hint for Python that the string may contain special characters that are not meant for Python itself, but for the regular expression instead.

## blog.urls

Create a new empty file named `blog/urls.py`. All right! Add these first two lines:

``` python
# blog/urls.py
from django.conf.urls import url
from  import views
```

Here we're importing Django's function `url` and all of our `views` from the `blog` application. (We don't have any yet, but we will get to that in a minute!)

After that, we can add our first URL pattern:

``` python
# blog/urls.py
urlpatterns = [url(r'^$', views.post_list, name='post_list'),]
```

As you can see, we're now assigning a `view` called `post_list` to the `^$` URL. This regular expression will match `^` (a beginning) followed by `$` (an end) -- so only an empty string will match. That's correct, because in Django URL resolvers, `<http://127.0.0.1:8000/>` is not a part of the URL. This pattern will tell Django that `views.post_list` is the right place to go if someone enters your website at the `<http://127.0.0.1:8000/>` address.

The last part, `name='post_list'`, is the name of the URL that will be used to identify the view. This can be the same as the name of the view but it can also be something completely different. We will be using the named URLs later in the project, so it is important to name each URL in the app. We should also try to keep the names of URLs unique and easy to remember.

If you try to visit `<http://127.0.0.1:8000/>` now, then you'll find some sort of 'web page not available' message. This is because the server (remember typing `runserver`?) is no longer running. Take a look at your server console window to find out why.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-10-at-6.15.08-pm.jpg)

Your console is showing an error, but don't worry -- it's actually pretty useful: It's telling you that there is no attribute `post_list`. That's the name of the *view* that Django is trying to find and use, but we haven't created it yet. At this stage your `/admin/` will also not work. No worries -- we will get there.

If you want to know more about Django URLconfs, look at the [official documentation](https://docs.djangoproject.com/en/1.10/topics/http/urls/).
