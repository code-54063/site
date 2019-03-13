---
title: Defining your item
category: scrape
order: 
permalink: "/scrape/defining-your-item"
last_modified_at: ""
---

Items are containers that will be loaded with the scraped data; they work like simple python dicts but provide additional protecting against populating undeclared fields, to prevent typos.

They are declared by creating an [`scrapy.item.Item`](https://doc.scrapy.org/en/0.16/topics/items.html#scrapy.item.Item) class an defining its attributes as [`scrapy.item.Field`](https://doc.scrapy.org/en/0.16/topics/items.html#scrapy.item.Field) objects, like you will in an ORM (don't worry if you're not familiar with ORMs, you will see that this is an easy task).

We begin by modeling the item that we will use to hold the sites data obtained from dmoz.org, as we want to capture the name, url and description of the sites, we define fields for each of these three attributes. To do that, we edit items.py, found in the `tutorial` directory. Our Item class looks like this:


    from scrapy.item import Item, Field

    class DmozItem(Item):
        title = Field()
        link = Field()
        desc = Field()
:::
:::

This may seem complicated at first, but defining the item allows you to
use other handy components of Scrapy that need to know how your item
looks like.
:::

::: {.wedocs-article-author itemprop="author" itemscope="" itemtype="https://schema.org/Person"}
:::

Updated on January 11, 2017
:::
:::
:::
:::
:::
:::

::: {.container}
::: {.row}
::: {.widget-area .clearfix}
::: {.section .widget .col-md-3 .pages-3 .widget_pages}
### Quick links

-   [Home](../../../../index.html)
:::
:::

::: {.col-md-12 .copyright .clearfix}
[ © 2019 DSM \| Code ]{.copy-text}
:::
:::
:::
