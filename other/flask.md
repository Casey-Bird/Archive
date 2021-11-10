## Initialization

```python
from flask import Flask # Flask Module is needed to actually create the flask app

app = Flask(__name__)

if __name__ == "__main__":
    app.run(debug=True) # Debug allows dynamically updating code. No need to restart server.

```

A route is basically a url or location.
```python
from flask import render_template # Module which finds a "templates/" folder and grabs all html in it

@app.route('/') # Decorator to assign a route location (url location)
def home():
    return render_template("index.html") # Checks for a "templates/index.html" folder/file location.
```

```python
from flask import Flask, render_template

@app.route('/u/<name>') # <variable> allows us to pass in a variable to the backend
def user_route(name): # Takes in that <name> variable from the route parameter.
    return render_template("user.html", user_name = name) # user_name is being passed into a {{ user_name }} jinja variable on the frontend

```

## Error Handling

```python
@app.errorhandler(404) # Pass in the error code that should be handled
def page_not_found(error):
    return render_template("views/404_error.html"), 404 # Error code goes back into function, idk why this exists 
```