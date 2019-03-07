---
title: Working with log-ins
category: django
order: 
permalink: "/django/working-with-log-ins"
last_modified_at: "July 26, 2018"
---

**Type out these login exercises in IDLE then save and run them.**

## Exercise 1

``` python
# Allowed users to login
allowed_users = ['bill', 'steve']
     
# Get the username from a prompt
username = input("What is your login? : ")
     
# Control if the user belongs to allowed_users
if username in allowed_users:
	 print ("Access granted")
else:
	print ("Access denied")
```
Let's talk about Exercise 1. Can you explain how python is interpreting and understanding data inputs and presenting information?

## Exercise 2

``` python
import sys
while True:
	print('Type exit to exit.')
	response = input()
    if response == 'exit':
		sys.exit()
	print('You typed ' + str(response) + '.')
```
 
**What is happening in Exercise 2? Check out [this page](https://stackoverflow.com/questions/5605299/what-do-these-python-import-statements-mean) for some initial help.**
