---
title: Working with virtualenv
category: django
order: 
permalink: "/django/working-with-virtualenv"
last_modified_at: " July 25, 2017"
---

The command above will create a directory called `myvenv` (or whatever name you chose) that contains our virtual environment (basically a bunch of directory and files).

You will know that you have `virtualenv` started when you see that the prompt in your console is prefixed with `(myvenv)`.

When working within a virtual environment, `python` will automatically refer to the correct version so you can use `python` instead of `python3`.

 
## MacOSX and Linux

Start your virtual environment by running from command-line

```
source myvenv/bin/activate
```
NOTE: sometimes `source` might not be available. In those cases try doing this instead: ` . myvenv/bin/activate`

## Windows

Start your virtual environment by running:

```
C:\Users\Name\djangogirls> < myvenv>\Scripts\activate
``

Remember to replace `< myvenv>` with your chosen `virtualenv` name! Also make sure you are using the right slashes! `\`  instead of  `/`.

NOTE: on Windows 10 you might get an error in the Windows PowerShell that says `execution of scripts is disabled on this system`. In this case, open another Windows PowerShell with the "Run as Administrator" option. Then try typing the following command before starting your virtual environment:
```
C:\WINDOWS\system32>  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```
> Execution Policy Change

The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose you to the security risks described in the about_Execution_Policies help topic at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): A

**Remember**

When your Virtual Environment is activate, it will display the name of it in brackets:

![no-alignment]({{ site.url }}{{ site.baseurl }}/assets/images/Screen-Shot-2017-07-25-at-1.12.48-pm.jpg)

To exit your Virtual Environment, simply type: `deactivate`.
