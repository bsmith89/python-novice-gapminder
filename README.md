## Setup

-   Install all software
-   Download all data
-   Open the Socrative
-   Open the etherpad
-   Run test scripts??

## Running python

-   From the command-line
    -   Use like a calculator
    -   Variable assignment
        -   Variables must be created before they're used (`NameError`)
        -   Variable naming rules
        -   Case-sensitivity
    -   `print`ing
        -   Printing values
        -   Printing strings
        -   Difference between strings and variable names
    -   CHECKPOINT: Swap the values of two variables (x and y)
    -   CHECKPOINT: Convert a celsius temperature stored in `temp_C` to fahrenheit and print it.
-   Jupyter notebook
    -   Explain the relationship to the command line
    -   Mention that you can write scripts just like for shell
    -   Explain that we'll be using the jupyter notebook and why

## Operating on values

-   Strings
    -   Using the builtin `len` function
    -   Indexing into strings
        -   Zero indexing
    -   Slicing strings
    -   CHECKPOINT:  Without running it, what will the following code print?
        ```
        first_value = "initial"
        second_value = first_value[1:4]
        first_value = second_value[1]
        print(second_value)
        ```
        What is the value of `first_value`?
    -   Using variables or output of functions to index
    -   Omitting first or last index (since `string[i:len(string)]` always
        produces from `i` to the end)
    -   Casting
        -   Difference between `int` 1 and `'1'`
    -   `type` function
    -   `TypeError`s
        -   `len(an_integer)`
    -   CHECKPOINT: What is the type of `3.4`?
    -   Combining strings with numbers.
        -   `print('(' + str(int) + ')')`

## Functions

    -   What are some functions we've already used?
        -   `type`
        -   `int` / `str`
        -   `print`
        -   `len`
    -   Builtin help (`help` function)
    -   Some more helpful functions
        -   min
        -   max
        -   CHECKPOINT: What do you think the `round` function does?
        -   CHECKPOINT: How would you round `1 / 3` to three decimal points?
            (hint: `help(round)`)
        -   Named arguments: `round(1/3, ndigits=3)`
    -   `SyntaxError`
        -   name = 'this
        -   min(1, 2 3)
    -   Every function returns something
        -   Capture that return value with `=` assignment
        -   `print` returns `None`
    -   CHECKPOINT: Talk through the order of operations in following:
        ```
        radiance = 1.0
        radiance = max(2.1, 2.0 + min(radiance, 1.1 * radiance - 0.5))
        ```
        What is the final value of `radiance`?


## COFFEE BREAK

## External libraries

-   Import external libraries with `import` statements
-   Refer to contents of that library with `library.object`
-   `import pandas`
-   `dir(pandas)`
    -   We want the `read_table` function
-   `pandas.read_csv`
-   Tab completion to see quick / full help
-   Look at the contents of `data/gapminder_gdp_europe.csv`
    -   go back to shell and use `less`
-   `pandas.read_csv('data/gapminder_gdp_europe.csv', index_col='country')`
    -   Pretty printed, sumarized table 
-   Assignment of a dataframe to a variable
-   Indexing into a dataframe
    -   `df['column']` syntax
    -   `df.loc['Germany']` syntax
    -   CHALLENGE: What do you think `df.loc['Germany':'Sweden']` does?
-   Calculations on `DataFrame`s
    -   `min`
    -   `max`
    -   `mean`
    -   Calculations on `Series`
-   CHECKPOINT:
    -   Read data from `data/gapminder_gdp_all.csv` to a dataframe and save it to a variable named `gdp`
    -   Find the mean GDP of Canada in 1972.

## Plotting

-   Import a new library:
    ```
    import matplotlib.pyplot
    plt = matplotlib.pyplot
    ```
    -   Explain aliasing
        ```
        import matplotlib.pyplot as plt
        ```
-   `plt.hist(gdp['gdpPercap_1972'])`
-   TODO: All the other plotting things we'll show them before they go home
