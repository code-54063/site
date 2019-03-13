---
title: Extracting the data
category: scrape
order: 
permalink: "/scrape/extracting-the-data"
last_modified_at: "January 11, 2017"
---

Now, let's try to extract some real information from those pages.

You could type `response.body` in the console, and inspect the source code to figure out the XPaths you need to use. However, inspecting the raw HTML code there could become a very tedious task. To make this an easier task, you can use some Firefox extensions like Firebug. For more information see [Using Firebug for scraping](https://doc.scrapy.org/en/0.16/topics/firebug.html#topics-firebug) and [Using Firefox for scraping](https://doc.scrapy.org/en/0.16/topics/firefox.html#topics-firefox).

After inspecting the page source, you'll find that the web sites information is inside a `<ul>`{.docutils .literal}element, in fact the *second* `<ul>` element.

So we can select each `<li>` element belonging to the sites list with this code:

``` python
hxs.select('//ul/li')
```

And from them, the sites descriptions:

``` python
hxs.select('//ul/li/text()').extract()
```

The sites titles:

``` python
hxs.select('//ul/li/a/text()').extract()
```

And the sites links:

``` python
hxs.select('//ul/li/a/@href').extract()
```

As we said before, each `select()`{.docutils .literal} call returns a list of selectors, so we can concatenate further `select()` calls to dig deeper into a node. We are going to use that property here, so:

``` python
sites = hxs.select('//ul/li')
for site in sites:
    title = site.select('a/text()').extract()
    link = site.select('a/@href').extract()
    desc = site.select('text()').extract()
    print title, link, desc
	```
	
**Note:  For a more detailed description of using nested selectors, see [Nesting
selectors](https://doc.scrapy.org/en/0.16/topics/selectors.html#topics-selectors-nesting-selectors) and[Working with relative
XPaths](https://doc.scrapy.org/en/0.16/topics/selectors.html#topics-selectors-relative-xpaths) in the
[Selectors](https://doc.scrapy.org/en/0.16/topics/selectors.html#topics-selectors) documentation.**

Let's add this code to our spider:


``` python
from scrapy.spider import BaseSpider
from scrapy.selector import HtmlXPathSelector

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
    for site in sites:
        title = site.select('a/text()').extract()
        link = site.select('a/@href').extract()
        desc = site.select('text()').extract()
        print title, link, desc
```
				
Now try crawling the dmoz.org domain again and you'll see sites being printed in your output, run:

```
scrapy crawl dmoz
```
