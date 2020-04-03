# TechForNonTechies

## Prerequisites

* No background in programming required
* No software needs to be installed. All coding is done using [repl.it](https://repl.it).
* Programming will be done in Python

## Goals

* A whistle stop tour of the life a program
* Give the absolute basics of programming
* Each class broken up into two sections:
	* Background
	* Coding tutorial
* At the end you should be able to call an API and do something with the response
* Teach programming concepts while teaching standard practices within Mastercard

## Week 1

Note: Look at Harvard CS50 for sample course outline


### The Basics

### What is a computer?

### What is an operating system?

#### A brief history and the Pirates of Silicon Valley

Introduction to the early OS wars involving Xerox, Microsoft, Apple, IBM, etc.

#### Components of an OS

* Kernel
* Interrupts
* Memory management
* Thread management
* File organization
	* Command line exercises to navigate the directory tree
* User interface



### What is a program?

### Programming languages

* Common characteristics of programming languages
	* We can focus on Python language features since we're going to be doing exercises
	* Compare python with other languages (e.g. C++, Java, Ruby)
	* Explain what domains each language might be used for (C++ embedded systems, Java microservices, Javascript front end web pages, Python + data science / ML)
	* Exerices related to this?
		* Match a code snippet with functionality / feature
		* Identify the language feature (e.g. For Loop, function definition)
* Type systems
* Compilers

Week 1
 
# Variables

Some paragraph defining this

## How to declare a variable?

Some example

## Some other section

* Variables
	* Types
		* Primitives
			* What is a primitive?
				* Has to do with how the data is retrieved from memory
				* Basic building blocks of all applications
				* Create new data types (objects) out of these primitives
			* Integer
			* Boolean
			* Float
			* String
		* String
			* Some languages consider String a primitive, some don't
		* Collections
			* List
			* Array
			* Dictionary
			* Tuple
			* Set
* Operators
	* Mathematical
		* +
		* -
		* *
		* /
		* \**
		* %


Week 4

* HTTP requests / responses
	* Calling the Mastercard API
	* Final project


### Exercises
See appendix

#### Quizzes
* Simple quizes to reinforce the information presented
* Quiz before and after each session?

#### "Hello world"

#### Input and Output

Implement in python, but show implementations in other languages e.g. C, Javascript, R, Erlang, to cover different programming paradigms, OO, Functional, Logical, Procedural



## Week 2

### Recap and looking ahead

In week 1 we were introduced to primitive data types, collections, and mathematical operators.

This week we will explore two other types of operators and how we can use them to control the flow of our program. We will then take a look at a special control specifically designed for collections.

The topics covered this week include:

* Comparison Operators
* Logical Operators
* Control Structures
* Conditionals
* Loops

### Operators

#### Review: Arithmetic Operators

Arithmetic operators typically take two numeric operands and return a result of the specified operation.

Example:

```python
val = 5 + 7	# operator is +; left operand is 5; right operand is 7
```

One special scenario to consider is when using the addition operator to concatenate two strings.

Example:

```python
result = "Hello, " + "world"

print(result)	# prints "Hello, world"
```

#### Comparison Operators

Comparison operators, sometimes called relational operators, also take two operands which are often numeric. The main difference from arithmetic operators is that these operators test the relationship between (compare) the operands and return a `boolean` value, either `True` or `False`

These operators enable our programs to make decisions based on certain conditions for which they can test.

Example: To enforce parental controls, a program might check that the current time is earlier than 9pm before granting a user (the parents' child) access, or;

To authorize an incoming API request, we need to validate that the request token was issued by Mastercard.

Similar to the `+` operator used to concatenate two strings, some comparison operators can be used to compare strings as well as numbers.


Operator	|	Description			            | Example
----------|----------------------------------|---------
   `==`   | Is the left operand equal to the right operand?		     | `1 == 2` returns `False` <br> `"hello" == "hello"` returns `True` <br> `"1" == 1` returns `False`
   `!=`   | Is the left operand *not* equal to the right operand?      | `1 != 2` returns `True` <br> `"hello" != "hello"` returns `False`
   `>`    | Is the left operand greater than the right operand? | `5 > 5` returns `False`
   `>=`   | Is the left operand greater than or equal to the right operand? | `5 >= 5` returns `True`
   `<`    | Is the left operand less than the right operand? | `5 < 5` returns `False`
   `<=`   | Is the left operand less than or equal to the right operand? | `5 <= 5` returns `True`

There are two special operators used to test equality in a very specific way. We'll return to these next week.

Operator  |  Description                        | Example
----------|-------------------------------------|---------
  `is`    | Is the left operand the same object as the right operand? |  `p1 = {"name":"Bret"}` <br> `p2 = {"name":"Bret"}` <br> `p1 == p2` returns `True` <br> `p1 is p2` returns `False`
  ` is not` | Is the left operand *not* the same object as the right operand? | `p1 != p2` returns `False` <br> `p1 is not p2` returns `True`
  
  
#### Logical Operators

Logical operators, sometimes called boolean operators, take either one or two `boolean` operands and return a `boolean` result. 

These operators allow us to make decisions in our program based on *multiple* conditions which may change over time. A logical operator can take the result of a comparison and combine it with the result of another comparison to return a new result.

Operator    | Description               | Example
------------|---------------------------|----------
  `and`     | Are the left operand *and* the right operand both `True`? | `True and True` returns `True` <br> `True and False` returns `False` <br> `False and False` returns `False`
  `or`      | Is either the left operand *or* the right operand `True`? | `True or  True` returns `True` <br>  `True or False` returns `True` <br>  `False or False` returns `False`
  `not`     | Is the inverse of the operand `True`? | `not True` returns `False` <br> `not False` returns `True`

### Control Structures

Control structures determine the execution flow of your code and enable a program to change its behavior based on its current state. State can change due to any number of reasons including user input, time of day, network avaialability, and navigation. This means your program can respond to state changes and prevent unexpected behavior.

#### Sequence

By default, all of your code is executed sequentially, with each line executing in the exact order in which it's written. A program written this way will always execute the same code no matter what happens. This works fine for very simple programs with predetermined and guaranteed state.

```python
# A simple program which will always work when executed sequentially
x = int(input('Enter a number: '))
y = int(input('Enter another number: '))

print(f'Sum of {x} and {y} is {x + y}')
```

#### Selection

If your program needs to behave differently dependending on its current state, you can introduce **conditional statements** to allow your your program to *select* flows of exeuction for different states.

For more complex programs (99.9999% of all software), you will need to ensure that the program behaves correctly by evaluating its current state and choosing what to do next.

##### `if` Statements

In Python, selections are written in the form of `if-elif-else` statements. 

`if` statements are given a `conditional expression` which evaluates to either `True` or `False`. If the expression evaluates to `True` the following code block is executed. If the expression evaluates to `False` the block is skipped.

```python
# Only show the time if the user wants to know

show_time = input('Do you want to know the current time (Y/n)? ')

if show_time == 'Y':
    print(datetime.now())   # This is skipped if the user enters 'n'

```

`elif` provides a sort of fallback in case the preceeding `if` evaluates to `False`. This is useful when there are multiple possible outcomes you want to test for. The block following `elif` will executing *only* if preceding `if` and `elif` statements evaluate to `False` and this `elif` statement evaluates to `True`

```python
# Normalize your user input to prevent negative side-effects

num = int(input('Give me a number between 0 and 100: '))

if num < 0:
    num = 0
    print('Your negative number was rounded to 0')
elif num > 100:
    num = 100
    print('Your number was rounded to 100')
    
use_number(num)
```


`else` provides a fallback that is guaranteed to run if all preceeding `if` and `elif`statements evaluate `False`. This is useful if you can't predict all possible outcomes and want to provide a default behavior.

```python
# Enable your program to behave differently according to its input

result = None
x = int(input('Give me a number: '))
y = int(input('Give me another number: '))
op = input('What do you want to do (+, -, *, /, **): ')

if op == '+':
    result = x + y
elif op == '-':
    result = x - y
elif op == '*':
    result = x * y
elif op == '/':
    result = x / y
elif op == '**':
    result = x ** y
else:
    print("I don't know what that means...")
    
if result is not None:
    print(f'{x} {op} {y} = {result}')
    
```


##### More examples

Test whether a number falls between two other numbers

```python
lock_start_hour = 21              #Restrict access starting at 9pm (21:00)
lock_end_hour = 6                 #Remove restriction at 6am (06:00)
current_hour = datetime.now().hour   #Get the current hour

if current_hour >= lock_end_hour and current_hour < lock_start_hour:
    access_allowed() # Access allowed outside of restricted hours
else:
    access_refused() # Otherwise access is refused
    
# Can you spot the bug in this code?
```


#### Iteration

Often times we want to execute the same block of code multiple times. Maybe we have a collection of values that we want to display to the user or we want the user to input an undetermined number of values from the terminal.

When we need to iterate through a collection of items and perform some task, a `for` loop is usually the best choice. If the number of loops required is unknown, we can use a `while` loop provided with a `conditional expression`.

##### `for` Statements

Given a collection of items, a `for` loop enables a program to perform some task on each item in the collection individually.

```python
# Generate average spending of users

users = get_all_users() # Returns a list of all users
total_spent = [] # A collection to hold each user's total ($) spent

for user in users:  # For each user
    total_spent.append(user.total_spent)  # Record each user's total ($) spent

med_spent = median(total_spent)    

print(f'The median amount spent for all users is {med_spent}')
```


##### `while` Statements

A `while` loop continuously repeats a block of statements as long as a given conditional expression evaluates to `True`. This is fundamentally different from a `for` loop, which iterates over the items contained within a given collection.

```python
# Generate a report from recent transactions

trans = []
value = int(input('Enter your recent transaction amounts (-1 to exit):'))

while value != -1:
    trans.append(value)
    
    value = int(input())
    
trans_total = sum(trans)
trans_median = median(trans)
trans_mean = mean(trans)

print(f'Total: {sum(trans)}, median: {median(trans)}, mean: {mean(trans)}')
```


### Programming Exercises

#### Exercise 1: Authentication

Before we grant a user access to our system, they need to sign in to an existing account using the correct username and password combination. This is a very basic form of authentication. 

Write a program which allows a user to input their username and password. Verify that the username exists and that the entered password matches the password associated with this username.

##### Acceptance Criteria

1. If the username entered does not exist, print an error message.
2. If the username does exist, allow the user to enter the password.
3. If the password entered does not match the correct password, print an error message.
4. If the password does match, print a success message.

**Extra credit:**

1. Allow the user to enter their password up to *three* times before quitting the program.
2. Allow the user to create an account if it does not already exist.




## Week 3

Week 2 enabled us to write more complex and useful programs by using control structures such as selections (`if-elif-else`) and iterations (`for` and `while`). We can now evaluate the current state of our program and make decisions by testing their conditions.

### Quiz Review

#### Question 1

Translate the following statement into code: Given variables x and y, if x is greater than y, print their sum, but if x is less than or equal to y, print their difference.

```python
if x > y:
    print(x + y)
elif x <= y:
    print(x - y)    # Technically, difference should be an absolute value
    
# or, more concisely

if x > y:
    print(x + y)
else:
    print(x - y)
```

#### Question 2

Translate the following statement into code: Input a list of users' names until an empty return and then print out all of the names that were entered.

```python3
users = []
name = input()

while name != "":
    users.append(name)
    
    name = input()

for name in users:
    print(name)

```

#### Question 3

Translate the following statement into code: Given variables x and y, if x plus y is greater than 0 but less than 100, print the sum. Otherwise print "Out of bounds."


### Objects and Functions


Week 3

* Objects
	* Functions



### Running software

* Pivotal Cloud Foundry
	* Sample push application
	* Pipelines
* Jenkins
* CI/CD

	
### The cloud

### Exercises

#### Dictionaries
* Iterate over values in a dictionary

## Week 4

### How does the internet work?

* Show the basics of an HTTP request?
* What are microservices?
* What is an API?

### Exercises

#### Call an API

* Make a call to the DarkSky API to retrieve the weather for Dublin
* Do something with the result (e.g. get the max wind speed for the day)

* **Advanced**: call a Mastercard API
	* Requires using the OAuth signer

### Summary of learning

#### Goals
* Graduates should be able to identify terminology
	* API
	* JSON
	* Keys
	* XML
	* Git
	* Maven, Gradle
	* Microservices
* Relate what they learned in the course to their daily work lives
* Capstone project 
	* DarkSky API integration

### Tools

* Repl.it
* Jupyter?
* Documentation!


### Exercises
#### Week 1
#### Variables
#### Exercise 1: Variables
#### Input/Output
#### Exercise 2: Print "Hello, \<your name>"
##### Code

```python
print('Please tell me your name')
name = input()
print(f'Hello {name}')
```



### Old Stuff (Delete?)

### Where is code stored?


### Frameworks

* What is a library?
	* Spring Boot
		* Goal to reduce boilerplate or ramp-up of a project
* Packaging libraries/frameworks
* Distributing libraries/frameworks
	* Artifactory

### Exercises

* Walkthrough of a sample Spring Boot project
	* Look at pom.xml OR build.gradle
	* Look at src/main/java directory
	* Where are classes saved
	* Building an application
