# Loops in Python 🔄

To be even more flexible and especially to automate tasks in Python we use *loops*. Loops are being used to execute a given code block over and over again. We will talk about `while` and `for` loops. Just as almost everything that's built into Python, loops are started with their corresponding keywords `while` and `for`. Again: the resemblance to the English language makes it easy to understand the concept behind both kinds of loops. 

## while loop 🔁

Let's talk about the `while`-loop first and start off with an example. Before reading on try to figure out what the following code block does:

```python
number = 0

while number < 5:
number = number + 1	print(number)
```

So in essence the code provided loops over the variable `number` and checks if the value of `number < 5` evaluates to `True` or `False`. If it evaluates to `True` it executes or runs the indented block. This is what will be printed (without the comments of course):

```python
1 # number (0) + 1 -> number = 1
2 # number (1) + 1 -> number = 2
3 # number (2) + 1 -> number = 3
4 # number (3) + 1 -> number = 4
5 # number (4) + 1 -> number = 5
```

To sum up: in our loop the condition is checked at the start of the iteration (each execution of the loop). The code is being executed *while* the condition evaluates to `True` (and will not stop until it is not `True`!). The last bit in the parenthesis is important. When working with `while` loops you have to think of a way to get out of your loop.

Being stuck in a loop will happen eventually so if you want to get out of a loop you can interrupt your program by `Ctrl+C` on your keyboard or by a stop-button (looks like a square icon most of the time ⏹) in your IDE.

Let's take a look at our next example. Imagine you want to program a game where a user has to guess a number you have chosen between, let's say, 1 and 10 (we will learn about ways to create random numbers in the lecture). Think about what the *stop condition* here is before proceeding. Feel free to copy the code into your IDE and try it out:

```python
hiddennumber = 5
mynumber = int(input("Enter a number between 1 and 10: "))
while True:    
    if hiddennumber == mynumber:
        print(f"Great, the hidden number was {hiddennumber}")
    else:
        mynumber = int(input("Try again: "))
```

So as you might have noticed there is no real stop condition here. The program never stops. To avoid annoying `while`-loops you use `break`-statements in Python! The `break` -statement will break out of a `while`-loop entirely (you will make Python exit the `while`-loop altogether). So in this case we can repair our code by inserting a single `break`-statement. Can you imagine where (= when do we want to exit our `while` Loop? Think about our *stop condition*).

```python
hiddennumber = 5
    mynumber = int(input("Enter a number between 1 and 10: "))
        while True:
            if hiddennumber == mynumber:
                print(f"Great, the hidden number was {hiddennumber}")
                    break # since we want to exit if the number has been guessed!
            else:
                mynumber = int(input("Try again: "))
```



Other than the `break`-statement, `continue`-statements can be used inside loops. When Python encounters a `continue`-statement it jumps right back at the beginning of the loop:

```python
number = 0
while number < 10:
    number += 1
    print(number)
    continue
    print("hey")
```

Feel free to copy the code in your own IDE and run the script. The line after `continue` will never be printed since in line three we add 1 to the value of `number` each iteration. At the point where `number = 10`, the script goes back to line two and checks if `number < 10` is `True` which will evaluate to `False` and the code will finish. Let's look at another example. What's happening?:

```python
while True:
    username = input("Enter username ")
    if username != "username":
        continue
    else:
        print("Hello username")
        break
```

The program asks you for "username" (and not *your* username). If you enter *username*, the program will go on, otherwise it will jump back to the start right until you've entered *username*. We will talk about `while` and `for` loops more in detail over the course of *Software and Interface Technology*!

Aside from `while` loops we can (and do) use `for` loops in Python. Before jumping right into the `for` loops, we will have to talk about the `range()`-function in Python for a second.

## the range() function 🔢

The `range()`-function *returns* a range object. A range object is a data type in Python which is comparable to a *sequence*. The syntax is pretty straight forward: `range(start,stop,step)` with start being the point where we start and stop where our sequence will stop. While our start-value is optional (the default value is 0), the stop-value is mandatory (since Python needs to know when to stop our sequence). The step size is also optional and determines the increment from one value to the next (we'll see what that means in a second). Let's look at some examples:

```python
print(type(range(0,10,2)))
>>> <class 'range'>
```

As you can see the type of the expression `range(0,10,2)` is `range`. Generally speaking this is as much as you need to know about the `range()`-function *for now*! Let's jump over to `for` loops.

## for loops 🔂

While the `while` loop continues to loop over itself while the condition in the loop clause evaluates to `True`, the `for` loop will run e.g. a certain number of times. To do that you need the `for` loop itself and the `range()`-function which is why we introduced it concisely. In truth you don't necessarily need the `range()`-function, you can loop over everything that is a *sequence* in Python. For example `str`ings:

```python
for letter in "test":
    print(letter)

> t
> e
> s
> t
```

So our `for` loop goes over our sequence ``"test"`` and iterates over each *element* of our sequence. Our sequence consists of `t`, `e`, `s` and `t`. If we print each element, we end up printing the letters of the word `"test"`. If Python has looped over all elements, it stops by itself so you don't need to worry about a stop condition. So why did we learn about the `range()`-function?

Now imagine you want to instruct Python to repeat a code block for a certain number of times. An `int`eger value is a good starting point, however, an `int`eger is just a number and we need a sequence. We can use the `range()`-function to create a sequence:

```python
for i in range(10):    
print(i)    
> 0
> 1
> 2
> 3
> 4
> 5
> 6
> 7
> 8
> 9
```

As you can see our loop iterates ten times including the 0 and stopping at the value we have passed into `range()` without including it (the last printed number is 9 and not 10!). Anyhow, we can do more with range: we can set a step size and a start point:

```python
for i in range(1,10,2):
    print(i)
    
> 1
> 3
> 5
> 7
> 9
```

As you can see we now started at 1 instead of 0. That's the first value we've passed into our `range()`-function (the `1`). Starting with `1`, we print everything up until `10` in steps of `2`. If we start with printing `1` and we add 2 on top of it (because we have a step size of 2), we end up with `3` and that's what's being printed. We stop with 9 because our range is from 1 to 10 and 9+2 would extend our range.

To elaborate and show you what else we can do with for loops, let's create a `list` in Python and square all the numbers in our list:

```python
list_of_values = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in list_of_values: # using i as letter is convention, you can name it whatever you like
    i *= i
    print(i)
    
> 1
> 4
> ...
```

As you can see we went over a sequence (our list of values) and squared each value inside our list and printed out our value. To show one more example, let's take a quick look at a range from 1 to 11 and see which of the numbers are even or odd:

```python
for i in range(1,11):
    if i % 2 == 0:
        print(i, "is even")
    else:
        print(i, "is odd")
        
> 1 is odd
> 2 is even
> ...
```

As you can see we have combined the `for` loop with `if` statements to iterate over a sequence and print out results depending on conditions. Let's look at the last example for `for` loops:

```python
sum = 0
for i in range(1,11):
    sum+=i
print(sum)

> 55
```

Concluding the last chapter, we focus on loops in the final exercise of PGG101. Keep in mind that our ultimate goal is to work on full-fledged projects in Python. To do this, we'll need to apply the concepts we've learned here, which you'll implement in your own projects over the course of your masters program.


`````{admonition} Final Python Task:
:class: warning

{bdg-danger}`Link to PDF on HCU Cloud:` [Final Exercise 🎉](https://cloud.hcu-hamburg.de/nextcloud/s/M7YNZLZTQJQLWA3)
`````