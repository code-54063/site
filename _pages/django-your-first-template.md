---
title: Your first template
category: django
order: 
permalink: "/django/your-first-template"
last_modified_at: "May 17, 2017"
---

Creating a template means creating a template file. Everything is a file, right? You have probably noticed this already.

Templates are saved in `blog/templates/blog`directory. So first create a directory called `templates` inside your blog directory. Then create another directory called `blog` inside your templates directory:

```
blog
	└───templates
    └───blog
```

(You might wonder why we need two directories both called `blog` -- as you will discover later, this is simply a useful naming convention that makes life easier when things start to get more complicated.)

And now create a `post_list.html` file inside Sublime Text (just leave it blank for now) and place it in the `blog/templates/blog`directory.

See how your website looks now: `<http://127.0.0.1:8000/>`.

> If you still have an error `TemplateDoesNotExist`, try to restart your server. Go into command line, stop the server by pressing Ctrl+C (Control and C buttons together) and start it again by running a `python manage.py runserver` command.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-11-at-6.08.12-pm.jpg)

No error anymore! Congratulations 🙂 However, your website isn't actually publishing anything except an empty page, because your template is empty too. We need to fix that.

Add the following to your template file: `blog/templates/blog/post_list.html`

``` xml
<html>
	<p>Hi there!</p>
    <p>It works!</p>
</html>
```

So how does your website look now? Visit it to find out: `<http://127.0.0.1:8000/>`.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-11-at-6.07.46-pm.jpg)

It worked! Nice work there 🙂

* The most basic tag, `<html>`, is always the beginning of any web page and `</html>` is always the end. As you can see, the whole content of the website goes between the beginning tag `<html>` and closing tag `</html>`.
* `<p>` is a tag for paragraph elements; `</p>`closes each paragraph.

## Head and body

Each HTML page is also divided into two elements: head and body.

* head is an element that contains information about the document that is not displayed on the screen.
* body is an element that contains everything else that is displayed as part of the web page.

We use `<head>` to tell the browser about the configuration of the page, and `<body>` to tell it what's actually on the page.

For example, you can put a web page title element inside the `<head>`, like this:


`blog/templates/blog/post_list.html`
``` xml
<html>
    <head>
        <title>Ola's blog</title>
    </head>
    <body>
        <p>Hi there!</p>
        <p>It works!</p>
    </body>
</html>
```

Save the file and refresh your page.

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-11-at-6.07.52-pm.jpg)

Notice how the browser has understood that "Ola's blog" is the title of your page? It has interpreted `<title>Ola's blog</title>` and placed the text in the title bar of your browser (it will also be used for bookmarks and so on).

Probably you have also noticed that each opening tag is matched by a *closing tag*, with a `/`, and that elements are *nested* (i.e. you can't close a particular tag until all the ones that were inside it have been closed too).

It's like putting things into boxes. You have one big box, `<html></html>`; inside it there is `<body></body>`, and that contains still smaller boxes: `<p></p>`.

You need to follow these rules of *closing* tags, and of *nesting* elements -- if you don't, the browser may not be able to interpret them properly and your page will display incorrectly.
