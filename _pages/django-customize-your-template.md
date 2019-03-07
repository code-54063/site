---
title: Customize your template
category: django
order: 
permalink: "/django/customize-your-template"
last_modified_at: "May 17, 2017"
---

You can now have a little fun and try to customize your template! Here are a few useful tags for that:

- `<h1>A heading</h1>` for your most important heading
- `<h2>A sub-heading</h2>` for a heading at the next level
- `<h3>A sub-sub-heading</h3>` ...and so on, up to `<h6>`
- `<p>A paragraph of text</p>`
- `<em>text</em>` emphasizes your text
- `<strong>text</strong>` strongly emphasizes your text
- `<br />` goes to another line (you can't put anything inside br)
- `<a href="https://djangogirls.org">link</a>` creates a link
- `<ul><li>first item</li><li>second item</li></ul>` makes a list, just like this one!
- `<div></div>` defines a section of the page

Here's an example of a full template, copy and paste it into `blog/templates/blog/post_list.html`:

`blog/templates/blog/post_list.html`

``` xml
<html>
    <head>
        <title>DSM code blog</title>
    </head>
    <body>
        <div>
            <h1><a href="">DSM Code Blog</a></h1>
		</div>
			
        <div>
            <p>published: 14.06.2014, 12:14</p>
            <h2><a href="">My first post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        </div>

	     <div>
             <p>published: 14.06.2014, 12:14</p>
             <h2><a href="">My second post</a></h2>
             <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut f.</p>
         </div>
	 </body>
</html>
```

We've created three `div` sections here.

- The first `div` element contains the title of our blog -- it's a
    heading and a link
- Another two `div` elements contain our blogposts with a published date, `h2` with a post title that is clickable and two `p`s (paragraph) of text, one for the date and one for our blogpost.

It gives us this effect:

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/2017-01-11-at-6.10.45-pm.jpg)

Yaaay! But so far, our template only ever displays exactly the same information -- whereas earlier we were talking about templates as allowing us to display different information in the same format.

But it looks a bit ugly. So install Bootstrap here: To install Bootstrap, you need to add this to your `<head>` in your `.html` file:

`blog/templates/blog/post_list.html`

``` xml
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css">
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css">
```

This doesn't add any files to your project. It just points to files that exist on the Internet. Just go ahead, open your website and refresh the page. Here it is!

We're going to end the blog tutorial here. But if you want to keep working on it (and maybe even submit it for your A3) you can work out how to develop CSS style sheets [here ](https://tutorial.djangogirls.org/en/css/)and extend your templates [here](https://tutorial.djangogirls.org/en/template_extending/). Keep reading the rest of the blog for further information.
