---
title: Introduction
category: understanding-python
order: 1
permalink: "/understanding-python/introduction"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-01-introduction.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

## What's Python?

Python is a *programming language*. With a programming language you define a *set of instructions* for a machine to execute. Sometimes, a set of instructions written in a programming language is a computer program, a.k.a. **code**.

There are two separated actions and two different actors here: 
* The first actor is **the coder** (that is, you!). The coder **writes** the code as text contained in some file. 
* The second actor is **the machine** (that is, what sits... well... everyewhere!). The machine **executes** the code written by the coder. 

It is important that you appreciate these two roles and these two actions. Because after you write your code, it is essential that you tell the machine to start executing (or running) your code.  

If you are reading this from an interactive [Jupyter Notebook](https://en.wikipedia.org/wiki/Project_Jupyter#Jupyter_Notebook), after writing or editing a code cell, you can simply press the *run cell* button. 

|![run-jupyter-notebook-cell](https://cloudstor.aarnet.edu.au/plus/s/TBQRCEE8qs7SV1X/download)|
|:--:| 
| *The 'run cell' button in the Jupyter Notebook toolbar.* |

If you are are reading this from a static document such a webpage, you will need to copy and paste (line by line!) the code into an interactive Python console and hit *return* after each line. 


|![terminal-python-shell](https://cloudstor.aarnet.edu.au/plus/s/US19MEsgf8i4oP1/download)|
|:--:| 
|*An interactive Python console waiting for your code!*|


|![spider-ipython-console](https://cloudstor.aarnet.edu.au/plus/s/oOCdKjc5BjOtYS2/download)|
|:--:| 
|*And the iPython console in [Spyder](https://www.spyder-ide.org/).*|


## A very simple set of instructions: the print() function

It's now time to see some actual code in action. In the following line of Python code, we ask our machine to print the *string* (that is, a sequence of characters): `Replace this string with your favourite quote!`. 


```python
print('Replace this string with your favourite quote!')
```

If you run it, the code line `print('Replace this string with your favourite quote!')` involves the *function* `print()` and the argument `'Replace this string with your favourite quote!'` (if you haven't changed it...), which is passed to the function. The function `print()` doesn't do much. It takes an argument and prints it out. 

## Data, data types and variables

A computer program sets instuctions to manipulate *data*. And data mostly have a specific *data type*. Data types (or better the wrong data type) is possibly responsible for 90% of all bugs. (Actually, I just made that figure up... But it's a lot!) If you pass the wrong data type to a function, the function will complain with an error message.

To use data in different in different parts of a program, it is common to assign data to *variables*. And let's think of data here as small (that is, human-manageable) bits of information or a value. A variable is defined by a name so that every time you call that name the value stored in the corresponding variable shows up. 

In the following example, we assign the value `"dog"` to a variable named `my_variable` with the *operator* `=`. (By the way, in Python, you can either use `"` or `'` to define a string).


```python
my_variable = 'dog'
print(my_variable)
```

**GEEKY INSIGHT:**  A variable is only *a name* and *a reference* to some value stored somewhere in the computer memory. That is, a variable is *not* its the value. 

You can also interrogate your machine about the data type of the variable with the function `type()`.


```python
type(my_variable)
```

Another common family of data types are the *numeric data types*. The most common numeric data types are *integers* and *floats*. 

A simple example, will clarify what you they are.


```python
room = 237
type(room)
```

but if we divide the value `237` by `2` (by using the operator `/`) and assign the result to our variable, we get a float data type.


```python
room = 237 / 2
type(room)
```

## Excercise

Let's try a small exercise now. 
1. Assign your age (or whatever age) to the variable `my_age`;
2. Assign the value `7.5` to the variable `human_2_dog_age`;
3. Assign your dog age by defining a variable `my_dog_age` where you divide `my_age` by `human_2_dog_age`;
4. Finally, print the your `my_dog_age`!
(Replace the `_____` in the cell below before running the code!)


```python
my_age = _____
_____ = 7.5
my_dog_age = _____
print(_____)
```
