---
title: Installing Scrapy
category: scrape
order: 
permalink: "/scrape/installing-scrapy"
last_modified_at: "March 16, 2017"
---

## Pre-requisites

The installation steps assume that you have the following things installed:

- Python 2.6 or 2.7
- OpenSSL. This comes preinstalled in all operating systems except Windows (see [Platform specific installation
    notes](https://doc.scrapy.org/en/0.16/intro/install.html#intro-install-platform-notes))
- [pip](http://www.pip-installer.org/en/latest/installing.html) or [easy_install](http://pypi.python.org/pypi/setuptools) Python package managers. 

## Install

You can install Scrapy using easy\_install or pip (which is the canonical way to distribute and install Python packages).

** Note: Check [Platform specific installation
notes](https://doc.scrapy.org/en/0.16/intro/install.html#intro-install-platform-notes) first.

- To install using pip: `pip install Scrapy`.
- To install using easy_install: `easy_install Scrapy`.

### Platform specific installation notes

#### Windows

After installing Python, follow these steps before installing Scrapy:

-  add the `C:\python27\Scripts` and `C:\python27` folders to the system path by adding those directories to the `PATH` environment variable from the [Control Panel](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/sysdm_advancd_environmnt_addchange_variable.mspx).
-  install OpenSSL by following these steps:
1. go to [Win32 OpenSSL
        page](http://slproweb.com/products/Win32OpenSSL.html)
2. download Visual C++ 2008 redistributables for your Windows and architecture
3. download OpenSSL for your Windows and architecture (the regular version, not the light one)
4. add the `c:\openssl-win32\bin` (or similar) directory to your `PATH`, the same way you added `python27`{.docutils .literal} in the first step" in the first step
-  some binary packages that Scrapy depends on (like Twisted, lxml and pyOpenSSL) require a compiler available to install, and fail if you don't have Visual Studio installed. You can find Windows installers for those in the following links. Make sure you respect your Python version and Windows architecture.
- pywin32: <http://sourceforge.net/projects/pywin32/files/>
- Twisted: <http://twistedmatrix.com/trac/wiki/Downloads>
- zope.interface: download the egg from [zope.interface pypi page](http://pypi.python.org/pypi/zope.interface) and install it by running `easy_install file.egg`
- lxml: <http://pypi.python.org/pypi/lxml/>
- pyOpenSSL: <https://launchpad.net/pyopenssl>
