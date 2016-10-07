python-novice-gapminder
=======================

Introduction to Python for non-programmers with a focus on plotting and data analysis.
Please see <https://swcarpentry.github.io/python-novice-gapminder/>
for a rendered version of this material,
[the lesson template documentation][lesson-example]
for instructions on formatting, building, and submitting material,
or run `make` in this directory for a list of helpful commands.

Maintainer(s):

* [Bennet Fauber][fauber-bennet]
* [Greg Wilson][wilson-greg]

[fauber-bennet]: http://software-carpentry.org/team/#fauber_bennet
[lesson-example]: https://swcarpentry.github.com/lesson-example/
[wilson-greg]: http://software-carpentry.org/team/#wilson_g

# Teaching Outline #

## Before ##

```bash
mv ~/.bash_aliases ~/.bash_aliases~
PS1="$"

```

-   Confirm that pandas, matplotlib, jupyter, ipython are all installed
-   Download [python-novice-gapminder-data.zip](http://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip)
-   Extract data on desktop and rename directory to `gapminder`
-   ???Motivation???


## Running Python Programs ##

-   Python is a program, and can be used at the command line
    -   To quit, use `ctrl-c`
    -   type: `print("hello world")`
    -   type: `1+1`
-   Jupyter Notebook is a way to more richly interact with python
-   Start a notebook
    -   `jupyter notebook`
    -   New Python3
    -   Rename to "test_notebook"
-   We can do the same things in a jupyter notebook as we can on the command-
    line
    -   Type the same two lines
    -   `Shift-Enter`
    -   Notice what happens when I type the two expressions in reverse
        order
-   We can also add text boxes
    -   Render a list
    -   Render equations

### [Check Your Understanding] ###

-   Quit Jupyter
-   restart it in the data directory (how do you know?)
-   Make a new notebook
-   Rename it to "python_day_1"
-   With a single cell:
    -   Print "1 + 1"
    -   Print "=" (on a new line)
    -   Print 3


## Variables and Assignment ##

### Variables are sticky notes ###

-   type `pi_ish = 3.14`
-   `shift-enter`
-   `pi_ish <Shift-Enter>`
-   `pi_ish + 1`
-   `outline = pi_ish * 10`
-   `pi_ish = 3.5`
-   `pi_ish`
-   (?) what does `outline` equal?
-   `print(outline)`
-   (?) what does `Outline` equal?

### [Check Your Understanding] ###

After running 

```python
initial = "left"
position = initial
initial = "right"
```

what is the final value of `position`?

a.   "left"
b.   "right"
d.   "initial"
c.   "position"

### [Challenge Question] ###

```python
first = 1
second = 2
```

How can you swap the values of `a` and `b` regardless of what values
they have?


## Data Types ##

-   Variables can point to a variety of data
    -   `some_text = "This is some text."`
    -   `type(1)`
    -   `type(some_text)`

-   Some operators that work on numbers also work on strings
    -   `some_text * 3`
    -   `some_text + " And this is some more."`

-   And some new operations, too.
    -   `len(some_text)`
    -   `len(pi_ish)  # Doesn't work; why?`
    -   read the TypeError to figure out what's going on

-   We can convert between types.
    -   `some_text + pi_ish  # Doesn't work.`
    -   `str(pi_ish)`
    -   `some_text + str(pi_ish)`

-   What about BOOLEANS?
    -   True
    -   False
    -   True and False
    -   True or False
    -   More complex expressions
    -   `str(True)`
    -   `bool(0)`
    -   `bool(1)`
    -   `bool(None)`

### [Check Your Understanding] ###

-   What is the type of `pi_ish`?
-   What is the type of `int(pi_ish)`?
-   What is the value of `int(pi_ish)`?
-   What is the value of `bool(some_text)`?

## Lists ##

-   So far we have three types:
    -   `int`s
    -   `float`s
    -   `str`s
-   What about collections?
-   Arrays, Lists, Vectors, etc.
-   `my_list = ['Einstein', 'Curie', 'Galileo', '???']  # Famous advisor.`
-   Notice the syntax.
-   What if we want just one item?
    -   `my_list[0]  # Indexing: get the zero-th item`
    -   `len(my_list)`
    -   `my_list[len(my_list) - 1]  # indexing with a variable`
-   `my_list[0:2]  # Slicing`
-   `my_list[0] = 'Albert Einstein'  # Assignment`
-   `print(my_list)`
-   Is indexing/slicing useful in other cases?
    -   `some_text[0:5]  # Yes!`


### [Check your understanding] ###

What do you get when you run the following:

```python
something_here = ['Apples', 'Oranges' 'Bananas']
print(something_here[3])
```

Why?
Can you make the necessary changes?

### [Challenge] ###

What is printed by the following:

```python
a_list = ["what's", "in", "a", "name"][3][1:3]

```

## Intro to functions ##

-   We've seen several functions so far:
    -   `print()`
    -   `len()`
    -   `int()`
    -   `str()`
    -   etc.
-   Here are a few more:
    -   `min()`
    -   `max()`
    -   `round()`
    -   `range()`
-   Transforming data with functions is a key component of programming

```python
some_text = "1.664"
a_number = float(some_text)
an_integer = round(a_number)
print(an_integer)
```

-   Here we've taken a string as input, and re-cast it as a float,
    rounded it to an integer, and printed it to the terminal
-   Every step along the way we've assigned our values to variables; sometimes
    this isn't necessary.
-   `print(round(float("1.664")))` does exactly the same thing!
-   Let's break down what we've done here.
-   Get help using the `help()` function
    -   Also `function_name?` while in Jupyter Notebook

-   Let's check out the help for `max`
    -   `help(max)  # OR: max? will work, too`
    -   We can read the "docstring" and figure out that `max()` takes two
        or more arguments and gives us back the largest one.
-   Now let's try it: `max(1, 2)`
-   What if I give it a list? `max([1,2,3])  # Cool!`

-   Every function returns something
    -   If it doesn't return a normal value, it returns `None`.

## Check your understanding ##

-   How can I round a number to the closest 1/10th?
-   Given the string `"1.500000001"`, write a _single_ expression that will
    evaluates to the string `"1.5"`.

## Challenge Question ##

-   Does python respect the normal order of operations for arithmetic?
-   How do you know?


## Coffee Break and Questions ##

...

## Libraries ##

-   Sometimes we want to use more than the builtin functions and variables
    like `+`, `print()`, `round()`, None, etc.
-   In that case we need to "import" additional libraries
    -   Alternatively called
        -   packages
        -   modules
        -   scripts (sometimes)
-   Try the following

```python
import math

print(math.pi)

```

-   Let's break-down what's happened here.
-   Think of the `.` between `math` and `pi` as meaning that there's
    an object
-   By importing math we no longer need to define `pi = 3.141596...`
    at the start of every module
-   `type(math.pi)`
-   What else do we get?  `math.cos`.  What do you think that does?
-   `help(math.cos)`
-   The real value of python is in the libraries
-   `help(math)`
-   `type(math)`
-   `dir(math)`

-   Importing specific items, importing with an alias

### Check your understanding ###

Find the sin of 0.2 * pi radians

## Tabular Data ##

-   We're going to finish up today using a couple of libraries which
    are particularly useful for scientific computing
-   Pandas!
-   `!head data.csv  # This shell command is a special feature of jupyter`

```python
import pandas as pd

data = pd.read_csv('data.csv')

data.mean()
data.max()
data.min()
data.info()

data.some_column
data['some_column']
data.some_column.mean()

```

-   This is kinda like an excel spreadsheet!
-   Except this way you can write a script and re-run your analysis.
-   My goal is to convince you to start replacing Excel with Python for
    analyses that you want to document and/or repeat.

### Selecting Data ###


--------

### [Challenge Question] ###

How do you _write_ a csv?


## Repeating Actions with Loops ##

### Motivation ###

What if we want to print everything in `names`?

```python
print names

print names[0]  # Newton
print names[1]  # Turing
print names[2]  # Darwin
print names[3]  # Tesla
print names[4]  # Einstein
```

That's kinda repetitive, and what happens if the length of the list is
unknown before we run that code?

There must be a better way.

```python
for some_name in names:
    print some_name
print "That's all of the names!"
```

### Anatomy of a loop ###

### Counting things with loops ###

### Accumulator pattern ###

### Challenge question ###

Exponentiation is built into Python:

```python
print 5 ** 3
125
```

Write a loop that calculates the same result as 5 ** 3 using multiplication
(and without exponentiation).


### Booleans ###

While `=` is the assignment operator, we often use it in common writing to mean
"is equal to".

In python, you ask the question "is x equal to y" with `x == y`.

The value of that statement depends on the values of `x` and `y`.

```python
print 6 == 6

x = 6
y = 7
z = '6'
print x == y
print x > y
print x <= x
```

### Booleans logic: `and` and `or` ###

```python
print x == z
print x == int(z)
print (x == z) or (x == int(z))
```

### Anatomy of an If-statement ###

```python
num = 37
if num > 100:
    print 'greater than 100'
else:
    print 'not greater than 100'
print 'done'
```

What if we want to do something else if `num` _is_ greater than 25?

We _could_ do this:

```python
num = 37
if num > 100:
    print 'greater than 100'
else:
    if num > 25:
        print 'greater than 25'
    print 'not greater than 100'
print 'done'
```

But this is messy and it's cleaner to use an `elif` block, which means
the same thing.


```python
num = 37
if num > 100:
    print 'greater than 100'
elif num > 25:
    print 'greater than 25'
else:
    print 'not greater than 25'
print 'done'
```

### Check your understanding ###

What will be printed if you run this code? Why did you pick this answer?

```python
if 4 > 5:
    print 'A'
elif 4 == 5:
    print 'B'
elif 4 < 5:
    print 'C'
```

## Writing Your Own Functions ##

At this point we've used a few functions (called with parameters in parentheses).
Python functions are kinda like mathematical functions.
Given a set of inputs, they do something, and/or give back the output.
One powerful way to use functions are as formulae.

### Converting Temperature Units ###

-   Encapsulation / `return`ing
-   `int`s vs `float`s
-   Composing functions
-   Syntax errors
-   Reading debug traces, debugging
-   Calling a function with positional vs keyword arguments
-   Why?

### Challenge Question ###

1.  Read the code below, and (without running it) try to identify what the
    errors are.

2.  Run the code, and read the error message. What type of NameError do you
    think this is? In other words, is it a string with no quotes, a
    misspelled variable, or a variable that should have been defined but
    was not?

3.  Fix the error.

4.  Repeat steps 2 and 3, until you have fixed all the errors.

```
for number in range(10):
    # use a if the number is a multiple of 3, otherwise use b
    if (Number % 3) == 0:
        message = message + a
    else:
        message = message + "b"
print message
```

### Converting Temperature Units ###

-   Encapsulation / `return`ing
-   `int`s vs `float`s
-   Composing functions
-   Syntax errors
-   Reading debug traces, debugging
-   Calling a function with positional vs keyword arguments
-   Why?

### Challenge Question ###

1.  Read the code below, and (without running it) try to identify what the
    errors are.

2.  Run the code, and read the error message. What type of NameError do you
    think this is? In other words, is it a string with no quotes, a
    misspelled variable, or a variable that should have been defined but
    was not?

3.  Fix the error.

4.  Repeat steps 2 and 3, until you have fixed all the errors.

```
for number in range(10):
    # use a if the number is a multiple of 3, otherwise use b
    if (Number % 3) == 0:
        message = message + a
    else:
        message = message + "b"
print message
```

### Centering Data ###

-   (Implicitly, introduce testing on a small dataset)
-   Add a new argument to center on something other than 0
-   Make that an optional argument

### Challenge Question ###

1.  Write a function rescale that takes an array as input and returns a
    corresponding array of values scaled to lie in the range 0.0 to 1.0.

    Hint: If L and H are the lowest and highest values in the original array,
    then the replacement for a value v should be (v − L)/(H − L).

    Be sure that this function has documentation.

### Writing "Correct" Code ###

-   Test on a dataset where we _know_ the answer
-   Write unit tests
    -   `if` statements are goood
    -   But `assert` is made for this
-   Check on state _while_ the program is running

### Super-Duper Challenge Question ###

1.  Re-write your rescale function to take optional 'a' and 'b' parameters
    and rescales to that range.  Is the formula you came up with correct?

2.  Write one unit test to check your answer.

3.  Add one assert statement to your function to check intermediate state.

## Writing your own module ##

-   Put the center function into the module
-   Import it

## Writing a script ##

-   Working with sys.argv
-   Working with sys.stdin/stdout
-   The software we use is NOT qualitatively different from the software you
    are able to write.

## Capstone? ##
