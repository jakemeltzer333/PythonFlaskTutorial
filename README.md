# Python/Flask 101

Written By Jake Meltzer and Jason Rowland

## Python

Python is one of the oldest programming languages still in use. Founded in 1991 by Dutch programmer Guido Van Rossum, Python is a powerful and easily readable general-purpose programming language that has many similarities to Javascript. Its longevity means it has been used to build many popular apps and programs, including Instagram and Dropbox, where Van Rossum currently works, and it's also used a lot at NASA because it is a popular language for helping to program robots!

### Installation

If you have a Mac, you should already have some version of Python installed on your computer, probably version 2.7.10. To know for sure, just go into your terminal and type `python --version`. Python 2 is many years old, so for the purposes of this tutorial, you're going to want to download Python 3. To do so, just go to Python's [website](https://www.python.org/) and hover over the Downloads tab to download the latest version, which should be 3.6.2. 

To run Python in the console is very easy: just type `python3` and the Python interpreter will open up. Now we're ready to play around! 

### Data Types

Python uses data types that are pretty much identical to Javascript: numbers, strings, and lists, which are basically Python's version of arrays. For example, this is a list:

```python
teachers = ['Ari', 'Dom', 'Drew', 'J', 'John', 'Ramsey']
len(teachers)  # => 6
```

That looks **A LOT** like a Javascript array!

Python also has two types of numbers: _integers_ and _floats_. Integers are whole numbers while floats are numbers with decimals.

For example:
```python
5 * 5 # => 25
5 + 5 # => 10
10 - 5 # => 5
10 / 5 # => 2.0
```

Whoa! Why did we get a float when we divided 10 and 5, even though the solution is a whole number? That's just a Python quirk. In order to get an integer instead of a float when you divide numbers, just type two `/` signs instead of one.

```python
10 // 5 # => 2
``` 

Another thing Python can do much more easily than Javascript is find a number's square root. In Javascript, to find 3-squared, you would have to do this:

`Math.pow(3, 2)`

But in Python, it's super easy!

`3**2`



