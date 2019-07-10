---
title: Jupyter Notebook
category: getting-started
order: 1
permalink: "/getting-started/jupyter-notebook"
last_modified_at: "July 10, 2019"
---

## Cloudstor

![cloudstor-logo.png](https://cloudstor.aarnet.edu.au/plus/s/pwXdzeYzcZPxqw9/download)

**Cloudstor** is a "file sharing and cloud storage solution for the research and education sector" (more information [here](https://www.aarnet.edu.au/network-and-services/cloud-services-applications/cloudstor)) offered by Australia’s Academic and Research Network (AARNet).

Basically, cloudstor is a service like Dropbox as it allows to store files online and optionally sync a folder located on your computer and all its files. 

UTS students (and staff) have access to the service (you also get out of the box 1TB of cloud storage).
  

To access cloudstor, you need to

1. Point your browser to [cloudstor.aarnet.edu.au](https://cloudstor.aarnet.edu.au/);

2. Login with your UTS credentials by selecting your institution (you need to search for "University of Technology Sydney" and not "UTS");

3. Accept the "Terms And Conditions Of Service" (don't worry, they won't sell your data - it's a not-for-profit service funded by the Australian government!).

If you want to take advantage of all the features offered by cloudstor --  including automatically syncing files located on your computer, you can have a look at [this guide](https://support.aarnet.edu.au/hc/en-us/articles/227469547-CloudStor-Getting-Started-Guide).

## Jupyter Notebook

<img src="https://cloudstor.aarnet.edu.au/plus/s/wp8ozshID6Aq2rF/download" alt="jupyter-logo" width="150">
  
**Jupyter Notebook** is a web application that allows you to interact with a document that contains live code.

Jupyter Notebook is part of the *Jupyter Project* which "exists to develop open-source software, open-standards, and services for interactive computing across dozens of programming languages." (https://jupyter.org/)

When you reach a Jupyter web application, you will see something like this
  
![jupyter-dashboard](https://cloudstor.aarnet.edu.au/plus/s/Q3NPc7B5cv5Tuey/download)

At this point you can either create your interactive notebook (in Python or in any other supported programming languages) or open an existing file. A Python notebook is expected to have this extension: `.ipynb`.


### Notebook user interface

*Adapted from [here](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html\#notebook-user-interface).*

![jupyter-notebook-ui](https://cloudstor.aarnet.edu.au/plus/s/1K0ZuFi9rgp6ZgO/download)

* **Menu bar** The menu bar presents different options that may be used to manipulate the way the notebook functions.

* **Toolbar** The tool bar gives a quick way of performing the most-used operations within the notebook, by clicking on an icon. 

* **Code cell** The default type of cell. (But there are also markdown cells and raw cells).

### Structure of a notebook document

*Adapted from [here](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html\#structure-of-a-notebook-document).*

The notebook consists of a sequence of cells. A cell is a multiline text input field, and its contents when the cell is selected can be executed

* by using `Shift-Enter`;
* by clicking the "Play" button in the *toolbar*;
![jupyter-run-toolbar](https://cloudstor.aarnet.edu.au/plus/s/h7zsbwCyYEwfyuo/download)
* by clicking "Cell" -> "Run" in the *menu bar*.

### Code cells

*Adapted from [here]( https://jupyter-notebook.readthedocs.io/en/stable/notebook.html\#code-cells).*

A code cell allows you to edit and write new code, with full syntax highlighting that can help you detecting possible errors. The programming language you use depends on the kernel, and the default kernel (IPython) runs Python code.

When a code cell is executed, code that it contains (as appears in the *display area* of the cell) is sent to the kernel associated with the notebook. The results that are returned from this computation are then displayed in the notebook as the cell's *output*. 

![jupyter-display-area](https://cloudstor.aarnet.edu.au/plus/s/rmzlYGqBYpfXjjC/download)
![jupyter-output-area](https://cloudstor.aarnet.edu.au/plus/s/XbRpPY2mazxBT27/download)


### Code cells

 Finally, the *input area* "is identified by the `In []:` prompt to the left of the cell. Between the brackets of the `In` prompt can be one of three items: *a number*, *an asterisk*, or *a blank*. A number indicates that this cell has been executed and the value of the number indicates the order of execution. For example, normally, after you execute the first cell after opening a notebook, its prompt will read `In [1]:`" (From https://jupyter4edu.github.io/jupyter-edu-book/jupyter.html\#using-jupyter-notebooks).

![jupyter-input-area](https://cloudstor.aarnet.edu.au/plus/s/QonWeNKSwEZ5yJe/download)

### Workflow

With a Jupyter Notebook, there are two possible workflow scenarios:

1. You create new cells and run them (for example, writing your own *project code*);
2. You edit and run existing cells (for example, doing *code exercises*).


#### Workflow for code exercises

When completing code exercises, you'll have your own notebook files where you can edit the code cells.

 It is suggested that before editing the cells, you make a copy of the file by clicking "File"  -> "Make a Copy..." in the menu bar.

After *editing* the code cell, you'll *run* it (see above if you forgot how!) and *inspect the output*. You can also save your edits by clicking "File"  -> "Save and Checkpoint..." in the menu bar (In a notebook, you can revert to different checkpoints that are different versions of the same document.).

If you want to clear all the output of the entire notebook, you can click "Kernel" -> "Restart & Clear Output" in the menu bar.

**Autosave**:  Jupyter Notebook will autosave all the edits you do to the file (and this includes the output after you run a cell). If you want to restart with an unedited file you can either download the original file again or keep a copy of it in your own folder. 

## Cloudstor + Jupyter Notebook = SWAN

A Jupyter notebook will require a *kernel* to offer its interactive features (like running code). A kernel is an engine that executes the code and sends back the results to the user. Again, a notebook is not a simple document; it's an interactive document since you can run *cells* containing code.

  Conveniently, cloudstor offers that kernel with **SWAN** (Service for Web-based ANalysis).

![swan-logo](https://cloudstor.aarnet.edu.au/plus/s/musvpeY3OfhnAdF/download)

To access SWAN from cloudstor, you need to

1. Point your browser to https://cloudstor.aarnet.edu.au/ and login;

2. Click on the SWAN button in the toolbar of cloudstor's web interface; ![swan-toolbar-button](https://cloudstor.aarnet.edu.au/plus/s/TdxJNpwKPiO0i9N/download)

3. Click on "Go to my Notebooks";

4. Locate the notebook that you want to run among your files and click on it. 

Your notebook is now running and you are presented with the Jupyter Notebook web interface. 
