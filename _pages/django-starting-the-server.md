---
title: Starting the server
category: django
order: 
permalink: "/django/starting-the-server"
last_modified_at: "August 29, 2017"
---

You need to be in the directory that contains the `manage.py` file (the `djangogirls` directory). In the console, we can start the web server by running `python manage.py runserver`:

command-line
> (myvenv) ~/djangogirls$ python manage.py runserver

If you are on a Chromebook, use this command instead:

Cloud 9
>  (myvenv) ~/djangogirls$ python manage.py runserver 0.0.0.0:8080

If you are on Windows and this fails with `UnicodeDecodeError`, use this command instead:

command-line
>(myvenv) ~/djangogirls$ python manage.py runserver 0:8000

Now all you need to do is check that your website is running. Open your browser (Firefox, Chrome, Safari, Internet Explorer or whatever you use) and enter this address:

browser
```
http://127.0.0.1:8000/
```

If you're using a Chromebook, you'll always visit your test server by accessing:

browser
```
https://django-girls-<your cloud9 username>.c9users.io
```

Congratulations! You've just created your first website and run it using a web server! Isn't that awesome?

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-10-at-4.29.56-pm.jpg)

While the web server is running, you won't see a new command-line prompt to enter additional commands. The terminal will accept new text but will not execute new commands. This is because the web server continuously runs in order to listen for incoming requests.

To type additional commands while the web server is running, open a new terminal window and activate your virtualenv. To stop the web server, switch back to the window in which it's running and press CTRL+C -- Control and C buttons together (on Windows, you might have to press Ctrl+Break).

Ready for the next step? It's time to create some content!
