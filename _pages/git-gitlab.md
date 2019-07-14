---
title: Git and GitLab
category: getting-started
order: 3
permalink: "/getting-started/git-gitlab"
last_modified_at: " July 14, 2019"
---

## Git

**Git** is a version control system for *text files* (Yes, it can also track *binary* files (that is, non-text files)... but it is mainly used track text files!)

Git is extremely popular among computer programmers to facilitate collaboration and incremental software development.

That is, if you'll ever need to work with a computer programmer it is very possible you'll need to collaborate with her via GitHub (owned by Microsoft, 37M users) or GitLab (open-source), two of the most popular web-based services that use Git.

It is a good idea to have an basic understanding of what is Git and how it works (and also nice to have it on your CV!). 

  But first, what's actually a text file?

### What's a text file?

  Generally speaking, on your computer (and on every other computer around you) there are two types of files: *text files* and *binary files*.

A *text file* is a file that when opened with any text editor will be human-readable: characters ordered in lines.

A *binary file* is a file that when opened with a text editor will make no sense to most of us.

A *text editor* is a "computer program that edits plain text" ([Wikipedia](https://en.wikipedia.org/wiki/Text_editor)). Popular text editors are **Notepad** ![notepad-logo](https://cloudstor.aarnet.edu.au/plus/s/hFcLBRAYDYwudhw/download) (Microsoft Windows) and **TextEdit** ![textedit-logo](https://cloudstor.aarnet.edu.au/plus/s/MM3N9769Oypp4ZL/download) (macOS).


### Is a Word file a text file?

No, it is not.

Although a Word file looks like a text file when opened in Microsoft Word, it is actually a collection of multiple files packaged together.

For this reason, Git is definitely not ideal to track changes (and versions) of a Word file.
  
### Git, how to understand it

So how do we understand Git?

It is useful to consider Git as a computer program to maintain a systematic list of

1. **Changes** to a text file -- so different *chronological versions* of the same file.

2. **Parallel versions** of a text file -- so different *synchronous versions* of the same file.

Wait, what?

### Welcome to Git

Let's step into Git-world and see if we can make sense of it.

We'll introduce key **Git terminology** and basic `git command`s.

Commands are actions that you command git to take. For example, 

```bash
git init
```

will *initiate* a new git repository in the current directory.

So, what's a repository?

### Repository

In Git-world everything is contained by a *repository*, or a *repo* for short.

You can think of a Git *repository* as a directory with a bunch of files and subdirectories. If you decide to use Git for your project, a *repository* will likely contains all your files.

![directory](https://cloudstor.aarnet.edu.au/plus/s/C6eKuGrAcxY4Vju/download)

### Chronological versions of a file (Git workflow)

![file](https://cloudstor.aarnet.edu.au/plus/s/E5guLK824ofJABx)

Let's say that you have a file `my_file.txt` that you want to track. 

You can *add* the file to your *repository* simply with

```
git add my_file.txt
```

And every time you want to *commit* a new version of the file to your *repository* you do

```
git commit
```

### Parallel versions of a file (Git workflow)
Now let's say that both Alice and Bob wants to work on the same file *at the same time*.

| ![](https://cloudstor.aarnet.edu.au/plus/s/KjEsTFLjzTmObEZ/download)  | ![](https://cloudstor.aarnet.edu.au/plus/s/m0dAPbE5SPPAzKX/man)  |
|---|---|

Both can then create a *branch* of the project with

```
git checkout -b my_branch
```

and finally *merging* it into the same project with

```
git merge my_branch
```

## GitLab

![gitlab-logo](https://cloudstor.aarnet.edu.au/plus/s/iPsmMSDEnIjCW5o/download)

**GitLab** is a Git-repository hosting and management service. It offers a number of features such as managing *projects* (members, wikis, discussions, etc.), *Git repositories*, *issues* and *merge* requests.

You might want to create a GitLab profile to store and publish your code portfolio. You can also opt to use the very similar *GitHub* ([github.com](https://github.com/)) instead, but GitLab UTS will offer you the option to keep your repositories private, something that on GitHub is only an option for pro users. 

### 1. How to create your GitLab profile
  To create your own GitLab profile you need to visit [code.research.uts.edu.au/users/sign\_in](https://code.research.uts.edu.au/users/sign_in) and enter your UTS credentials.

  After creating your profile, you can create a new project or *cloning* an existing Git repository into your new project.

**Project or Repository?**: In general, we can consider *projects* and *repositories* to be the same thing: A project is a repository and a repository is a project. Yet, in GitLab projects adds additional features to a standard Git repository, so a project will be a repository plus something.


### 2. How to create a new project

1. From your GitLab dashboard, just click on "New project".

![gitlab-new-project](https://cloudstor.aarnet.edu.au/plus/s/LXjMIVSf5iKbzVX/download)

2. In the "Blank project" tab, enter a "Project name" and decide if your project is going to be "Private" (only authorised users can access it), "Internal" (every UTS users can view it) or "Public" (everyone can view it).

3. Finally, click on "Create project" and your done! (Your repository is empty though: you'll need to add your files).
  

### 3. How to clone an existing repository into a new project

Among the most powerful features of Git there is *cloning*. *Cloning* is different from *branching* as it creates an independent repository that you can manage and modify as you see fit.

1. From your GitLab dashboard, again click on "New project".

2. Now select the "Import project tab" and click on "git Repo by URL".

![gitlab-clone-repository](https://cloudstor.aarnet.edu.au/plus/s/LWUsHoDjjoK6anO/download)

3. You need now to enter this URL in the "Git repository URL": (for example, `https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks.git`, but the point is: it can be any URL pointing to a *Git repository*!)
    
4. Since you are also creating a new project, you need to define its "Project name" and "Visibility level" as before.

5. After clicking on "Create project", GitLab will take care of cloning the project. After that, you can inspect the files that have been added to your project and that you can now modify. 

### 4. How to use GitHub Desktop with GitLab

![github-desktop-logo](https://cloudstor.aarnet.edu.au/plus/s/Lo7cb7ZVnuFN4yk/download)

The GitLab web interface allows to manage and edit your project files directly from your browser. Still if your project involve code, you might want to also be able to edit and run your files locally on your machine.

**GitHub Desktop** (available for both macOS and Windows) facilitates synchronising your local *Git repository* with GitLab (or clearly GitHub.com).

You can refer to [this page](https://help.github.com/en/desktop/getting-started-with-github-desktop/installing-github-desktop) to download and install GitHub Desktop (which is free).

Once GitHub Desktop is installed you will need to add a Git repository. You now have three options:

1. Clone an existing repository;
2. Create a new repository;
3. Add an existing repository.

Let's clone our existing repository hosted on GitLab. 

#### Cloning a GitLab repository with GitHub Desktop

To clone a GitLab repository, you will need to indicate a directory on your computer where to store the repository ("Local path") and crucially the URL of the existing repository on GitLab (or wherever) you want to *clone*. To get the URL of your GitLab repository, you can simply copy the URL you see in your browser when you are on the project and add a `.git` to its end.

![github-desktop-clone-repository](https://cloudstor.aarnet.edu.au/plus/s/Eck9FjCzFTYNyiH)

 The URL will be something like `https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks.git`, but instead of `143852` your UTS number and instead of `code-as-literacy-jupyter-notebooks` the slug identifying your project.

#### Commit and push changes to GitLab with GitHub Desktop

Once you have created the local repository, which is linked to the online repository, every time you modify a file and after you *commit* its new version with the "Commit to master" button, you can *push* the new version to the online repository for everyone to see. Just remember that you will need to authenticate with your UTS credentials.

![github-desktop-commit-push](https://cloudstor.aarnet.edu.au/plus/s/gNIlwUfB1aiyok3/download)

![github-desktop-authenticate](https://cloudstor.aarnet.edu.au/plus/s/gNIlwUfB1aiyok3)
