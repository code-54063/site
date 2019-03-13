---
title: Selectors
category: scrapy
order: 
permalink: "/scrapy/selectors"
last_modified_at: "January 11, 2017"
---

Here are some examples of XPath expressions and their meanings:

- `/html/head/title`: selects the `<title>` element, inside the `<head>` element of a HTML document
- `/html/head/title/text()`: selects the text inside the aforementioned `<title>`{.docutils .literal} element.
- `//td`: selects all the `<td>` elements
- `//div[@class="mine"]`: selects all `div`{.docutils .literal} elements which contain an attribute `class="mine"`

These are just a couple of simple examples of what you can do with XPath, but XPath expressions are indeed much more powerful. To learn more about XPath we recommend [this XPath tutorial](http://www.w3schools.com/XPath/default.asp).

For working with XPaths, Scrapy provides a [`XPathSelector`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.XPathSelector "scrapy.selector.XPathSelector") class, which comes in two flavours, [`HtmlXPathSelector`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.HtmlXPathSelector) (for HTML data) and [`XmlXPathSelector`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.XmlXPathSelector) (for XML data). In order to use them you must instantiate the desired class with a [`Response`](https://doc.scrapy.org/en/0.16/topics/request-response.html#scrapy.http.Response) object.

You can see selectors as objects that represent nodes in the document structure. So, the first instantiated selectors are associated to the root node, or the entire document.

Selectors have three methods (click on the method to see the complete API documentation).

- [`select()`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.XPathSelector.select): returns a list of selectors, each of them representing the nodes selected by the xpath expression given as argument.

- [`extract()`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.XPathSelector.extract ): returns a unicode string with the data selected by the XPath selector.

- [`re()`](https://doc.scrapy.org/en/0.16/topics/selectors.html#scrapy.selector.XPathSelector.re): returns a list of unicode strings extracted by applying the regular expression given as argument.

## Trying Selectors in the Shell

To illustrate the use of Selectors we're going to use the built-in [Scrapy shell](https://doc.scrapy.org/en/0.16/topics/shell.html#topics-shell), which also requires IPython (an extended Python console) installed on your system.

To start a shell, you must go to the project's top level directory and run: `scrapy shell http://www.dmoz.org/Computers/Programming/Languages/Python/Books/`.

This is what the shell looks like:

```
    [ ... Scrapy log here ... ]

    [s] Available Scrapy objects:
    [s] 2010-08-19 21:45:59-0300 [default] INFO: Spider closed (finished)
    [s]   hxs        <HtmlXPathSelector (http://www.dmoz.org/Computers/Programming/Languages/Python/Books/) xpath=None>
    [s]   item       Item()
    [s]   request    <GET http://www.dmoz.org/Computers/Programming/Languages/Python/Books/>
    [s]   response   <200 http://www.dmoz.org/Computers/Programming/Languages/Python/Books/>
    [s]   spider     <BaseSpider 'default' at 0x1b6c2d0>
    [s]   xxs        <XmlXPathSelector (http://www.dmoz.org/Computers/Programming/Languages/Python/Books/) xpath=None>
    [s] Useful shortcuts:
    [s]   shelp()           Print this help
    [s]   fetch(req_or_url) Fetch a new request or URL and update shell objects
    [s]   view(response)    View response in a browser

    In [1]:
```

After the shell loads, you will have the response fetched in a local `response` variable, so if you type `response.body` you will see the body of the response, or you can type `response.headers` to see its headers.

The shell also instantiates two selectors, one for HTML (in the `hxs` variable) and one for XML (in the
`xxs` variable) with this response. So let's try them:

```
    In [1]: hxs.select('//title')
    Out[1]: [<HtmlXPathSelector (title) xpath=//title>]

    In [2]: hxs.select('//title').extract()
    Out[2]: [u'<title>Open Directory - Computers: Programming: Languages: Python: Books</title>']

    In [3]: hxs.select('//title/text()')
    Out[3]: [<HtmlXPathSelector (text) xpath=//title/text()>]

    In [4]: hxs.select('//title/text()').extract()
    Out[4]: [u'Open Directory - Computers: Programming: Languages: Python: Books']

    In [5]: hxs.select('//title/text()').re('(\w+):')
    Out[5]: [u'Computers', u'Programming', u'Languages', u'Python']
```
