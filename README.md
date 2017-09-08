# Python/Flask 101

Written By Jake Meltzer and Jason Rowland

![Power of Python!](https://media.giphy.com/media/t48kZup19QOWs/source.gif)

## Python

Python is one of the oldest programming languages still in use. Founded in 1991 by Dutch programmer Guido Van Rossum, Python is a powerful and easily readable general-purpose programming language that has many similarities to Javascript. Its longevity means it has been used to build many popular apps and programs, including Instagram and Dropbox, where Van Rossum currently works, and it's also used a lot at NASA because it is a popular language for helping to program robots!

### Installation

If you have a Mac, you should already have some version of Python installed on your computer, probably version 2.7.10. To know for sure, just go into your terminal and type `python --version`. Python 2 is many years old, so for the purposes of this tutorial, you're going to want to download Python 3. To do so, just go to Python's [website](https://www.python.org/) and hover over the Downloads tab to download the latest version, which should be 3.6.2. 

To run Python in the console is very easy: just type `python3` and the Python interpreter will open up. Now we're ready to play around! 

_To exit the interpreter/console, just type `ctrl D`_

### Data Types

Python uses data types that are pretty much identical to Javascript: numbers, strings, and lists, which are basically Python's version of arrays. You can check for what sort of data you have by typing `type(data)` in the terminal, so `type(4)` would print `< class 'int' >` for integer.  

#### Lists

This is a list:

```python
teachers = ['Ari', 'Dom', 'Drew', 'J', 'John', 'Ramsey']
len(teachers)  # => 6
```

That looks **A LOT** like a Javascript array! You can even do similar some similar methods on them, but with slightly different syntax. For example, that `len()` method is Python's version of `.length`. You can also _slice_ in Python, but instead of writing `teachers.slice()`, you just write this:

```python
teachers[0:2] # => ['Ari', 'Dom']
```

Getting the last value of a list or a string is also extremely simple. 

```python
teachers[-1] # => 'Ramsey'
'Ramsey'[-1] # => 'y'
```

As is adding or removing data.

```python
teachers.append('Cornelius')
# ['Ari', 'Dom', 'Drew', 'J', 'John', 'Ramsey', 'Cornelius']

teachers.remove('Ari')
# ['Dom', 'Drew', 'J', 'John', 'Ramsey', 'Cornelius']
```

#### Numbers

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

```python
Math.pow(3, 2) # => 9
```

But in Python, it's super easy!

```python
3**2 # => 9
```

### Loops and If Statements

Python, like Javascript, also has `for` loops and `if` statements. If you haven't noticed a theme by now, they're also easier to read in Python!

You know what `for` loops in Javascript look like:

```javascript
for (let i = 0; i < teachers.length; i++) {
    // YOUR CODE HERE
}
```

It's almost funny how much easier they are to read in Python. It's basically English!

```python
for teacher in teachers:
    # YOUR CODE HERE
```

Another cool thing you can do in Python loops is loop through a _range_ of elements, meaning you can choose where you want to start and end the loop and by how much you want to iterate through it. So if I wanted to get every 4th number between 0 and 20, I would just do this:

```python
for n in range(0, 20, 4)
    print(n)
    # 0, 4, 8, 12, 16
```
Notice how 20 is not printed. That's because in Python, the end number in a range is non-inclusive.

Like `for` loops, `if` statements are very easy to read in Python:

```python
if x < 10:
    print 'Young Buck!'
else:
    print 'Time to grow up!'
```

We can use our favorite Fizzbuzz `if` statement to demonstrate it even further and show how `else if` is written in Python:

```python
if x % 3 == 0
    print 'Fizz'    
elif x % 5 == 0
    print 'Buzz'
else
    print x    
```

#### Dictionaries

Dictionaries are another Python data type that act very much like Javascript objects. They accept key value pairs and are even written in the same fashion, here with a key `name` and a value `age`:

```python
teachers = {'Ari': 24, 'Drew': 29, 'John': 32}
```

You can also build a dictionary from scratch.

```python
dict(Ari=24, Drew=29, John=32)
```

Looping through dictionaries is also really intuitive. There's even a built-in `.items()` method that Python gives you for free.

```python
teachers = {'Ari': 24, 'Drew': 29, 'John': 32}

for key, val in teachers.items():
    print(k, v)
# => Ari 24, Drew 29, John 32    
```

![Dictionary](http://pad2.whstatic.com/images/thumb/d/d4/Use-a-Dictionary-Step-1.jpg/aid27308-v4-728px-Use-a-Dictionary-Step-1.jpg)
### Functions

Functions in Python are written like a mix of Javascript and Ruby syntax with Python's signature colon at the end.

```python
def say_hi(name):
    print (f'Hey {name}!')

sayHi('Jake')
# => Hey Jake!    
```

Notice the `f` in front of the string? That's how Python does string interpolation.
