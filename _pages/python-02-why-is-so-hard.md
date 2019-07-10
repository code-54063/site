---
title: Why is coding so hard?
category: understanding-python
order: 2
permalink: "/understanding-python/why-is-so-hard"
last_modified_at: " July 10, 2019"
---

*This page is also available as Jupyter interactive notebook. Download it from [here](https://code.research.uts.edu.au/143852/code-as-literacy-jupyter-notebooks/blob/master/understanding-python/python-02-why-is-so-hard.ipynb) and run it in your [cloudstor](/getting-started/jupyter-notebook).* 

> "If debugging is the process of removing software bugs, then programming must be the process of putting them in." ([Edsger Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra))

|![coding-movies-vs-real-life.gif](https://cloudstor.aarnet.edu.au/plus/s/iu3IKGx8oxsQAIb/download)|
|:--:| 
| *Programming: in movies vs in real life.* |

Programming is frustrating because is hard. What set members of our species (that is, *Homo sapiens*) apart from any other animal species is our capacity to communicate very complex and sophisticated ideas to other fellow humans beings. We know that during the last 1.8 million years, the regions of our brain that have being growing the most are the regions associated with problem solving, depth of planning and *communication* (Hawks 2013). Still, the kind of communication we excel at is the *human-to-human* communication. But coding is about *human-to-machine* communication (and, in some sense, also *machine-to-human* - for example, when we get some obscure error message from our computer...).

When we try to switch from *human-to-human* to *human-to-machine* communication, we face at least three huge challanges. 

1. Human-to-human communication is rule-based (clearly, we do share both a common grammar and vocabulary) but these rules are constantly streched, bended and adapted to our communicative needs. In fact, "All grammars leak" (Sapir 1921, p. 23). **In human-to-machine communication, we can't bend the grammar**.  

2. In human-to-human communication, sender and receiver share a *common sense*, which allows us to save a lot of time by keeping a lot of information implicit. **In human-to-machine communication, we need to make everything explicit.**

3. Finally, human-to-human communication is characterised by a high level of *abstraction* as we rather prefer dealing with ideas than with ordered events and facts. **In human-to-machine communication, we need to [reify](https://en.wikipedia.org/wiki/Reification_%28computer_science%29) our ideas as precisely as (humanly) possible.**

## Infinite loops

A famous example can hopefully help you understand the nature of the challange number 2. Let's say that you find the following instruction on a bottle of shampoo: **lather, rinse, repeat**. We can safely say that the point of the instructions is not to *endlessly repeat* lathering and rinsing since it is assumed that you will need to stop, eventually. But of course no stopping event is explicitly coded in the instructions. 

|![shampoo-how-to-use.png](https://cloudstor.aarnet.edu.au/plus/s/DfiVVPE8Fsl3TZw/download)|
|:--:| 
| *Lather, rinse, repeat: Any problem with these instructions?* |

In Python, that set of instructions will look like this: 

```python
while True:
    lather()
    rinse()
```

If you execute this lines as they are, you will get an error as `lather()` and `rinse()` are not probably not defined in your environment. But let's say that we define both functions with the following code: 


```python
def lather():
    print("Lathering...")
    
def rinse():
    print("Rinsing...")
```

After executing the previous cell (where we define with `def` `lather()` and `rinse()`) by clicking on it and then pressing the `►|` button, we can now try to see what happens when we run the following cell where our two functions are within a `while` loop...


```python
while True:
    lather()
    rinse()
```

What happens is simple: your interpreter will execute `lather()` followed by `rinse()` forever since. That is, until you don't stop the execution by pressing the `■` button. (And after that, you might also want to clear all output with "Cell" -> "All Output" -> "Clear".) In this case, what controls the loop is the `while` statement, which we set to `True` (change `True` to `False` and nothing will happens...) determining that it will run until something happens *within* the loop.

What we don't specify in that loop is a way to *eventually* break the loop; simnply, there is no way that your intepreter will assume it will need to break it, eventually. We need to make that explicit by adding a `break` statement following some specific event, for example after five series of `lather()` and `rinse()`.


```python
completed_cycles = 0
while True:
    lather()
    rinse()
    completed_cycles = completed_cycles + 1
    print("Cycles completed: " + str(completed_cycles))
    if completed_cycles >= 5:
        break
```

In the previous cell, we create a variable `completed_cycles` that keeps track of the number of completed cycles (or loops) and that we initialise with the value `0`. Every time we complete a cycle, we add one to the variable with `completed_cycles + 1` which is immediately assigned to the same variable `completed_cycles`. The final step is add a logical test: if `completed_cycles` is equal or larger than five, we `break` the `while` loop.

## Break down the task

Challange number 3 (abstraction vs reification) can be another very significant problem. Here the problem is not a lack of common sense on the machine-side. It's more about the machine lack of creativity and problem-solving capacity (don't expect any!). For example, let's say your hear a friend of yours saying: "Let's go to Paris!". You immediately realise that, first, she doesn't mean let's go to Paris right now, but possibly in a few days, weeks or even months. Second, you also realise that in order to reach Paris, you will need to break an abstract idea (going to Paris) into practical steps that can be individually executed. In the language of computer science you will need to *reify* (from the Latin *res*, which means "thing") your friend's idea.

So for example, in order to go to Paris some of the practical steps that we will need to orderly complete are: getting a passport before getting a visa or buying a ticket to Paris before boarding a plane to Paris. But how do you *practically* get a passport? Well, you need to get a photo, go to the Post Office, pay, etc. As you see, every task can (and must) be broken down into multiple subtasks for a machine to be able to execute it. Considering this, it won't be surprising anymore to know that an average high-end car runs on petrol but also on approximately 100 million lines of code and that Google runs on billions of lines of code. 

So when do we stop in breaking tasks into smaller components? Simply put you stop writing new functions when you have found an existing function that does exactly what you need. That is, if you are lucky and find the code for the function `goToParis(passenger_name, passenger_location, date)` you don't need to write a sigle line of code.

**GEEKY INSIGHT**: From [Wikipedia](https://en.wikipedia.org/wiki/Reification_%28computer_science%29): "By means of reification, something that was previously implicit, unexpressed, and possibly inexpressible is explicitly formulated and made available to conceptual (logical or computational) manipulation."

So, as you start coding, brace yourself for a constant flow of errors (and when you meet any, remember the four most important words you'll ever read about computer programming: "Google is your friend!"). It is not you. It the fact that you are working at the human-machine boundary. It's exciting, but also very hard. To give you a preview, in the follwing sections you can taste some of the most frequent programming errors. 


## The most common bugs in Python

**Note**: This section is adapted from Mueller and Massaron, 2019.

### Code indentation

In Python you need to indicate a block of an `if-else` statement, a `while` statement or others, by precisely indenting their lines of code. The line of the block starting with `if`, `else` or `while` will need to be (by convention) 2 or 4 spaces to the left of the other block lines.  

For example,


```python
# Code adapted from Gaddis, 2019
temperature = 5
if temperature < 15:
    print("A little cold, isn't it?")
print("Turn up the heat!")
else:
    print("Nice weather we're having.")
    print("Pass the sunscreen.")
```

will throw a very common `IndentationError`. Can you correct it and re-run the cell? You can also set the `temperature` to a different value to try to execute the `else` block. 

### Assignment operator and the equality operator

The assignment operator `=` assigns a value to a variable. In the previous example `temperature = 5` assigned the value of `5` to a variable named `temperature`. The equality operator, which is a logical operator used to compare two values, is instead composed by two equal signs: `==`. 


```python
temperature = 10
print(temperature)
temperature == 10
```

which returns `True` because 


```python
10 == 10
```

is also `True`. But, if we use `=` instead of `==` 


```python
if temperature = 5:
    print("It's cold!")
```

we get a `SyntaxError`. Can you correct it and re-run the cell?

### Logical operators

In Python, as in most of the programming languages, when writing a logical statement with multiple *operands*, there is a difference between `and` and `or`. In `temperature > 5 and temperature < 10`, `and` indicates that *both* operands must be `True`, so to be true the `temperature` must be higher than five `and` lower than ten. Instead, in `temperature < 5 or temperature > 10`, either one or the other operand (or possibly both, which is of course not possible in this case) must be `True` for the statement to be `True`. 

### Spelling

Check your spelling! Spelling errors are by far the most common errors (followed by assuming the wrong variable type...). If you mistype a function or variable, you will be told that the mispelled version of it `is not defined`. For example,


```python
prnt("Check your spelling!")
```

And also remember that Python interpreters are *case sensitive*. So `VARIABLE` is different from `Variable` that is different from `variable`.

## References

Gaddis, T., 2019. Starting out with Python, Fourth. ed. Pearson, Harlow. URL to the 2018 edition http://find.lib.uts.edu.au/?R=OPAC_b3297555 

Hawks, J., 2013. "How has the human brain evolved?". *Scientific American*. URL https://doi.org/10.1038/scientificamericanmind0713-76b

Mueller, J.P., Massaron, L., 2019. "The 8 most common Python programming errors". *Python for data science for Dummies cheat sheet*. URL https://www.dummies.com/programming/python/the-8-most-common-python-programming-errors/

Sapir, E., 1921. *Language: an introduction to the study of speech*. Andrews UK Limited, Luton. URL https://ebookcentral.proquest.com/lib/uts/detail.action?docID=4460679
