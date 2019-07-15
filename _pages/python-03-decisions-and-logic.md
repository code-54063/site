---
title: Decision structures and boolean logic
category: understanding-python
order: 3
permalink: "/understanding-python/decisions-and-logic"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-03-decisions-and-logic.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

## Relational operators and boolean expressions

*Relational operators* are essentials to create *decision structures*. A decision structure can be represented by a simple flow chart. In this example, we test the logical statement "the lamp is ON". `if` the statement is `False` we do something ("turn lamp ON"). `if` the statement is `True` we don't do anything. In computer science, a statement that can be either `True` or `False` is called a *boolean expression* (from George Boole, a mathematician).

|![flowchart.png](https://cloudstor.aarnet.edu.au/plus/s/G956mXPYyR1aToZ/download)|
|:--:| 
|*A simple flow chart*| 

In Python there are seven relational (or comparison) *operators*. These same operators are also used in many other computer languages. They are used to compare the values of two *operands*: one at the left of the operator and one at its right. It is now easy to think at the operands as numerical variables (let's say `a = 10` and `b = 20`) but in Python also strings can be compared. 

| Relational operator | Meaning | Boolean expression |
|:--:|:--:|:--|
| `>`  | Greater than | `a > b` is `False`|
| `<`  | Less than | `a < b` is `True`|
| `>=` | Greater than or equal to | `a >= b` is `False`|
| `<=` | Less than or equal to | `a <= b` is `True`|
| `==` | Equal to | `a == b` is `False`|
| `<>` | Not equal to | `a <> b` is `True`|
| `!=` | Not equal to | `a != b` is `True`|
|*Relational operators and exaples with `a = 10` and `b = 20`.*|
|*Note: `!=` is similar to `<>`, but `!=` is more common*|

## The if statement

Relational operators can be used in an `if` statement. In Python, an if statement is defined with a block of at least two lines. The first line contains the *condition* - a logical statement - that will be tested by the interpreter. The statements in the lines below the first line that are indented will be executed only if the *condition* in the first line is `True`. 

```python
if condition:
    statement 1
    statement 2
    etc.
```

## The if-else statement

The `if`-`else` statement simply details what statements to execute `if` the *condition* in the first line of the block is `False`. 

```python
if condition:
    statement 1
    statement 2
    etc.
else:
    statement 3
    statement 4
    etc.
```

In the previous example, `statement 3` and `statement 4` are executed by the intepreter only if the *condition* in the first line is `False`, in which case `statement 1` and `statement 2` are *not* executed. Simple. Just be careful to the indentation!


## Exercises

In the following cells, replace `____` so that the intepreter will always print `yes`.


```python
a = ____
b = ____
if a == b:
    print('yes')
else:
    print('no')
```


```python
a = ____
b = ____
if a <= b:
    print('yes')
else:
    print('no')
```


```python
a = ____
b = ____
if a != b:
    print('yes')
else:
    print('no')
```

## Additional resources

- [Conditional structures](https://www.lynda.com/Python-tutorials/Conditional-structures/661773/707225-4.html?org=uts.edu.au) on Lynda.com.
