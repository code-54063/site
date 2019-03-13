---
title: Crawling
category: scrapy
order: 
permalink: "/scrapy/crawling"
last_modified_at: "January 11, 2017"
---

To put our spider to work, go to the project's top level directory and run:

```
scrapy crawl dmoz
```

The `crawl dmoz` command runs the spider for the `dmoz.org` domain. You will get an output similar to
this:


> 2008-08-20 03:51:13-0300 [scrapy] INFO: Started project: dmoz
> 2008-08-20 03:51:13-0300 [tutorial] INFO: Enabled extensions: ...
> 2008-08-20 03:51:13-0300 [tutorial] INFO: Enabled downloader middlewares: ...
> 2008-08-20 03:51:13-0300 [tutorial] INFO: Enabled spider middlewares: ...
> 2008-08-20 03:51:13-0300 [tutorial] INFO: Enabled item pipelines: ...
> 2008-08-20 03:51:14-0300 [dmoz] INFO: Spider opened
>  2008-08-20 03:51:14-0300 [dmoz] DEBUG: Crawled <http://www.dmoz.org/Computers/Programming/Languages/Python/Resources/> (referer: <None>)
> 2008-08-20 03:51:14-0300 [dmoz] DEBUG: Crawled <http://www.dmoz.org/Computers/Programming/Languages/Python/Books/> (referer: <None>)
> 2008-08-20 03:51:14-0300 [dmoz] INFO: Spider closed (finished)

Pay attention to the lines containing `[dmoz]`, which corresponds to our spider. You can see a log line for each URL defined in `start_urls`. Because these URLs are the starting ones, they have no referrers, which is shown at the end of the log line, where it says `(referer: <None>)`.

But more interesting, as our `parse` method instructs, two files have been created: *Books* and *Resources*, with the content of both URLs.

## What just happened under the hood?

Scrapy creates [`scrapy.http.Request`](https://doc.scrapy.org/en/0.16/topics/request-response.html#scrapy.http.Request) objects for each URL in the `start_urls` attribute of the Spider, and assigns them the `parse` method of the spider as their callback function.

These Requests are scheduled, then executed, and [`scrapy.http.Response`](https://doc.scrapy.org/en/0.16/topics/request-response.html#scrapy.http.Response) objects are returned and then fed back to the spider, through
the [`parse()`](https://doc.scrapy.org/en/0.16/topics/spiders.html#scrapy.spider.BaseSpider.parse) method.
