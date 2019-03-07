---
title: Objects
category: django
order: 
permalink: "/django/objects"
last_modified_at: "January 11, 2017"
---

What we want to create now is something that will store all the posts in our blog. But to be able to do that we need to talk a little bit about things called `objects`.

Objects {#objects}
-------

There is a concept in programming called *object-oriented programming*. The idea is that instead of writing everything as a boring sequence of programming instructions, we can model things and define how they interact with each other.

So what is an object? It is a collection of properties and actions. It sounds weird, but we will give you an example.

If we want to model a cat, we will create an object `Cat` that has some properties such as `color`, `age`, `mood` (like good, bad, or sleepy ;)), and `owner` (which could be assigned a `Person` object -- or maybe, in case of a stray cat, this property could be empty).

Then the `Cat` has some actions: `purr`, `scratch`, or `feed` (in which case, we will give the cat some `CatFood`, which could be a separate object with properties, like `taste`).

```
    Cat
    --------
    color
    age
    mood
    owner
    purr()
    scratch()
    feed(cat_food)

    CatFood
    --------
    taste
```

So basically the idea is to describe real things in code with properties (called `object properties`) and actions (called `methods`).

How will we model blog posts then? We want to build a blog, right?

We need to answer the question: What is a blog post? What properties should it have?

Well, for sure our blog post needs some text with its content and a title, right? It would be also nice to know who wrote it -- so we need an author. Finally, we want to know when the post was created and published.

```
    Post
    --------
    title
    text
    author
    created_date
    published_date
```

What kind of things could be done with a blog post? It would be nice to have some `method` that publishes the post, right?

So we will need a `publish` method.

Since we already know what we want to achieve, let's start modeling it in Django!
