---
title: Regex
category: django
order: 
permalink: "/django/regex"
last_modified_at: "January 11, 2017"
---

Do you wonder how Django matches URLs to views? Well, this part is tricky. Django uses `regex`, short for "regular expressions". Regex has a lot (a lot!) of rules that form a search pattern. Since regexes are an advanced topic, we will not go in detail over how they work.

If you still wish to understand how we created the patterns, here is an example of the process -- we will only need a limited subset of the rules to express the pattern we are looking for, namely:

- `^` for the beginning of the text
- `$` for the end of the text
- `\d` for a digit
- `+` to indicate that the previous item should be repeated at least once
- `()` to capture part of the pattern

Anything else in the URL definition will be taken literally.

Now imagine you have a website with the address like `http://www.mysite.com/post/12345/`, where `12345` is the number of your post.

Writing separate views for all the post numbers would be really annoying. With regular expressions, we can create a pattern that will match the URL and extract the number for us: `^post/(\d+)/$`. Let's break this down piece by piece to see what we are doing here:

-  `^post` is telling Django to take anything that has `post` at the  beginning of the url (right after `^`)
-   `(\d+)` means that there will be a number (one or more digits) and that we want the number captured and extracted
-   `/` tells django that another `/` character should follow
-   `$` then indicates the end of the URL meaning that only strings ending with the `/` will match this pattern.
