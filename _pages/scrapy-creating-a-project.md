---
title: Creating a project
category: scrapy
order: 
permalink: "/scrapy/creating-a-project"
last_modified_at: "January 11, 2017"
---

Before you start scraping, you will have set up a new Scrapy project. Enter a directory where you'd like to store your code and then run:

```
scrapy startproject tutorial
```

This will create a `tutorial` directory with the following contents:

```
    tutorial/
        scrapy.cfg
        tutorial/
            __init__.py
            items.py
            pipelines.py
            settings.py
            spiders/
                __init__.py
                ...
```

These are basically:

-   `scrapy.cfg`: the project configuration file
-   `tutorial/`: the project's python module, you'll later import your code from here.
-   `tutorial/items.py`: the project's items file.
-   `tutorial/pipelines.py`: the project's pipelines
    file.
-   `tutorial/settings.py`: the project's settings file.
-   `tutorial/spiders/`: a directory where you'll later put your spiders.
