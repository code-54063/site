---
title: Settings
category: django
order: 
permalink: "/django/settings"
last_modified_at: "May 12, 2017"
---

Let's make some changes in `mysite/settings.py`. Open the file using the code editor you installed earlier.

It would be nice to have the correct time on our website. Go to [Wikipedia's list of time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) and copy your relevant time zone (TZ) (e.g. `Europe/Berlin`).

**Hint:** Use Ctrl + F to find text in Sublime Text. You can also copy and paste into Sublime.

In `settings.py`, find the line that contains `TIME_ZONE` and modify it to choose your own timezone. For example:

``` python
# mysite/settings.py
TIME_ZONE = 'Europe/Berlin'
```

We'll also need to add a path for static files. (We'll find out all about static files and CSS later in the tutorial.) Go down to the *end* of the file, and just underneath the `STATIC_URL` entry, add a new one called `STATIC_ROOT`:

``` python
# mysite/settings.py
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```

When `DEBUG` is `True` and `ALLOWED_HOSTS` is empty, the host is validated against `['localhost', '127.0.0.1', '[::1]']`. This won't match our hostname on PythonAnywhere once we deploy our application so we will change the following setting:


``` python
# mysite/settings.py
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
```

Note: If you're using a Chromebook, add this line at the bottom of your settings.py file: `MESSAGE_STORAGE = 'django.contrib.messages.storage.session.SessionStorage'`.
