---
title: Django views
category: django
order: 
permalink: "/django/views"
last_modified_at: "May 17, 2017"
---

Time to get rid of the bug we created! =)

A *view* is a place where we put the "logic" of our application. It will request information from the `model`you created before and pass it to a `template`. We'll create a template in the next chapter. Views are just Python functions that are a little bit more complicated than the ones we learnt about in the early weeks of this course.

Views are placed in the `views.py` file. We will add our *views* to the `blog/views.py` file.

## blog/views.py

OK, let's open up this file and see what's in there:

``` python
# blog/views.py

from django.shortcuts import render

# Create your views here.

```

Not too much stuff here yet.

Remember that lines starting with `#` are comments -- this means that those lines won't be run by Python.

The simplest *view* can look like this:

``` python
# blog/views.py

def post_list(request):
return render(request, 'blog/post_list.html', {})
```

As you can see, we created a function (`def`) called `post_list` that takes `request` and `return` a function `render` that will render (put together) our template `blog/post_list.html`.

Save the file, go to `<http://127.0.0.1:8000/>` and see what we've got.

Another error! Read what's going on now:

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-11-at-6.01.32-pm.jpg)

This shows that the server is running again, at least, but it still doesn't look right, does it? Don't worry, it's just an error page, nothing to be scared of! Just like the error messages in the console, these are actually pretty useful. You can read that the *TemplateDoesNotExist*. Let's fix this bug and create a template in the next chapter!

**Learn more about Django views by reading the [official documentation](https://docs.djangoproject.com/en/1.10/topics/http/views/)**
