---
title: Installing Django
category: django
order: 
permalink: "/django/installing-django"
last_modified_at: "August 29, 2018"
---

## Installing Django

Now that you have your `virtualenv` started, you can install Django.

That's it! You're now (finally) ready to create a Django application!

*Handy Hint: \~\$ signals a new line. Don't type it, just ignore it.*

Before we do that, we should make sure we have the latest version of `pip`, the software that we use to install Django:

> (myvenv) ~$ pip install --upgrade pip

Then run `pip install django` to install Django.

> (myvenv) ~$ pip install django
> 
> Collecting django~=1.10.0
>    Downloading Django-1.10.4-py2.py3-none-any.whl (6.8MB) 
>    Installing collected packages: django 
 >    Successfully installed django-1.10.4

That's it! You're now (finally) ready to create a Django application!

## Troubleshooting

If you run into an error message when trying to install Django that looks like this:

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/Screen-Shot-2018-08-29-at-2.32.01-pm.png)

Run the following command in Terminal to force upgrade pip again (copy and paste the entire line): `curl https://bootstrap.pypa.io/get-pip.py | python`

After that try installing Django again.

### Windows

If you get an error when calling pip on Windows platform, please check if your project pathname contains spaces, accents or special characters (for example, `C:\\Users\\User Name\\djangogirls`). If it does, please consider using another place without spaces, accents or special characters (suggestion: C:\\djangogirls). Create a new virtualenv in the new directory, then delete the old one and try the above command again. (Moving the virtualenv directory won't work since virtualenv uses
absolute paths.)

### Windows 8 & 10

Your command line might freeze after when you try to install Django. If this happens, instead of the above command use:

> C:\Users\Name\djangogirls> python -m pip install django
