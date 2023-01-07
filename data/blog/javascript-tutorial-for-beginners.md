---
title: JavaScript Tutorial for Beginners
date: '2023-01-06'
tags: ['javascript', 'code', 'web development']
draft: true
summary: summary is here
---

## Introduction to JavaScript

Nowadays, Javascript is getting more and more popular particularly in web application development. Once it only supported front end, but now it made possible to brace backend, hybrid apps, embedded devices and many more.

#### What is JavaScript and how does it work

In short, when accessing the web page, if something dynamic happened such as changing web theme, promptly content updating, animating image, showing interactive map, etc, it can be sure that javascript involved and it is client side meaning that all the web application code runs on the browser. The language is a single threaded programming language which means it has single statement is executed at a given time.
Therefore, it can only process one thing at a time in the call stack.

link is https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript

### Setting up a development environment 💻

Not like any other languages, javascript does not need to be installed in our machines. Anyone with browser, automatically the development environment is already presented to them, because all browsers come with javascript by default.
Major **browsers** used for javascript development are [Google Chrome](https://www.google.com/chrome/), [Mozilla Firefox](https://www.mozilla.org/en-US/firefox/new/), [Microsoft Edge](https://www.microsoft.com/en-us/edge/download?form=MA13FJ), [Opera](https://www.opera.com/), [Safari](https://support.apple.com/downloads/safari), etc.
For the convenience of development, normally Integrated Development Environment or IDE is used during the application implementation. The mainstream IDEs are [VSCode](https://code.visualstudio.com/download), [Sublime](https://www.sublimetext.com/download_thanks?target=win-x64), [Intellij IDEA](https://www.jetbrains.com/idea/download/#section=windows), [XCode](https://developer.apple.com/xcode/), [WebStorm](https://www.jetbrains.com/webstorm/download/#section=windows), [Eclipse](https://www.eclipse.org/downloads/)  
To test the very first JavaScript code on our browsers, here is the simplest example of a script that displays `Hello World` message on the page:

```html
<html>
  <head>
    <title>My Web Page</title>
  </head>
  <body>
    <script>
      alert('Hello, World!')
    </script>
  </body>
</html>
```

When the page is loaded, the code in the element will execute, and the message "Hello, World!" will be displayed in an alert box.

### Basic syntax and data types 🎥

```js
// This is a single line comment.

/* This is a
multi-line comment. */

// Declare a variable with the "var" keyword
var myVariable

// Declare a variable using the "let" keyword
let myVariable = 'hello'

// Declare a variable using the "const" keyword
const myVariable = 'hello'

// Assign a value to a variable
myVariable = 'hello'

// Declare a function
function myFunction() {
  // function code goes here
}

// Call a function
myFunction()

// Declare an object
const myObject = {
  key: 'value',
}

// Access an object property
console.log(myObject.key)

// Declare an array
const myArray = [1, 2, 3]

// Access an array element
console.log(myArray[0])
```

### Control structures

### Basic functions

## DOM Manipulation

🚜 🚀🚀🚀

### Introduction to the Document Object Model (DOM)

### Accessing and manipulating DOM elements using JavaScript

### Working with events (e.g., click events, hover events)

## Advanced JavaScript Techniques

### Object-oriented programming in JavaScript

### Working with arrays and higher-order functions (e.g., map, filter, reduce)

### Asynchrony and Promises

### Working with APIs and fetching data from the web

## JavaScript Frameworks

### Introduction to JavaScript frameworks (e.g., React, Angular, Vue.js)

### Setting up a project with a JavaScript framework

### Building a simple application using a JavaScript framework

#### Testing and debugging JavaScript code

#### Working with forms and input validation

#### Building interactive applications with JavaScript (e.g., games, animations)
