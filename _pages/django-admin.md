---
title: Django Admin
category: django
order: 
permalink: "/django/admin"
last_modified_at: "2017-01-10-at-5.00.10-pm"
---

To add, edit and delete the posts we've just modeled, we will use Django admin.

Let's open the `blog/admin.py` file and replace its contents with this:

``` python
# blog/admin.py

from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

As you can see, we import (include) the Post model defined in the previous chapter. To make our model visible on the admin page, we need to register the model with `admin.site.register(Post)`.

OK, time to look at our Post model. Remember to run `python manage.py runserver` in the console to run the web server. Go to your browser and type the address <http://127.0.0.1:8000/admin/>. You will see a login page like this:

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-10-at-4.59.59-pm.jpg)

To log in, you need to create a *superuser* -- a user account that has control over everything on the site. Go back to the command line, type `python manage.py createsuperuser`, and press enter.

**Remember, to write new commands while the web server is running, open a new terminal window and activate your virtualenv. We reviewed how to write new commands in the Your first Django project! chapter, in the Starting the web server section.**

When prompted, type your username (lowercase, no spaces), email address, and password. Don't worry that you can't see the password you're typing in -- that's how it's supposed to be. Just type it in and press `enter` to continue. The output should look like this (where the username and email should be your own ones) after `manage.py createsuperuser`:


> (myvenv) ~/djangogirls$ python manage.py createsuperuser
> Username: admin
> Email address: admin@admin.com
> Password:
> Password (again):
> Superuser created successfully.

Return to your browser. Log in with the superuser's credentials you chose; you should see the Django admin dashboard.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-10-at-5.00.03-pm.jpg)

Go to Posts and experiment a little bit with it. Add five or six blog posts. Don't worry about the content -- you can simply copy-paste some text from this tutorial to save time. 🙂

Make sure that at least two or three posts (but not all) have the publish date set. It will be helpful later.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-10-at-5.00.10-pm.jpg)

If you want to know more about Django admin, you should check [Django's documentation](https://docs.djangoproject.com/en/1.10/ref/contrib/admin/).

You created your first Django model -- congratulations!
