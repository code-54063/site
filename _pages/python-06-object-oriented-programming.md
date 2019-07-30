---
title: Object-oriented programming
category: understanding-python
order: 6
permalink: "/understanding-python/object-oriented-programming"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-06-object-oriented-programming.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

Most of the computer languages commonly in used today are *object-oriented*. Object-oriented programming focuses on, well, *objects*. The alternative to object-oriented programming is *procedural programming* which is not so commonly used anymore and focuses on, well, *procedures*. A procedure is simply an ordered list of tasks or functions: simply put, "a series of computational steps to be carried out" ([Procedural programming on Wikipedia](https://en.wikipedia.org/wiki/Procedural_programming)). An object is instead a *entity* that contains both procedures and data (or the entity's attributes). The key benefit of dealing with objects is that objects, like functions - which in fact are also objects, are defined once and used as many times as necessary. Python is an object-oriented language.

Yes, but in practice what is an object? Let's consider a website such as Facebook, which in December 2018 had 2.3 billion monthly users. We can assume that the software that runs Facebook (which was coded using PHP, an objected-oriented language) defines a *class* called `User` and that the 2.3 billion users will be represented by Facebook as 2.3 billion different objects of the same class `User`. The class `User` will define (only once) a number of attributes and functions that each object of the class `User` will automatically inherit. 

In Python, we can create a simple class `User` defining three attributes (`name`, `age` and `sex`) and three class *methods* (or functions) `status`, which will update the status of the user, `online` and `offline` to declare that the user is either online or offline. 


```python
class User():

    # Class User attributes 
    def __init__(self, name, age, sex):
        self.name = name
        self.age = age
        self.sex = sex
        
    # Class User methods    
    def online(self):
        print(self.name + " status is now online.")
        
    def offline(self):
        print(self.name + " status is now offline.")
        
    def status(self, status):
        print(self.name + " status is now '" + status + "'.")
```

Once the class is defined, we can create as many users as we like.


```python
John = User('John', 18, "male")
Alice = User('Alice', 22, "male")
```

Once the the two users are finally created, we can used the method defined for that specific class.


```python
Alice.online()
```

## Exercise

How would you set the status of John to `Driving home`?


```python
John._____
```
## Additional resources

- [Classes](https://www.lynda.com/Python-tutorials/Classes/661773/707227-4.html?org=uts.edu.au) on Lynda.com

- One of the best [lecture on object-oriented programming and classes](https://youtu.be/nWheM30THaY) you will find anywhere (by Professor Mehran Sahami for the Stanford Computer Science Department)
