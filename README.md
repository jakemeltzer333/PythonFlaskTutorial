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


## Flask

Flask is a Python frame work for building web applications. Django is more commonly used and offers more out of the box, but Flask is light weight and easy for beginners to pick up.
Flask gives you the minimum and leaves everything to be implemented by the developer, while Django includes database interfaces, directory structure, and more.  
The Flask docs put it well:

`"Everything else is up to you, so that Flask can be everything you need and nothing you don’t."`

Flask supports numerous extensions allowing you to build your app exactly to your needs.

You might say Flask is to Python as Express is to node.js, and Django is to Python as Rails is to Ruby.

### Installation

Install is simple. Just install Flask using `pip`. In the directory of your Flask app run

`pip install flask`

or

`pip3 install flask --user`

depending on the version of Python you're using.

Once you have Flask installed, create a file `appName.py` and initiate your app with the following code in that file:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
  return "Hello World!"

if __name__ == "__main__":
  app.run()
```
In this initial file:

- Line 1 imports Flask
- Line 3 initializes an `app` variable, using the `__name__` attribute.
- In Line 5 Flask uses `@app.route` which is a Python `decorator`. The `route()` decorator is used to bind a function to a URL.
- Line 6 defines our function
- Line 7 returns `"Hello World"` to the `"/"` route, similarly you can:
```python
return render_template(
  'index.html')
```
to render a Template instead of a string.
- Line 9 is a standard Python boilerplate that is used to make sure none of the code is ran automatically if the code is imported by another Python script.
- Line 10 calls the `run()` method of the `app` and starts the development server for Flask and allows you to visit the web app locally via localhost.

Now run your app with:

`python appName.py`

and you should get:

`* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)`

That's it! Your app is now running on `http://localhost:5000/` and should say `Hello World!`

### Routing and URLs

- You can have many `@app.route()` decorators, and the URL correlates to the function name being called by the decorator.
- URLs can also attach multiple rules to a function.
- Variables can be passed as a keyword arguments to functions.

```python
@app.route("/hello/<string:name>/")
def hello(name):
    return name
```

### HTTP Methods

By default a route only handles `GET` requests but you can add different request methods to the `route()` decorator.

```python
from flask import request

@app.route('/hello/<name_id>', methods=['GET', 'POST', 'DELETE'])
def hello(name_id):
    if request.method == 'GET':
        #Do this

    if request.method == 'POST':
        #Do that

    if request.method == 'DELETE':
        #Delete this or that
    else:
        #Handle error
```

### Static Files

Static files like CSS and Java-Script files can be stored in a `/static` directory while in development. You can generate URLs for static files using the 'static' endpoint name:

```python
url_for('static', filename='style.css')
```

Static files should be stored on the file system as `static/style.css`.

### Templates

Flask uses the Jinja2 template engine to make rendering HTML easy. To render a template you use the `render_template()` method.
Just use the name of the template and the variables you want to pass to it as keyword arguments:

```python
@app.route("/hello/<string:name>/")
def hello(name):
    return render_template(
    'hello.html', name=name)
```

You can use Template Inheritance to always display certain elements to your app like header, footer, and nav elements. (This is similar to ejs partials).

### Request Object and Responses

To access the request method you have to import it from the flask module:

```python
from flask import request
```

The return value from a view function is automatically turned into a response object and can be accessed in multiple ways including being rendered in a template.

That's a web application at it's most basic form but Flask can do so much more. Imported middle wares and extensions make Flask very flexible.

So get developing!

### Resources

http://flask.pocoo.org/docs/0.12/

http://jinja.pocoo.org/docs/2.9/templates/

https://pythonspot.com/en/flask-web-app-with-python/
