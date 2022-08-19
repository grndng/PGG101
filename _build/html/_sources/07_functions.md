# Functions ☄️
Functions will enable us to leverage the benefits of programming and for the first time, we will have a real sense of automation when using functions. When we were writing down formulas for different mathematical problems, we wrote them down in a manner comparable to what we do in mathematics. We had some kind of boilerplate or template formula (e.g. `2 * pi * r` ) and we used variables (in this case `r`) to compute the result of a circumference of a circle:

```python
r = 3
pi = 3.14
circle_circumference = 2*pi*r
print(circle_circumference)
```

That means that if we want to compute the circumference of the circle with a higher accuracy by using more decimal places, we would have to switch `pi` to `3.14159` by hand. If we want to compare the results, our code will bloat up by doing the same thing over and over again:

```python
r = 3
pi = 3.14
circle_circumference_01 = 2*pi*rr = 3
pi = 3.14159
circle_circumference_02 = 2*pi*r
print(circle_circumference_01, circle_circumference_02)
```

## Our first function 💥
After talking about automating things and outsourcing the tedious work to computers this seems like a major step back. This is where functions come into play. With functions in Python we can go ahead and set our "template", in this case `2 * pi * r`, into a function we can use over and over again:

```python
def circle_circumference(pi, r):
    return 2*pi*r
```

This might look slightly cryptic and complicated at first but we will go through it step by step. So the keyword `def` tells Python that we are going to create a function. Python expects a function name in that case which is `circle_circumference`. Then we can, in parenthesis, set parameters to pass data inside our function. In our case we want to be able to enter the value for `pi` and the `r`adius for the circumference computation. So this is, and this is <u>important</u> to remember(!!!), how you **create** a function. Creating a function doesn't mean we use the function in any way, we just create it. Just as you would write down the formula in mathematics, nothing is being calculated yet. To really do something with our function, we have to **call** it. This is very important and a common mistake. To call the function, you use the function name followed by the arguments (in our case `pi` and `r`) in parenthesis:

```python
# CREATING the function
def circle_circumference(pi, r):
    return 2*pi*r

# CALLING the function
circle_circumference(3.14, 3) # this will not print out anything

#PRINTING the function
print(circle_circumference(3.14, 3)) # this will print out the result
```

This will print out `18.84` which is the result of `2 * 3.14 * 3`. So if we want to calculate the circumference of a circle with different values, we can just use our newly created function:

```python
# CREATING the function
def circle_circumference(pi, r):
    return 2*pi*r

# CALLING and PRINTING the function
print(circle_circumference(3.14, 3))
print(circle_circumference(3.14159, 3))
print(circle_circumference(3.14, 25))
print(circle_circumference(3.14, 22))
print(circle_circumference(3.14, 11))
```

This begs the question: why not go ahead and use the formula in every line instead of calling the function every time? One reason is readability. When you call your function at a later point in your code, you'll be grateful that you know what you're doing by looking at the function name. Another reason is that if you want to change something within your calculation, you have to change it once and it'll be valid for every time you call your function. Let's look at the following example:

```python
def squaring_things(x,y):
    return x**y

squaring_things(2,4)
squaring_things(5,2)
squaring_things(1,6)
squaring_things(12,2)
```

We notice that we made a mistake. We didn't want to calculate `x**y` but `x**2 + y**2`. If you call the function ten times within your code, you need to change `x**y` into `x**2 + y**2` ten times. When using functions you can simply alter the formula where you have created the function:

```python
def squaring_things(x,y):
    return x**2 + y**2

squaring_things(2,4)
squaring_things(5,2)
squaring_things(1,6)
squaring_things(12,2)
```

Also copy-pasting simple formulas works but what if your function looks like this?:

```python
# Taken from https://github.com/scikit-image/scikit-image/blob/main/skimage/util/dtype.py#L544-L565

def convert(image, dtype, force_copy=False, uniform=False):
    warn("The use of this function is discouraged as its behavior may change 
    dramatically in scikit-image 1.0. This function will be removed
    in scikit-image 1.0.", FutureWarning, stacklevel=2)    
    
    return _convert(image=image, dtype=dtype,                    
    force_copy=force_copy, uniform=uniform)
```

You don't need to understand what's going on in the function (but you still see the pattern: `def`, the `function_name` and `(parameters)`). It's self explanatory that it wouldn't make sense to copy-paste that code block over and over again. The more complicated and extensive your program gets, the happier you will be about functions - no doubt!

## `print` and `return` in functions 🖨

As you might have noticed we don't use print-statements in our functions. Instead we use `return`. If you have a function that doesn't return anything within the function, it will return `None`:

```python
def my_func():    
    return	# this will return None
```

Also it is important to know that if you use a return statement and Python reaches the return statement, the function call will be left:

```python
def my_func():    
    x = "funny function"    
    return x	
    x = "this is fun"

>>> print(my_func)
"funny function"
```

On a side note: you can't leave functions empty. If you want to define a function for later use, you can use the `pass`-keyword:

```python
def my_func():    
    pass
```

We will take a deeper look at return statements during the lectures, too. However, for now you can remember that when working with return statements, we can *reuse* the results of our functions which will be important later on!:

```python
def square(x):
    return x ** 2a = 4

>>> print(a * square(2)) # 4 * (2**2) = 4 * 4 = 1616
```

This would *not* work if we would use `print` instead of `return`!

To solidify your knowledge about functions in Python, there is another exercise which you can take a look at:


`````{admonition} Third Python Task:
:class: warning

{bdg-danger}`Link to PDF on HCU Cloud:` [Functions in Python](https://cloud.hcu-hamburg.de/nextcloud/s/8CrbmncnEpHZi7D)
`````
