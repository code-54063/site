---
title: Functions
category: understanding-python
order: 5
permalink: "/understanding-python/functions"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-05-functions.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

Functions are essential components in computer programs. They allow to define the details of a single task made of multiple statements. The task will be executed every time the corresponding function is called. Functions have at least two important benefits:

1. Functions allow to write the instructions for a task only once even if the task needs to be executed multiple times.
2. Functions increase the clarity of your code: they are confined blocks of code that are small enough to be easily understood independently of the rest of your code. 

Optionally, a function can take some *input*, which are generally refers to as *arguments*, and return some *output*. Again, a function doesn't need necessarily to have input and output: a function can also execute without requiring any additional information and without producing any information. 

In Python, the syntax to define a the block of a function is

```python
def my_function(my_argument1, my_argument2, etc.):
    statement 1
    statement 2
    return 
```

where `my_function` is the name of the function, which is used every time we need to call it, `my_argument1` is one of the arguments (generally, some value) that we pass to function to be processed. Finally, by convention we use the `return` command at the end of the function also if we don't want to return any value after the execution of the function.

## A simple function

Let's say I want to write a function to greet someone (yes, generally you will only define functions for more complicated tasks, buyt bear with me...). I already know that to combine two strings I simply need to add them: so `'cat' + 'tle'` will result in `'cattle'`. So this is going to be my function


```python
def greet(name, message):
   print('Hello ' + name + ', ' + message)
   return
```

The function takes two arguments: a `name` and a `message`. As you see, after `print()`ing the message the function `return` without passing back any value. After running the previous cell, you can test the function with the following code


```python
greet("Pauline", "how are you?")
```

## A function returning something

Now let's say that I need a function that will compose the same greeting message as before but instead of printing the message out, it will return it a string value. I can simply modify the function such that I store the message in a variable called `my_message` and then I return the value of that variable.


```python
def greet(name, message):
   my_message = 'Hello ' + name + ', ' + message
   return my_message

returned_value = greet("Pauline", "how are you?")
```

the previous cell will not output anything (there's not a `print()` statement anymore!) Still, if I run the following I get my message back...


```python
print(returned_value)
```

## Exercise

Can you complete the following code so that the function will add two numbers and print the solution?


```python
# Here you define the function
def sumTwoNumbers(num1, num2):
    result = ____ + ____
    print("The result is " + ____)
    
# Here you call the function    
sumTwoNumbers(34, 86)
```

Did you get an error such as `TypeError: Can't convert 'int' object to str implicitly`? Remember that you can't concatenate a string to a number. You need to convert the number to a type string first with `str()`.

## Additional resources

- [Python functions](https://www.lynda.com/Python-tutorials/Python-functions/661773/707224-4.html?org=uts.edu.au) on Lynda.com.
