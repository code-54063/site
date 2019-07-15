---
title: Static files in Django
category: django
order: 
permalink: "/django/static-files"
last_modified_at: "September 13, 2018"
---

Finally we will take a closer look at these things we've been calling **static files**. Static files are all your CSS and images. Their content doesn't depend on the request context and will be the same for every user.

## Where to put static files for Django

Django already knows where to find the static files for the built-in "admin" app. Now we need to add some static files for our own app, `blog`.

We do that by creating a folder called `static` inside the blog app:

```
    djangogirls
    ├── blog
    │   ├── migrations
    │   ├── static
    │   └── templates
    └── mysite
```

Django will automatically find any folders called "static" inside any of your apps' folders. Then it will be able to use their contents as static files.

### Your first CSS file!

Let's create a CSS file now, to add your own style to your web page. Create a new directory called `css`inside your `static` directory. Then create a new file called `blog.css` inside this `css` directory. Ready?

```
    djangogirls
    └─── blog
         └─── static
              └─── css
              └─── blog.css
```

Time to write some CSS! Open up the `blog/static/css/blog.css` file in your code editor.

We won't be going too deep into customizing and learning about CSS here. There is a recommendation for a free CSS course at the end of this page if you would like to learn more.

But let's do at least a little. Maybe we could change the color of our header? To understand colors, computers use special codes. These codes start with `#` followed by 6 letters (A--F) and numbers (0--9). For example, the code for blue is `#0000FF`. You can find the color codes for many colors [here](http://www.colorpicker.com/). You may also use [predefined colors](http://www.w3schools.com/colors/colors_names.asp), such as `red` and `green`.

In your `blog/static/css/blog.css` file you should add the following code:

``` css
h1 a {
        color: #FCA205;
		}
```

`h1 a` is a CSS Selector. This means we're applying our styles to any `a` element inside of an `h1`element. So when we have something like `<h1><a href="">link</a></h1>`, the `h1 a` style will apply. In this case, we're telling it to change its color to `#FCA205`, which is orange. Or you can put your own color here!

In a CSS file we determine styles for elements in the HTML file. The first way we identify elements is with the element name. You might remember these as tags from the HTML section. Things like `a`, `h1`, and `body` are all examples of element names. We also identify elements by the attribute `class` or the attribute `id`. Class and id are names you give the element by yourself. Classes define groups of elements, and ids point to specific elements. For example, you could identify the following tag by using the tag name `a`, the class `external_link`, or the id `link_to_wiki_page`:


``` html
<a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page">
```

You can read more about [CSS Selectors at w3schools](http://www.w3schools.com/cssref/css_selectors.asp).

We also need to tell our HTML template that we added some CSS. Open the `blog/templates/blog/post_list.html` file in the code editor and add this line at the very beginning of it: `blog/templates/blog/post_list.html`.

We're just loading static files here. 🙂 Between the `<head>` and `</head>` tags, after the links to the Bootstrap CSS files, add this line:

{% raw %}
``` html
<link rel="stylesheet" href="{% static 'css/blog.css' %}">
```
{% endraw %}

The browser reads the files in the order they're given, so we need to make sure this is in the right place. Otherwise the code in our file may be overriden by code in Bootstrap files. We just told our template where our CSS file is located.

Your file should now look like this:

{% raw %}
``` html
{% load static %}
<html>
    <head>
            <title>Django Girls blog</title>
            <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
            <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
            <link rel="stylesheet" href="{% static 'css/blog.css' %}">
        </head>
        <body>
            <div>
                <h1><a href="/">Django Girls Blog</a></h1>
            </div>

            {% for post in posts %}
                <div>
                    <p>published: {{ post.published_date }}</p>
                    <h1><a href="">{{ post.title }}</a></h1>
                    <p>{{ post.text|linebreaksbr }}</p>
                </div>
            {% endfor %}
        </body>
</html>
```
{% endraw %}

OK, save the file and refresh the site!

![Figure 14.2](https://tutorial.djangogirls.org/en/css/images/color2.png)

Nice work! Maybe we would also like to give our website a little air and increase the margin on the left side? Let's try this!

``` css
    body {
        padding-left: 15px;
    }
```

Add that to your CSS, save the file and see how it works!

![Figure 14.3](https://tutorial.djangogirls.org/en/css/images/margin2.png)

Maybe we can customize the font in our header? Paste this into your `<head>` in `blog/templates/blog/post_list.html` file `blog/templates/blog/post_list.html`.

``` xml
<link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css">
``` 

As before, check the order and place before the link to `blog/static/css/blog.css`. This line will import a font called *Lobster* from Google Fonts (<https://www.google.com/fonts>).

Find the `h1 a` declaration block (the code between braces `{` and `}`) in the CSS file `blog/static/css/blog.css`. Now add the line `font-family: 'Lobster';` between the braces, and refresh the page:

``` css
h1 a {
	color: #FCA205;
	font-family: 'Lobster';
}
```

![Figure 14.3](https://tutorial.djangogirls.org/en/css/images/font.png)

Great!

As mentioned above, CSS has a concept of classes. These allow you to name a part of the HTML code and apply styles only to this part, without affecting other parts. This can be super helpful! Maybe you have two divs that are doing something different (like your header and your post). A class can help you make them look different.

Go ahead and name some parts of the HTML code. Add a class called `page-header` to your `div` that contains your header, like this:

``` xml
<div class="page-header">
	<h1><a href="/">Django Girls Blog</a></h1>
</div>
```

And now add a class `post` to your `div` containing a blog post.

{% raw %}
``` xml
<div class="post">
	<p>published: {{ post.published_date }}</p>
	<h1><a href="">{{ post.title }}</a></h1>
    <p>{{ post.text|linebreaksbr }}</p>
</div>
```
{% endraw %}

We will now add declaration blocks to different selectors. Selectors starting with `.` relate to classes. There are many great tutorials and explanations about CSS on the Web that can help you understand the following code. For now, copy and paste it into your `blog/static/css/blog.css` file:

``` css
.page-header {
        background-color: #ff9400;
        margin-top: 0;
        padding: 20px 20px 20px 40px;
    }
.page-header h1, .page-header h1 a, .page-header h1 a:visited, .page-header h1 a:active {
        color: #ffffff;
        font-size: 36pt;
        text-decoration: none;
    }

.content {
        margin-left: 40px;
    }

h1, h2, h3, h4 {
        font-family: 'Lobster', cursive;
    }

.date {
        color: #828282;
    }

.save {
        float: right;
    }

.post-form textarea, .post-form input {
        width: 100%;
    }

.top-menu, .top-menu:hover, .top-menu:visited {
        color: #ffffff;
        float: right;
        font-size: 26pt;
        margin-right: 20px;
    }

.post {
        margin-bottom: 70px;
    }

.post h1 a, .post h1 a:visited {
        color: #000000;
    }
```

Then surround the HTML code which displays the posts with declarations of classes. Replace this:

{% raw %}
``` xml
    {% for post in posts %}
        <div class="post">
            <p>published: {{ post.published_date }}</p>
            <h1><a href="">{{ post.title }}</a></h1>
            <p>{{ post.text|linebreaksbr }}</p>
        </div>
		{% endfor %}
```
{% endraw %}

in the `blog/templates/blog/post_list.html` with this:

{% raw %}
``` xml
    <div class="content container">
        <div class="row">
            <div class="col-md-8">
                {% for post in posts %}
                    <div class="post">
                        <div class="date">
                            <p>published: {{ post.published_date }}</p>
                        </div>
                        <h1><a href="">{{ post.title }}</a></h1>
                        <p>{{ post.text|linebreaksbr }}</p>
                    </div>
                {% endfor %}
            </div>
        </div>
		</div>
```
{% endraw %}

Save those files and refresh your website.

![Figure 14.4](https://tutorial.djangogirls.org/en/css/images/final.png)

Woohoo! Looks awesome, right? Look at the code we just pasted to find the places where we added classes in the HTML and used them in the CSS. Where would you make the change if you wanted the date to be turquoise?

Don't be afraid to tinker with this CSS a little bit and try to change some things. Playing with the CSS can help you understand what the different things are doing. If you break something, don't worry -- you can always undo it!

We really recommend taking this free online [Codeacademy HTML & CSS course](https://www.codecademy.com/tracks/web). It can help you learn all about making your websites prettier with CSS.