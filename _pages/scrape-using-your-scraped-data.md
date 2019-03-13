---
title: Using your scraped data
category: scrape
order: 
permalink: "/scrape/using-your-scrape-data"
last_modified_at: "January 11, 2017"
---

[`Item`](https://doc.scrapy.org/en/0.16/topics/items.html#scrapy.item.Item) objects are custom Python dicts; you can access the values of their fields (attributes of the class we defined earlier) using the standard dict syntax like:

> item = DmozItem()
> item['title'] = 'Example title'
> item['title']
> 'Example title'

Spiders are expected to return their scraped data inside [`Item`](https://doc.scrapy.org/en/0.16/topics/items.html#scrapy.item.Item) objects. So, in order to return the data we've scraped so far, the final code for our Spider would be like this:

``` python
from scrapy.spider import BaseSpider
from scrapy.selector import HtmlXPathSelector

from tutorial.items import DmozItem

class DmozSpider(BaseSpider):
    name = "dmoz"
    allowed_domains = ["dmoz.org"]
    start_urls = [
        "http://www.dmoz.org/Computers/Programming/Languages/Python/Books/",
        "http://www.dmoz.org/Computers/Programming/Languages/Python/Resources/"
       ]

def parse(self, response):
    hxs = HtmlXPathSelector(response)
    sites = hxs.select('//ul/li')
    items = []
    for site in sites:
        item = DmozItem()
        item['title'] = site.select('a/text()').extract()
        item['link'] = site.select('a/@href').extract()
        item['desc'] = site.select('text()').extract()
        items.append(item)
    return items
```
		   
**Note: You can find a fully-functional variant of this spider in the [dirbot](https://github.com/scrapy/dirbot) project available [here](https://github.com/scrapy/dirbot)**.

Now doing a crawl on the dmoz.org domain yields `DmozItem`'s:

```
    [dmoz] DEBUG: Scraped from <200 http://www.dmoz.org/Computers/Programming/Languages/Python/Books/>
         {'desc': [u' - By David Mertz; Addison Wesley. Book in progress, full text, ASCII format. Asks for feedback. [author website, Gnosis Software, Inc.\n],
          'link': [u'http://gnosis.cx/TPiP/'],
          'title': [u'Text Processing in Python']}
    [dmoz] DEBUG: Scraped from <200 http://www.dmoz.org/Computers/Programming/Languages/Python/Books/>
         {'desc': [u' - By Sean McGrath; Prentice Hall PTR, 2000, ISBN 0130211192, has CD-ROM. Methods to build XML applications fast, Python tutorial, DOM and SAX, new Pyxie open source XML processing library. [Prentice Hall PTR]\n'],
          'link': [u'http://www.informit.com/store/product.aspx?isbn=0130211192'],
          'title': [u'XML Processing with Python']}
```

## Storing the scraped data

The simplest way to store the scraped data is by using the [Feed exports](https://doc.scrapy.org/en/0.16/topics/feed-exports.html#topics-feed-exports), with the following command: `scrapy crawl dmoz -o items.json -t json`.

That will generate a `items.json` file containing all scraped items, serialized in [JSON](http://en.wikipedia.org/wiki/JSON).

In small projects (like the one in this tutorial), that should be enough. However, if you want to perform more complex things with the scraped items, you can write an [Item Pipeline](https://doc.scrapy.org/en/0.16/topics/item-pipeline.html#topics-item-pipeline). As with Items, a placeholder file for Item Pipelines has been set up for you when the project is created, in `tutorial/pipelines.py`. Though you don't need to implement any item pipeline if you just want to store the scraped items.
