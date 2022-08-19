# Our first Python program 🥇
After setting up Python and VS Code (or Spyder), we are ready to make our first steps in writing programs. When learning new programming languages as well as verifying that the installation process went down as expected, `Hello World` is a popular first program. It simply prints out the words `Hello World`. There are even collections where you can check out the `Hello World`-examples of different programming languages (e.g. [Hello World Collection](http://helloworldcollection.de/)).

## Hello world 👋
To print out any words in Python, and for the sake of staying true to the example, to print out `Hello World` you simply write:

```py
print("Hello, world!")
```
which should return your Python version (e.g. Python 3.9.0 or Python 3.10.6, ...).

In Python, before being able to run a script or a program, you need to save the file first. So our next steps would be to create a Python file, print out `Hello world` and see what happens! If something is unclear, you can re-watch the video where we have installed VS Code or Spyder to get an idea on how to create, save and run a file in either program.

## Assigments, variables and comments 👉
Before proceeding with writing more interesting programs, let’s take a look at three elements of Python (you remember the list we had earlier?) which will help us with programming in Python: variables, assignments and comments.

### Assignments
Assignments are comparable to assignments in mathematics when you "store" a numerical value in a variable. Taking a look at an assignment in Python we will notice that we’ve seen the form a lot of times in mathematics already:

```py
a = 3
b = 5
a = b
```

In Python the expression left of the *assignment operator* `=` is the variable. So in our case, in the first line `a` is the variable, `=` the assignment operator and `3` the *value*. It's a rather intuitive concept and you will surely get used to it in no time! 

When talking about variables and values, it's important to keep in mind that in the first line `3` is *assigned to* `a` and not `3` *is* `a`. In line 3 we assign `b` to `a` which means that `a` apparently is not `3` but `3` is the value assigned to `a` which can change over the course of our program.

### Operators in short
Before jumping to comments, just because we've used one, let's quickly talk about operators which we will talk about more in depth at a later point. So `=` apparently is the *assignment operator*. There are more operators in Python. Imagine an operator as a function inherent to Python. When Python *parses* or reads through our code when we run our program and it notices one of the built in operators, it *does* something. When Python encounters a `=` it knows that it has to assign a value to a variable. If Python encounters a `+` it knows it has to add things, `*`  is multiplication and so on. Again, there will be a more elaborate take on operators and variables!

### Comments
The other concept we should talk about are comments. Imagine a cookbook. You look through the different recipes and try some of them. While doing so, you find out that using a little less flour and a little more milk lead to nicer cookies so you write that down next to the recipe. You made a comment. Just like that you have the possibility to write comments in your code. You will eventually get to a point where you write code and don't touch it for a while and then go back to the code. The first question when scrolling through the code will probably be *"well, what did I write?"*. You naturally remember some things and some you don't. To avoid that, you <u>write comments for yourself</u>: it's easier (and more efficient) to take your time to write comments while writing your code instead of trying to find out what your functions do at a later point in time. It also makes a lot of sense to <u>comment your code for others</u>, especially if you know that you will share your code or work on a project with other developers so they don't have to figure out what has been written on their own. So how do comments work in *Python*? When writing comments we can use the hash-mark `#` and everything after the `#` in that line won't run:

```python
print("Welcome to Python 101!") # this is a comment
```

In this case the program will print out "Welcome to Python 101!" and ignore "this is a comment" since it comes *after* the hash-mark `#`. If you want to write a comment in the next line, you need to use another `#`!

```python
print("Welcome to Python 101!") # this is a comment
# this is a comment as well
# and this, too!
```

There is also an easy way to have multiline-comments in Python that span more than one line. To do that we wrap our comment in triple-quotes `"""`:

```python
a = 3
"""
This is a multiline comment in which
we can write over multiple lines and
Python will treat every single line
as a comment and not as code!
"""
print(a)
```

Knowing all this and with a little extra input in a second we will be able to solve some mathematical problems in Python. To proceed you can create a Python file on your computer and try to solve the tasks in the following PDF file:

`````{admonition} First Python Task:
:class: warning

{bdg-danger}`Link to PDF on HCU Cloud:` [First Python Program](https://cloud.hcu-hamburg.de/nextcloud/s/wg5WerxgmFq59CM)
`````


