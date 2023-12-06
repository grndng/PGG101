# Variables and operators 🗃️
As you can guess from the title of this chapter we will learn more about variables and operators in Python. We already talked about variables and what you should keep in mind about variables is that they are comparable to a container or box where we can store values so our program can work with it.

## Variables 🅰
When naming variables there are some things to keep in mind. Variable names have to start with an underscore `_` or a letter and can be as long as you wish. So a variable name could be `_42` but not `42` since `42` doesn't start with an underscore or a letter. For the students having keyboards set to a language that is not English: we recommend you not to use special characters like `ü`, `ä`, `à` and so on in your variable names. Also in Python there are [keywords](https://docs.python.org/3/reference/lexical_analysis.html#keywords) that are *reserved* for Python-internal functions. Those can't be used as variables and shouldn't be used as e.g. file names when saving your Python files:

> ```
> False      await      else       import     pass
> None       break      except     in         raise
> True       class      finally    is         return
> and        continue   for        lambda     try
> as         def        from       nonlocal   while
> assert     del        global     not        with
> async      elif       if         or         yield
> ```

Try to keep variable names descriptive for example `list_of_measurements` for, you've guessed it, a list of measurements. The Python Style Guide ([PEP8](https://www.python.org/dev/peps/pep-0008/)) recommends using a notation called `snake_case` which divides words in variables by `_`. Another way to write variable names would be `camelCase` or `MixedCase` where you write the first letter of each word in upper-case letters. Generally speaking: whichever you use, stick to it within your Python file.

## Operators ↔
### Arithmetic operators
We already have used some operators in our first assignment. We will start with the more intuitive operators: arithmetic operators.

| Operator | Name           | Example       |
| -------- | -------------- | ------------- |
| +        | Addition       | `4+5 = 9`     |
| -        | Subtraction    | `4-5 = -1`    |
| *        | Multiplication | `4*5 = 20`    |
| /        | Division       | `4/5 = 0.8 `  |
| %        | Modulus        | `4%5 = 4 `    |
| **       | Exponentiation | `4**5 = 1024` |
| //       | Floor division | `4//5 = 0`    |

Most of those are pretty obvious. You can imagine modulus as the simple remainder of the division of two numbers. `23/5` results in the 5 "fitting" four times inside the 20 and `3`remains which means `23 % 5 = 3`. With floor division it's the opposite: you don't try to figure out what remains after you have divided a number by another number but how many times one number can fit into another number. That means that `23 // 5` would result in 4 since 5 "fits" 4 times in 23.

---

### Comparison operators
Next we will talk about comparison operators. We already know the assignment operator `=`. At first it might feel misleading because we know the assignment operator from mathematics as the operator that shows that something is equal to one another. In Python we use `==` to check for equality. Other comparison operators are:

| Operator | Name                  | Example          |
| -------- | --------------------- | ---------------- |
| ==       | Equal                 | `5 == 5 -> True` |
| !=       | Not equal             | `5 != 5 -> True` |
| >        | Greater than          | `5 > 5 -> False` |
| <        | Less than             | `5 < 5 -> False` |
| >=       | Greater than or equal | `5 >= 5 -> True` |
| <=       | Less than or equal    | `5 <= 5 -> True` |

Other than the notation in Python the comparison operators should be rather intuitive.

---

### Logical and membership operators
Let us take a look at logical and membership operators. Those are pretty self explanatory and are heavily utilized in programming languages to combine statements. The following examples all evaluate to `True`:

| Operator | Description                                           | Example                 |
| -------- | ----------------------------------------------------- | ----------------------- |
| and      | Returns True if both statements are true              | `5 == 5 and 3 > 2`      |
| or       | Returns True if one of the statements is true         | `5 == 5 and 3 < 2`      |
| not      | Reverses the result (returns False if result is true) | `not(5 == 5 and 3 < 2)` |
| in       | Returns True if one value is an element of a sequence | `'5' in '555'`          |


We already have learned how to compute in Python. In the next exercise we'll take another look at some problems where you will have to think more about how to use operators and parenthesis. You can find the tasks in the following PDF file:


`````{admonition} Second Python Task:
:class: warning

{bdg-danger}`Link to PDF on HCU Cloud:` [Operators in Python](https://cloud.hcu-hamburg.de/nextcloud/s/3RbKAH6zBwgA5Dx)
`````

