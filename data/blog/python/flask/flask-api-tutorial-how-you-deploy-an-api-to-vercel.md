---
title: Flask API Tutorial - How you deploy an API to Vercel
date: '2023-09-26'
tags: ['api', 'code', 'python', 'flask', 'vercel']
draft: false
summary: In this brief article, I am going to show you how to create a minimal Python API using the Flask microframework. I will provide a step-by-step walkthrough for building a basic API that returns a JSON message.
---

In this short article, I want to demonstrate how to write the simplest API python code by using Flask microframework.
I will walk you through it step by step to create a basic API that responds with a JSON message.

#### Step 1

Make sure you have install flask library, by issuing this command on your terminal

```python
flask --version
```

in my case, i got replied `Python 3.10.9`, `Flask 2.2.3`, `Werkzeug 2.2.3` but if not, then

```python
pip install Flask
```

#### Step 2

Alright, now we're gonna whip up a basic Flask API:

- create a `app.py` file. put it on the root folder.
- need to import libaries, i.e Flask, jsonify

```python
from flask import Flask, jsonify

app = Flask(__name__)
```

#### Step 3

We need to tell explicitly the route that will return the json response. So, we need to create an endpoint
at the root `URL` or `"/"` that returns a message like the code below

```python
@app.route("/")
def hello_world():
    message = {"message": "Hello, This message is your api response!"}
    return jsonify(message)
```

#### Step 4

Finally, we need to make our Flask app executable by putting

```python
if __name__ == "__main__":
    app.run(debug=True)
```

code to the bottom of the app.py file to start the development server:
In the end, the app.py code should look like this:

```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/")
def hello_world():
    message = {"message": "Hello, This message is your api response!"}
    return jsonify(message)

if __name__ == "__main__":
    app.run(debug=True)
```

Save the file and open a terminal. Navigate to the directory where app.py is located and run the application:

```python
python app.py
```

Great! You've created a simple Flask API that responds with a JSON message. You can extend this example by adding more routes and functionality as needed for your application.
