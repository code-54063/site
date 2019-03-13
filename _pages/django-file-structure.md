---
title: File Structure
category: django
order: 
permalink: "/django/file-structure"
last_modified_at: "August 29, 2017"
---

`django-admin.py` is a script that will create the directories and files for you. You should now have a directory structure which looks like this:

```
    djangogirls
    ├───manage.py
    └───mysite
            settings.py
            urls.py
            wsgi.py
            __init__.py
```

`manage.py` is a script that helps with management of the site. With it we will be able (amongst other things) to start a web server on our computer without installing anything else.

The `settings.py` file contains the configuration of your website.

Remember when we talked about a mail carrier checking where to deliver a letter? `urls.py` file contains a list of patterns used by `urlresolver`.

Let's ignore the other files for now as we won't change them. The only thing to remember is not to delete them by accident!
