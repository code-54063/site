---
title: Create tables for models in your database
category: django
order: 
permalink: "/django/create-tables-for-models-in-your-database"
last_modified_at: "August 29, 2017"
---

The last step here is to add our new model to our database. First we have to make Django know that we have some changes in our model. (We have just created it!) Go to your console window and type `python manage.py makemigrations blog`. It will look like this:

> (myvenv) ~/djangogirls$ python manage.py makemigrations blog
>   Migrations for 'blog':
>  blog/migrations/0001_initial.py:
>  Create model Post

Django prepared a migration file for us that we now have to apply to our database. Type `python manage.py migrate blog` and the output should be as follows:

>  Operations to perform:
>  Apply all migrations: blog
>   Running migrations:
>   Rendering model states... DONE
>   Applying blog.0001_initial... OK

Hurray! Our Post model is now in our database! It would be nice to see it, right? Jump to the next chapter to see what your Post looks like!
