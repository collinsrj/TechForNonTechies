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

### Variables
 
Variables are carriers of data values labeled by a descriptive name. They store relevant information that is then used by a program to perform computations or output it to the user. All variables have a data type and a value. A data type is the kind of data that the variable is storing, and the value is the actual data.
 
#### Declaring a variable
 
```python
age = 23
name = "Sam"
```


#### Primitives

Basic building blocks of all applications. You can create more complex data types (objects) out of these 4 primitives

##### Integer

They are positive or negative whole numbers with no decimal point

```python
totalStudents = 100
temperature = -7
```

##### Boolean

The boolean data type is either True or False

```python
isNightTime = False
isDayTime = True
```

##### Float

They represent real numbers and are written with a decimal point dividing the integer and the fractional parts.

```python
weight = 17.34
average = -34.0
```

##### String

Strings are amongst the most popular types in Python. We can create them simply by enclosing characters in single or double quotes.

```python
name = "John"
lastName = 'Doe'
```
 
#### Collections
 
##### List
Sequence of values encapsulated in a single variable. Are created by putting comma separated values insisde square brackets. Elements inside a list can be of different data types and can change.

```python
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ]
list3 = ["a", "b", "c", "d"]
```

To retreive a particular element of a list, we must enclose the index of the list we want in square brackets. Note: Indexes in python go from 0 to n-1, with n being the size of the list.

```python
firstElement = list1[0] #gets the first value of list1 ('physics')
lastElement = list1[3] #gets the last value of list1 (2000)
```

We can also modify the values of the list using a similar approach.

```python
list1[0]= 'biology' #Now list1 looks like this ['biology', 'chemistry', 1997, 2000]
list1[3] = 3000 #Now the list1 looks like this ['biology', 'chemistry', 1997, 3000]
```

##### Dictionary
Are sequences of key-value pair, where every key in the sequence is unique, but values may not be. More than one entry per key is not allowed. Keys can be of any type but can't change. Values can change. Each key is separated from its value by a colon (:), the items are separated by commas, and the whole thing is enclosed in curly braces.

```pyhton
dict = {'Name': 'Sam', 'Age': 23, 'isLefty': False}
```

Elements in a dictionary are access with its key. Dictionaries can be modified by assigning a value to a new or existing key.

```python
dict['Name'] = 'Bret'   #Modifies the name value
dict['Hair'] = 'Brown'  #Adds a new value with the key 'Hair'
```

Modifying Dictionaries:
##### Tuple
Same as lists but with the main difference that the elemens inside of it can't change. Created by putting different comma-separated values, and can optionally be wrapped inside parenthesis

```python
tup1 = ('physics', 'chemistry', 1997, 2000)
tup3 = "a", "b", "c", "d"
```

Elements in a tuple are access using their corresponding index

```python
print(tup1[0])  #output: physics
```

##### Set

A set is similar to a dictionary, except that it stores values without an associated key. The biggest implication of this is that a set cannot contain duplicate values. It is an unordered collection of unique elements.

```python
set = set(['physics', 'chemistry'])
print(set)  #output: {'physics', 'chemistry'}

set.add('physics')
print(set)  #output: {'physics', 'chemistry'} -- set has not been modified

set.add('biology')
print(set)  #output: {'physics', 'biology', 'chemistry'} -- order is not guaranteed
```

### Operators

#### Mathematical

Addition (+)

```python
x = 5
y = 8

print(x + y)    #output: 13
```

Subtraction (-)

```python
x = 10
y = 3

print(x - y)    #output: 7
```

Multiplication (\*)

```python
x = 5
y = 7

print(x * y)    #output: 35
```

Division (/)

```python
x = 10
y = 2

print(x / y)    #output: 5
```

Exponentiation (\**)

```python
x = 5
y = 2

print(x ** y)   #output: 25
```

Modulation (%)

```python
x = 10
y = 3

print(x % y)    #output: 1
```

### Exercises

#### Exercise 1: Variables

Write a python program that creates a list with five elements your name, last name, age, height (in), and whether you are lefty (True or False), then create three variables and assign it the values of the firs, middle, and last element of the list respectively, and lastly prints to screen these three variables.

```python
list1 = ['Hello', 'World', 5, 3.56, False]
first = list1[0]
middle = list1[2]
last = list1[4]
print(f'{first} {middle} {last}')  #prints: Hello 5 False
```

#### Exercise 2: Say hello!

Write a program that prompts the user for their name. After the user enters their name, give them a personalized greeting.

```python
print('Please tell me your name')
name = input()
print(f'Hello {name}')
```


### Quiz

TODO: Quiz questions for week 1

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
   `==`   | Is the left operand equal to the right operand?		   | `1 == 2` returns `False` <br> `"hello" == "hello"` returns `True` <br> `"1" == 1` returns `False`
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

### Exercises

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


### Quiz

TODO: Come up with quiz questions


## Week 3

Week 2 enabled us to write more complex and useful programs by using control structures such as selections (`if-elif-else`) and iterations (`for` and `while`). We can now evaluate the current state of our program and make decisions by testing their conditions.

### Review Quiz

Q1. Translate the following statement into code: Given variables x and y, if x is greater than y, print their sum, but if x is less than or equal to y, print their difference.

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

Q2. Translate the following statement into code: Input a list of users' names until an empty return and then print out all of the names that were entered.

```python
users = []
name = input()

while name != "":
    users.append(name)
    
    name = input()

for name in users:
    print(name)
```

Q3. Translate the following statement into code: Given variables x and y, if x plus y is greater than 0 but less than 100, print the sum. Otherwise print "Out of bounds."

```python
x = input()
y = input()
sum = x + y

if sum < 0 or sum > 100:
    print('Out of bounds.')
else:
    print(f'Sum is {sum}.')
```

### Classes, Objects, and Functions

A class can be thought of as a blueprint that defines state and behavior of a particular *thing*. In the real world, you often have many objects of the same kind. For example, your bicycle is just one of many bicycles in the world. Using object-oriented terminology, we say that your bicycle object is an *instance* of the *class* of *objects* known as bicycles. Bicycles have some state (current gear, current cadence, two wheels) and behavior (change gears, brake) in common. However, each bicycle's state is independent of and can be different from that of other bicycles.

While you may not have realized it, you've actually been using classes for the last 2 weeks! Consider a class as a complex data type which can hold other types of data. Sound familiar? Where have we seen this in previous weeks? All of the collections we worked with in weeks 1 and 2 are classes.

#### Define a Class

A class is defined with 3 components in mind:

* Name
    * Also referred to as a class's Type
* Data
    * The attributes that make up its state
* Functions
    * Blocks of code which can operate on available data

```python
#A simple Bicycle class example
class Bicycle:                          #Bicycle is the name of this class
    def __init__(self, name, color):    #Special function to create an object
        self.name = name                #Data attribute for the name of the bicycle
        self.color = color              #Data attribute for the color of the bicycle
        self.gear = 1                   #Data attribute for the current gear
    
    def shift_up(self):                 #Function declaration
        self.gear += 1                  #Modifies the gear attribute
    
    def shift_down(self):               #Function declaration
        self.gear -= 1                  #Modifies the gear attribute
        
#Can you spot the bug in this code?
```

#### Data Attributes

Data attributes consist of the instance variables that make up an object's state. These attributes can be assigned, read, and used for operations within functions.

#### Method Attributes

There are two types of functions in Python. Functions defined globally or as part of a class can be accessed independent of a specific instances. Functions defined as part of an object instance can be accessed only in the context of that instance, and are referred to as method attributes or simply methods.

```python
class Dog:
    def __init__(self, name):
        self.name = name            #Data attribute for dog's name
        self.tricks = []            #List data attribute for dog's tricks
    
    def add_trick(self, trick):     #Method attributes always take parameter 'self'
        self.tricks.append(trick)   #Call list method attribute (append) to add a new trick
        
    def bark():                     #Class function associated with Dog
        print('Woof!')
        
def bark():                         #Global function
    Dog.bark()                      #Calls class function
    
my_dog = Dog('Waffles')             #Create an object instance
my_dog.add_trick('speak')           #Call the method attribute

if 'speak' in my_dog.tricks:        #Check tricks data attribute for 'speak'
    bark()                          #Call global function to bark
```

### Exercises

Q1. Define a class which represents the user of an app. A user should have a username, email address, and a collection of actions they are allowed to perform. Include methods to allow actions to be added or removed from a user instance. A user should not have more than one of each action.

```python
class User:
    def __init__(self, username, email, actions):
        self.username = username
        self.email = email
        self.actions = actions
        
        if not actions:
            self.actions = set()
    
    def add_action(self, action):
        self.actions.add(action)
        
    def remove_action(self, action):
        self.actions.remove(action)
```

Q2. Write a program which accepts two users and an action. If user1 has an 'admin' action, allow them to add the given action to user2. If user1 is not allowed to add the action, notify them by printing an appropriate message.

```python
def add_action(user1, user2, action):
    if 'admin' in user1.actions:
        user2.add_action(action)
    else:
        print('Permission denied: must be admin to add that action to another user')
        
```

### Quiz

Q1. What is the difference between a function and a method?
A1. A method is unique to an object instance, where a function is common for a class or program (global).

Q2. What is the difference between a class and an object instance?
A2. A class defines a type name and attributes common across a group of objects (or a *class* of objects ;)), where an object actually holds the data in its instance.

## Week 4

### How does the internet work?

* Show the basics of an HTTP request?
* What are microservices?
* What is an API?

### What is a Web Page?
A webpage is a rendering of `HTML`. HTML is a language for describing how content should be presented. Here's a really simple example:

```HTML
<html>
  <body>
    <p>This is a paragraph.</p>
  </body>
</html>
```

This is turned by a web browser like Internet Explorer or [Chrome](https://www.google.com/chrome/) into the following:

![Example](ExampleWebPage.png)

#### The URL or Address
A URL (Uniform Resource Locator) is a 'simple' way of referring to a server. It's an address, just like you would use to refer to a house or office. Like many things in computers, this is not the complete answer.

A URL is made up on a couple of pieces:
 - the scheme e.g. `http`
 - the domain e.g. `www.mastercard.com`
 - path e.g.`/index.html`

#### The Scheme
The scheme portion of the URL, tells the computer what type of URL this is. The one you're likely most familiar with is http. HTTP is a protocol. A protocol describes how to interact with a system. 
```
> GET / HTTP/1.1
> Host: example.com
>
< HTTP/1.1 200 OK
< Content-Type: text/html; charset=UTF-8
< Date: Mon, 24 Feb 2020 17:09:02 GMT
...
```
HTTP is a simple text based protocol. In the output above the lines starting `>` are data we send to a server. The lines starting `<` is the data coming back.
You can try it if you like. On MacOS, open a terminal and type `nc -v www.example.com 80`. Then type in the following:
```
GET / HTTP/1.1
Host: example.com
```

#### The Domain
The `domain` part of the URL is a layer on top of IP (Internet Protocol). It points a user to an IP address. This is a numeric address pointing to a real server somewhere. An IP address e.g. `64.233.185.103`. This isn't particularly memorable, so domains give us a much easier way to refer to them. That's not their only function, but it's perhaps the most useful.
You can think of a domain like a postcode. In the United States this would be your ZIP+4. In Ireland, this would be your Eircode. It's specific enough to get you to a building.

You can see this in action by typing in the following:
```python
import socket
s = socket.gethostbyname('www.mastercard.com')
print(s)
```

#### IP Addresses
IP addresses identify a "host" or "network interface" on the network. A host can be a real of virtual computer. Your Internet Service Provider will allocate these. In the previous section we've seen that a domain name can be resolved to an IP address. It's the IP address that your website requests go to. 
An interesting question to ask now is, how does the website know where to send the data back to? When you connect to a website, a connection is opened between your computer and the web server. It uses your IP address as part of the connection details. You can see your public IP address by running the following `dig +short myip.opendns.com @resolver1.opendns.com`.

### What is an API
An API or Application Programming Interface is a way for bits of programs or computers to talk to each other. It is a description of what to send and what you should expect to get back. 
It may be best to start with an example. In week 3 you encountered a class called `Bicycle`. Bicycle has two functions: `shift_up` and `shift_down`. These two functions form the API for bicycles.
Mastercard exposes APIs to perform functions. On the Mastercard Developers platform a number of **REST APIs** are exposed. The term REST describes the approach to exposing the API. It says the API will use the HTTP protocol and that some standard HTTP methods will be used. When a user wants to create something, they `POST` it to the server. When they want to get something, they `GET` it. These two methods are the exact same methods your web browser uses. A handy side effect of using HTTP is that many REST APIs can be accessed using a normal web browser.

### Exercises

#### Call an API
The following code example shows how to call a Mastercard REST API. 

```
import oauth1.authenticationutils as authenticationutils
from oauth1.signer import OAuthSigner
import requests

# Identifies the user to the API Gateway
consumer_key = "LVX4tdsW6nM8hn7YT6I2FiLyK9Wl8lt4f0JSdEP66f2c4137!aaedc71f4e554dd5b5b0e2094ac8835a0000000000000000"
signing_key = authenticationutils.load_signing_key('LearningProject-sandbox.p12', 'keystorepassword')

merchant_id = 'DOLIUMPTYLTDWELSHPOOLWA'

# Make a request object
url = 'https://sandbox.api.mastercard.com/merchant-id/v2/merchant-ids?merchant_id={}&type=ExactMatch'.format(merchant_id)
request = requests.Request()
request.method = "GET"
request.url = url
signer = OAuthSigner(consumer_key, signing_key)
request = signer.sign_request(url, request)
request = request.prepare()

# Send the request
s = requests.Session()
response = s.send(request)
merchants = response.json()

# View the results
print(merchants)
```

## Summary of learning

### Goals

* Graduates should be able to identify terminology
	* API
	* JSON
	* Keys
	* XML
* Relate what they learned in the course to their daily work lives
* Capstone project 
	* DarkSky API integration

### Tools

* Repl.it
* Jupyter?
* Documentation!
