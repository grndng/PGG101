# Data Types in Python 📊
Before utilizing more of Pythons potential and write more elaborate and extensive programs we will briefly learn about Pythons built-in Data Types. Or at least some of them. When working with our formulas we worked with numerical data. However, when we printed out "Hello world", that obviously was *not* numerical which brings us to data types. This section will be incomplete but you will be introduced to the most important and most used ones.

## Looking at some data types 🧾
Let's start off with our "Hello world"-statement. That's text obviously and Python uses `str` for textual data which stands for `string`. We worked with numeric types which are divided into `int` for `integer` values and `float` for floating point numbers. Then there are three types of sequences: `list`, `tuple` and `range`. Other important data types are `dict`ionaries, `set`s and `bool`eans. We are also offered binary types like `bytes` or `bytearray`s.

A general overview is great and for a full list of Built-in Data Types in Python you can always take a look in the [documentation](https://docs.python.org/3/library/stdtypes.html) which is one of the most important resources when looking up Python-related things. You don't have to remember all of them and also we can use a function called `type()` to find out the data type of expressions in Python:

```python
a = "abc"
# we put the element of which we want to
# know the type inside the parantheses like:
print(type(a))
```

Printing the expression `type(a)` will tell us that `a` is an object of the class `str`. You don't need to know about objects and classes yet, it's enough that we know that we can find out the data types of elements with the help of the `type()`-function. Try finding out the types of other data as well!

Another way of finding out the type of data is by using `isinstance()`. While `type()` will return the type of the data we are looking at, `isinstance()` will return `True` or `False` depending on the truthiness of our query:

```python
a = "abc"
print(isinstance(a, int))
# This would return False
print(isinstance(a, str))
# This would return True
```

**What we have learned so far:**
1. Python supports a list of built-in operators (see Table 1)
2. Python has Built-in Data Types (see Table 2)
3. We can utilize the built in operators to work with objects of the built in data types

## Data Types and operators 🔤❎
Let's take a deeper look at our data types. We already know how to work with numbers since we've tried that out in the interactive shell. Next we want to look at how operators behave in different context. In this case "different context" means as much as "what is left and right of the operator we're using?". When we use our addition operator `+` we expect it to add one value to another value. However, if we use the `+` symbol inbetween strings, it will join those. It will become more clear when we take a look:

```python
print('Let' + 'us' + 'join' + 'some' + 'strings')
> 'Letusjoinsomestrings'
```

The returned value `Letusjoinsomestrings` looks more or less what we have expected. To make it display the sentence with the gaps between the words we have to add them. The computer does exactly what we tell it to in the order we tell it to do it: not more, not less.

```python
print('Let' + ' ' + 'us' + ' ' + 'join' + ' ' + 'some' + ' ' + 'strings')
> 'Let us join some strings'
```

Now we get `'Let us join some strings'` and we have *concatenated* our first string. As you can see the `+` operator does *not* add one value to the other but concatenates them since you can not add a string to a string how we understand it in mathematics. What will happen if we try to add a string to a number?

```python
print('Hello' + 237)
Traceback (most recent call last):  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
```

Python returns another error which we haven't read about yet: a `TypeError` which suggests that there is something wrong with our data types. In this case it tells us that we can only concatenate `str` to `str` and not `int` to `str`. We can find another good example in the `*` operator. If we want to multiply a `str`ing, we can use multiplication:

```python
print('Five' * 5)
> 'FiveFiveFiveFiveFive'
```

So this way we can multiply a string without typing it out five times by hand. Can you think of a problem that might occur when you aren't careful while multiplying? A `str` can be multiplied by an `int` but not by a `float` value which makes sense intuitively. If you multiply a `str` like `Five` by 2.5 Python wouldn't understand where to stop and *slice* the string:

```python
print('Five' * 5.0)
Traceback (most recent call last):  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'float'
```

As you can see we've got ourselves another `TypeError`. Again: working with error messages is crucial for developing programs so make sure you try to understand the error messages and why they occur. In this case Python tells us that we can not multiply a sequence (a `str` is a `sequence`, we will learn about `sequences` more in depth later on) by non-int objects (our `float`-value of `5.0` being a non-int object).
