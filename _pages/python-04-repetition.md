---
title: Repetition structures
category: understanding-python
order: 4
permalink: "/understanding-python/repetition"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-04-repetition.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

Sometimes, we want to programmatically reapeat the execution of some statement until some condition doesn't change or a specific number of times. A typical situation is adjusting the music volume. In that case, we keep increasing the volume by pressing a button or turning a knob until the volume is just right. The following figure presents a flow chart with a condition and a statement representing that situation. The condition is revaluated every time we adjust the volume (our statement) and only if the condition is found to be `False` we stop executing the statement.

|![while-loop.png](https://cloudstor.aarnet.edu.au/plus/s/4fASCZxa2TfbgK7/download)|
|:--:|
|*A loop: we keep increasing the volume as long as we find the volume to be low*|

## The while loop

The `while` command is used to execute a series of statements defined in the following indented lines until the while *condition* is determined to be `False`.

```python
while condition:
    statement 1
    statement 2
    etc.
```

For example, in the following cell we write a `while` loop to increase the `volume` until we reach the right level, which we define being exactly `10`. As you notice, within the `while` loop we have an `if` statement that test the condition `volume == 10`; `if` the condition if `True`, then the value of the variable `volume_is_too_low` is set to `no` - which is different from `yes`, the `while` condition - breaking the loop.


```python
volume = 0
volume_is_too_low = 'yes'
while volume_is_too_low == 'yes':
    print("Increasing the volume...")
    volume = volume + 1
    print("Volume is now " + str(volume))
    if volume == 10:
        volume_is_too_low = "no"
        
```

## The for loop

The `for` loop is useful when we know exactly the number of times we would like to execute a block of statements or, better, we know exactly the values we would like to process in a block of statements.

```python
for variable in [value1, value2, etc.]:
  statement 1
  statement 2
  etc.
```

For example, let's say I want to print the first ten roman numerals. First, I need to create a *list* of string values corresponding to the roman numerals. A list is a common Python object defined by square brackets (`[` and `]`) where to store multiple items. 


```python
roman_numerals = ['I', 'II', 'III', 'IV', 'V', 'VI', 'VII', 'VIII', 'IX', 'X']
```

Then I write a `for` statement to pass each item of my `roman_numerals` - one at a time - to the statement in the `for` loop. (Remember to run the previous cells *before* running the next cell or the intepreter will not find your `roman_numerals`!)


```python
for this_roman_numeral in roman_numerals:
    print(this_roman_numeral)
```

What's going on here? In the block we see two variables. The first variable is the list `roman_numerals`, which we initialised before. But what's the value of `this_roman_numeral`? Well, the value of `this_roman_numeral` is different in every iteration of the `for` loop. It assumes the value `I` during the first iteration, `II` during the second iteration and so on until it assumes the value `X` in the last iteration. In general terms, every `for` statement can also be read like this: 

```
Dear interpreter,
For every individual item you find in  this object, 
please do something. 
Sincerely,
The Coder.
```

As a matter of fact, you don't need to use the individual items at all in your `for` loop. Indeed, it is very common to use the object in the `for` statement as a counter. So if I want to print `cat` ten times I can simply do


```python
for i in [1,2,3,4,5,6,7,8,9,10]:
    print("cat")
```

or for the sake of brevity replace `[1,2,3,4,5,6,7,8,9,10]` with `range(10)`, a Python function that returns all the numbers in the range 0 to 10 (this excludes the first one, which is 0).


```python
for i in range(10):
    print("cat")
```

## Exercise

Complete the following code so to print `dog` exactly five times.


```python
____:
    print('dog')
```

## Additional resources

- [Loops](https://www.lynda.com/Python-tutorials/Loops/661773/707226-4.html?org=uts.edu.au) on Lynda.com.

