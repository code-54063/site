---
title: Anaconda
category:getting-started
order: 2
permalink: "/getting-started/anaconda"
last_modified_at: "July 10, 2019"
---


![anaconda-logo](https://cloudstor.aarnet.edu.au/plus/s/VKfqVc4PcuNBz3M/download)

**Anaconda** is a free distribution of Python (the programming language we use for the coding exercises in this subject). That is, by installing Anaconda you also install Python.

Installing Anaconda is very simple and is available for both Windows and Mac.

**Install Python 3.x, not Python 2.7**: Make sure you install the Python 3.7 version (or higher) of Anaconda. There are significant differences between Python 2 and 3 and Python 3 code is not guaranteed to run under Python 2.


## Installing Anaconda on Windows

If you run Windows, visit [https://docs.anaconda.com/anaconda/install/windows/](https://docs.anaconda.com/anaconda/install/windows/), which will guide you step-by-step through the installation.

There are a few options in the installation process. If in doubt, do what suggested. So, make sure that you

* *Do not select* to add Anaconda to your PATH;
* *Do select* to register Anaconda as your default Python.

![anaconda-win-install-options](https://cloudstor.aarnet.edu.au/plus/s/WXVc6u783wZWqFu/download)

### Using Anaconda on Windows

Once you have completed the installation, there are two ways you can use Python.

#### Anaconda Prompt
From the Start menu, search for and open "Anaconda Prompt". To enter the Python *interpreter*, just type `python`.

![anaconda-prompt-01](https://cloudstor.aarnet.edu.au/plus/s/1EOiY69nSBSQ9BB/download)
        
#### Spyder
From the Start menu, search for and open "Anaconda Navigator". From Anaconda Navigator, you can launch"Spyder".

![anaconda-navigator-win-01](https://cloudstor.aarnet.edu.au/plus/s/ya3NW8TmLCbNsiE/download)
![anaconda-navigator-win-02](https://cloudstor.aarnet.edu.au/plus/s/T2tAImKdTQlX4iA/download)

## Installing Anaconda on macOS

If you run macOS, visit [https://docs.anaconda.com/anaconda/install/mac-os/](https://docs.anaconda.com/anaconda/install/mac-os/), which will guide you step-by-step through the installation.

There are a few options in the installation process. If in doubt, do what suggested.

### Using Anaconda Python on macOS

Once you have completed the installation, there are two ways you can use Python.

#### Terminal

After completing the installation of Anaconda, you should make sure that you can access Anaconda Python from your *Terminal*.

1. Launch *Terminal* (if you don't know where is it, just search it with *Spotlight*, the small magnifying glass in the top-right corner);
2. Type `python`.

After your Python interpreter is started you should be able to read `Anaconda, Inc.` somewhere after the information about your Python version (which should be Python 3.7.1 or higher).

You can now interactively code in Python!
    
#### Spyder

After installing Anaconda, you should find *Anaconda Navigator* in your Applications. Once opened, launch *Spyder*.

![anaconda-navigator-win-02](https://cloudstor.aarnet.edu.au/plus/s/T2tAImKdTQlX4iA/download)

With *Spyder*, you have access to a Python *interpreter* (2) where you can enter Python commands and run them interactively.

But you can also open a text file containing Python code (1) and execute it. 

![anaconda-spyder](https://cloudstor.aarnet.edu.au/plus/s/TlWq5OotEpMqHar)



### Installing Python packages with Conda

There are (in June 2019) 63,595 Python packages out there. By installing these packages, you will get access to hundreds of thousands of functions written and donated to the Python community. That is, learning to install and use additional packages is essential.

By installing Anaconda, you have also installed **Conda**, which is a package management system.

For example, if you want to install a package called `django` with *Conda* simply open *Anaconda Prompt* (Windows) or *Terminal* (Mac) and write `conda install django`. When/if you are asked `Proceed ([y]/n)?`, answer `y`.

To check if Django installed correctly, launch `python` and in the Python interpreter type `import django`: no message means the package loaded correctly.

## Issues installing/using the software?

Post a question on [Teams](https://teams.microsoft.com/l/team/19%3abef8a451adf949aba91629d0f8666574%40thread.skype/conversations?groupId=6b2b6609-a95b-40a2-8570-91455f3f78ba&tenantId=e8911c26-cf9f-4a9c-878e-527807be8791)!


