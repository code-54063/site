---
title: Your first spider
category: django
order: 
permalink: "/scrape/your-first-spider"
last_modified_at: "January 11, 2017"
---

Spiders are user-written classes used to scrape information from a domain (or group of domains).

They define an initial list of URLs to download, how to follow links, and how to parse the contents of those pages to extract [items](https://doc.scrapy.org/en/0.16/topics/items.html#topics-items).

To create a Spider, you must subclass [`scrapy.spider.BaseSpider`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider), and define the three main, mandatory, attributes:

- [`name`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider.name): identifies the Spider. It must be unique, that is, you can't set the same name for different Spiders.

- [`start_urls`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider.start_urls): is a list of URLs where the Spider will begin to crawl from. So, the first pages downloaded will be those listed here. The subsequent URLs will be generated successively from data contained in the start URLs.

- [`parse()`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider.parse) is a method of the spider, which will be called with the downloaded [`Response`](https://doc.scrapy.org/en/0.16/topics/request-response.html#scrapy.http.Response)object of each start URL. The response is passed to the method as the first and only argument.

This method is responsible for parsing the response data and extracting scraped data (as scraped items) and more URLs to follow.

The [`parse()`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider.parse) method is in charge of processing the response and returning scraped data (as [`Item`](https://doc.scrapy.org/en/0.16/topics/items.html#scrapy.item.Item) objects) and more URLs to follow (as [`Request`](https://doc.scrapy.org/en/0.16/topics/request-response.html#scrapy.http.Request) objects).

This is the code for our first Spider; save it in a file named `dmoz_spider.py` under the `dmoz/spiders` directory:

``` python
from scrapy.spider import BaseSpider

class DmozSpider(BaseSpider):
	name = "dmoz"
	allowed_domains = ["dmoz.org"]
	start_urls = [
            "http://www.dmoz.org/Computers/Programming/Languages/Python/Books/",
            "http://www.dmoz.org/Computers/Programming/Languages/Python/Resources/"
			]

def parse(self, response):
	filename = response.url.split("/")[-2]
	open(filename, 'wb').write(response.body)
```

