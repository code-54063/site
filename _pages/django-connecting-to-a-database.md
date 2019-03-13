---
title: Connecting a database
category: django
order: 
permalink: "/django/connecting-a-database"
last_modified_at: "January 11, 2017"
---

There's a lot of different database software that can store data for your site. We'll use the default one, `sqlite3`.

This is already set up in this part of your `mysite/settings.py` file:

``` python
# mysite/settings.py
DATABASES = {
	'default': {
	'ENGINE': 'django.db.backends.sqlite3',
	'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
	}
}
```

To create a database for our blog, let's run the following in the console: `python manage.py migrate` (we need to be in the `djangogirls` directory that contains the `manage.py` file). If that goes well, you should see something like this:

From the command-line

> (myvenv) ~/djangogirls$ python manage.py migrate
> Operations to perform:
> Apply all migrations: auth, admin, contenttypes, sessions
> Running migrations:
> Rendering model states... DONE
> Applying contenttypes.0001_initial... OK
> Applying auth.0001_initial... OK
> Applying admin.0001_initial... OK
> Applying admin.0002_logentry_remove_auto_add... OK
> Applying contenttypes.0002_remove_content_type_name... OK
> Applying auth.0002_alter_permission_name_max_length... OK
> Applying auth.0003_alter_user_email_max_length... OK
> Applying auth.0004_alter_user_username_opts... OK
> Applying auth.0005_alter_user_last_login_null... OK
> Applying auth.0006_require_contenttypes_0002... OK
> Applying auth.0007_alter_validators_add_error_messages... OK
> Applying sessions.0001_initial... OK

And we're done! Time to start the web server and see if our website is working!
