# Flow control ⬇️
By now it might be apparent that Python reads through the program you provide from top to bottom and executes the commands on its way down. Now when we think about automation, that's not necessarily what we have in mind since we want more flexibility. Functions are one way to be more flexible and accurate since we can call code blocks from certain positions in our code. However, in some cases you want to repeat an instruction a certain number of times or you want to decide on which code block to run based on a condition. A classic way to explain flow control is by the example of some person that wants to go outside. The question is "is it raining?" and if so, if we have an umbrella. Based on that we decide if we want to go outside or if we wait a while until it's not raining anymore. You can draw a *flow chart* with that information which is provided by Al Sweigart in [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/2e/chapter2/) which has a free online version and is absolutely worth a read.

So if you start at the top left and you want to get to the end you have to answer different questions with `True` (yes) or `False` (no). For us this is rather intuitive and self explanatory: if you don't want to get wet get an umbrella or wait until it stops raining. As for the computer, we need to tell it exactly what to do if either of those conditions apply. At the end of this chapter we will be able to write out the "is it raining"-example in Python!

## The input function in Python ⏺
Before we get to the condition-statements, let's learn about the `input()`-function in Python. So if we want the user to enter something in our program, we need to use the `input()`-function. As you can see the function looks exactly like the ones we have written. It has a name followed by parenthesis. A quick example will explain how the `input()`-function works:

```python
user_input = input("Enter something: ")
print(user_input)
```

So after setting `user_input = input("Enter something: ")` Python will prompt us to enter something. You can also use the input function without any string attached to it. However, then the user won't know that he has to enter something:

```python
user_input = input()
print(user_input)
```

So now we know that whatever we enter will be assigned to the variable `user_input` just like a regular assignment.

To build up on that we can write a simple greeting:

```python
username = input("What is your name? ")

print("Hello " + username)

#or

print("Hello", username)
```

What use cases for the `input()`-function can you think of?

## Flow control statements 🔃
One reason that Python is so popular is that it's supposed to be easy to learn. The resemblance of the syntax to the English language is therefore no coincidence. So if we want to ask if something is whether `True` or `False` in Python we use the `if`-statement:

```python
number = 5
if number == 5: # our if-statement    
    print("The number is five!")
```

This is quite intuitive, isn't it? Let's look at some other examples using different kinds of operators:

```python
number = 5

if number == 5:
    print("The number is five!")

if 3 < number < 10:
    print("The number is somewhere inbetween 3 and 10!")

if number != 3:
    print("The number is definitely not 3!")

if type(number) == int:
    print("The variable 'number' has been assigned an integer value!")

if 5**2 == 25:
    print("5 squared is 25!")
```

As you can see there is a wide variety of options we have when it comes to checking for  *truthiness*. Truthiness means that we try to evaluate an expression to be `True` or `False`. This will help us to control and design the flow of our program!

So what happens if our condition does NOT apply? For that we would use the `else`-statement. So we can either look at someone and see what we do `if` it applies or what `else` we do if it does not apply:

```python
number = 3
if number == 5:
    print("The number is five!")
else:
    print("The number is not five!")
```

Depending on what we assign to the variable `number` we will be able to print out either `The number is five!` or `The number is not five!` by using the `else`-statement. The important takeaway here is that if some condition applies, the following (indented) code block will run. In this case if `number == 5` evaluates to `True`, the according code block `print("The number is five!")` will run. If  `number == 5` evaluates to `False`, the block after our `else`-statement will run! This is important to remember since it's the essence of how we control our program!

So let's look at some other examples, too:

```python
if number == 5:    
    print("The number is five!")
else:
    print("The number is not five!")
    
if 2**2 != 4:
    print("There's something wrong with your math...")
else:
    print("Two squared is four!")
    
if number + 5 == 8:
    print("Our variable 'number' has to be 3 since adding 5 to it equals to 8.")
elif (number + 5) > 8:
    print("Our variable 'number' has to be higher than three because adding 5 to it equals in something higher than 8!")
else:
    print("Our variable 'number' has to be lower than three bcause adding 5 to it equals in something lower than 8!")
```

As you can see at the last code block we've sneaked in an `elif`-statement which is being used to check if another expression evaluates to `True` or not. A simpler example would be:

```python
number = 5

if number < 5:
    print("The number is less than 5!")
elif number > 5:
    print("The number is more than 5!")
else:
    print("The number is five!")
```

We check for the value of the variable `number`. If `number` is lower than five, we print accordingly. Else if (hence `elif`) the number is higher than five, we print accordingly, too. If the number is not higher and not lower than five, it has to be five so `else` (because no other condition applies), we print that the number is five.

We can take a look at the execution of our example at [PythonTutor](https://pythontutor.com/visualize.html#code=number%20%3D%205%0Aif%20number%20%3C%205%3A%0A%20%20%20%20print%28%22The%20number%20is%20less%20than%205!%22%29%0Aelif%20number%20%3E%205%3A%0A%20%20%20%20print%28%22The%20number%20is%20more%20than%205!%22%29%0Aelse%3A%0A%20%20%20%20print%28%22The%20number%20is%20five!%22%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false) which might help you to understand that the first two conditions are skipped since they do not evaluate to `True`.

Functions and flow control in Python are essential to develop applications and programs. To reinforce the knowledge you have gained so far, the following exercise will cover these concepts.


`````{admonition} Fourth Python Task:
:class: warning

{bdg-danger}`Link to PDF on HCU Cloud:` [Flow Control in Python](https://cloud.hcu-hamburg.de/nextcloud/s/YAP8z8fyYFNGyeM)
`````