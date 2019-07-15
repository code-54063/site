--
title: Object-oriented programming
category: web-scraping-with-python
permalink: "/web-scraping-with-python"
last_modified_at: " July 15, 2019"
---

In the following pages, we'll understand how to use Python to collect data from the web. Generally speaking, there are two way to collect data from the web:

1. Download a web page - the exact same HTML document that is rendered by your browser every time you visit google.com, facebook.com, uts.edu.au or any other webpage out there - and *parse* programmatically from the document the content we might be interested in. This task is generally referred to as *scraping*.

2. Request information from a application programming interface (a.k.a. [web API](https://en.wikipedia.org/wiki/Web_API)).

In general, if the information you are looking for is offered by an API, you don't want to lose time scraping the same information. Scraping is very time consuming (and can also be very frustrating)! To give you an example, a Python program to scrape a Twitter script can be coded in approximately 120 lines (see [this script](https://github.com/kennethreitz/twitter-scraper/blob/master/twitter_scraper.py)) while getting the same information from the Twitter API requires only a few lines:

```python
# Credit: http://benalexkeen.com/interacting-with-the-twitter-api-using-python/
search_headers = {
    'Authorization': 'Bearer {}'.format(access_token)
}

search_params = {
    'q': 'General Election',
    'result_type': 'recent',
    'count': 2
}

search_url = '{}1.1/search/tweets.json'.format(base_url)

search_resp = requests.get(search_url, headers=search_headers, params=search_params)
```

In this tutorial we won't explain how to get data from API. The web scraping tutorial is composed of these pages (ideally to be followed in this order):

1. [Getting started](/web-scraping-with-python/beautifulsoup-01-getting-started) (with an example)
2. [Understanding HTML]
3. Inspecting the page
4. Writing your scraping script
5. Export your data
6. Advanced users


