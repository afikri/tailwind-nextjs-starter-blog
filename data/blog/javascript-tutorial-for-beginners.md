---
title: JavaScript Tutorial for Beginners
date: '2023-01-06'
tags: ['javascript', 'code', 'web development']
draft: false
summary: Nowadays, Javascript is getting more and more popular particularly in web application development. Once it only supported front end, but now it made possible to brace backend, hybrid apps, embedded devices and many more.
---

## Introduction to JavaScript

Nowadays, Javascript is getting more and more popular particularly in web application development. Once, it only supported front end, but now it made possible to brace backend, hybrid apps, embedded devices and many more.

#### ⚙️ What is JavaScript and how does it work

In short, when accessing the web page, if something dynamic happened such as changing web theme, promptly content updating, animating image, showing interactive map, etc, it can be sure that javascript involved behind the screen. Javascript is wellknown as client side programming language, meaning that all the web application code in javascript runs on the browser. The language is a single threaded programming language which means it has single statement is executed at a given time. Therefore, it can only process one thing at a time in the call stack.

### 💻 Setting up a development environment

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

### 🎥 Basic syntax and data types

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

### 🚥 Control structures

JavaScript has several control structures that allow developers to manage the flow of their programs. These include:

- if/else statements: used to make decisions based on a condition.

```js
let x = 5
if (x > 10) {
  console.log('x is greater than 10')
} else {
  console.log('x is less than or equal to 10')
}
```

- switch statements: used to select one of many blocks of code to be executed.

```js
let day = 3
switch (day) {
  case 1:
    console.log('Monday')
    break
  case 2:
    console.log('Tuesday')
    break
  case 3:
    console.log('Wednesday')
    break
  default:
    console.log('Invalid day')
}
```

- for loops: used to repeat a block of code a certain number of times.

```js
for (let i = 0; i < 5; i++) {
  console.log(i)
}
```

- while loops: used to repeat a block of code while a certain condition is true.

```js
let i = 0
while (i < 5) {
  console.log(i)
  i++
}
```

- do while loops: similar to while loops, but the code block is executed at least once before the condition is evaluated.

```js
let i = 0
do {
  console.log(i)
  i++
} while (i < 5)
```

- for-in loops: used to iterate over the properties of an object.

```js
let person = { name: 'John', age: 30, city: 'New York' }
for (let key in person) {
  console.log(key + ': ' + person[key])
}
```

- for-of loops: used to iterate over the elements of an array or other iterable objects.

```js
let colors = ['red', 'green', 'blue']
for (let color of colors) {
  console.log(color)
}
```

### 🕹️ Basic functions

A function in JavaScript is a block of code that can be reused multiple times. Functions are defined using the `function` keyword, followed by a function name, a set of parentheses, and a pair of curly braces that enclose the code to be executed when the function is called.

Here is an example of a basic function in JavaScript:

```js
function add(a, b) {
  let result = a + b
  return result
}
console.log(add(3, 4)) // Output: 7
```

In the example above, the function is called `add`. It takes two parameters, `a` and `b`, and returns the sum of those two values. The function is called by invoking the function name, followed by a set of parentheses that contain the arguments to be passed to the function.

Functions can also be defined using function expression, the most common one is arrow function.

```js
const add = (a, b) => {
  return a + b
}
console.log(add(3, 4)) // Output: 7
```

The arrow function is shorthand for the function expression and it's widely used. The arrow function is also can be used like this if the function body contains only one line of statement:

```js
const add = (a, b) => a + b
console.log(add(3, 4)) // Output: 7
```

Functions can also be passed as arguments to other functions, returned as values from functions, and assigned to variables. They are a fundamental building block in JavaScript and are used to organize and structure code.

## ✨ DOM Manipulation

### 🌳🌳 Introduction to the Document Object Model (DOM)

DOM (Document Object Model) manipulation refers to the process of changing the structure, content, or style of a web page using JavaScript. The DOM is a tree-like representation of the elements, attributes, and content of an HTML or XML document. By manipulating the DOM, developers can change the appearance and behavior of a web page in real-time, without the need to reload the page.

There are several ways to manipulate the DOM using JavaScript, some of the most common methods include:

- `getElementById()`: used to select an element with a specific ID.
- `getElementsByTagName()`: used to select all elements with a specific tag name.
- `querySelector()`: used to select the first element that matches a CSS selector.
- `querySelectorAll()`: used to select all elements that match a CSS selector.
  Here is an example of how to use these methods to change the text of a `<p>` element:

```js
<p id="myText">Hello, World!</p>

<script>
  let text = document.getElementById("myText");
  text.innerHTML = "Hello, JavaScript!";
</script>
```

### 🔑 Accessing and manipulating DOM elements using JavaScript

To access and manipulate elements in the DOM, it can be using various methods and properties.
In order to get an element, the `document.getElementById()` method can be used, which takes the id of the element as an argument and returns the first element with a matching id.

For example, if the element with the id "my-element", it can be accessed like this: `let element = document.getElementById("my-element");`.
It can also be used `document.getElementsByClassName()` and `document.getElementsByTagName()` to access elements by class name or tag name. These methods return a collection of elements, so it might be needed to use an index to access a specific element.

To manipulate an element, use properties and methods such as `.innerHTML`, `.style`, `.setAttribute()`, `.appendChild()`, and `.removeChild()`.
For example, to change the text content of an element using `.innerHTML property : element.innerHTML = "New content";`
To change the style of an element, use the `.style property: element.style.color = "red";`
To add or remove an attribute, use `.setAttribute()` and `.removeAttribute()` method: `element.setAttribute("href", "https://google.com");` and `element.removeAttribute("href")`
To add or remove a child element, use `.appendChild()` and `.removeChild()` method: `element.appendChild(newElement);` and `element.removeChild(existingChild);`

These above are just few examples of how to access and manipulate DOM elements using JavaScript.

### 🚁 🖱️ 🗓️ Working with events (e.g., click events, hover events)

In JavaScript, events are actions or occurrences that happen in the browser, such as a user clicking on a button, hovering over an element, or a page finishing loading. Events can be used to make a web page more interactive and dynamic.
JavaScript provides a way to attach event listeners to elements on a web page. An event listener is a function that listens for a specific event to occur on an element and then executes a callback function when the event occurs.

For example, a click event listener can be attached to a button element like this:

```js
let button = document.getElementById('my-button')
button.addEventListener('click', function () {
  console.log('Button was clicked!')
})
```

In this example, the `addEventListener` method is used to attach a click event listener to the button element. The first argument to this method is the type of event to listen for, in this case "click", and the second argument is the callback function that will be executed when the event occurs.

The `.onclick` property can be used to attach a click event listener to an element.

```js
let button = document.getElementById('my-button')
button.onclick = function () {
  console.log('Button was clicked!')
}
```

Similarly, an event listeners for other events can be attached, such as hover, mouseover, mouseout, keydown, keyup, etc.

```js
let button = document.getElementById('my-button')
button.addEventListener('mouseover', function () {
  console.log('Button was hovered!')
})
```

It also possible to remove an event listener by calling the `removeEventListener` method on the element and passing in the type of event and the callback function as arguments.
Event listeners are powerful tools for making web pages more interactive and responsive to user input. They can be used to create dynamic effects, validate user input, and navigate between pages, among other things.

## 🔥🔥 Advanced JavaScript Techniques

It refers to advanced concepts and features of the JavaScript programming language that allow developers to write more efficient, maintainable, and powerful code. Some examples of advanced JavaScript techniques include:

#### Closures:

A closure is a function that has access to the variables in its parent scope, even after the parent function has returned Closures are used to create private variables and methods, and to create callback functions with access to specific variables. It is created when a function is defined inside another function, and the inner function has access to the variables and parameters of the outer function. A closure allows a function to "remember" the state of its environment, even after the outer function has returned. This can be useful for creating private variables and methods, and for creating callback functions with access to specific variables.
Here is an example of a closure in JavaScript:

```js
function outerFunction(x) {
  let privateVariable = x

  return function innerFunction() {
    return privateVariable
  }
}

let closure = outerFunction(5)
console.log(closure()) // Output: 5
```

In this example, the `outerFunction` defines a variable `privateVariable` and returns an inner function `innerFunction`. The inner function has access to the variable `privateVariable` and can return its value, even though the outer function has already returned. The variable `closure` is assigned the return value of the `outerFunction`, which is the inner function, and calling closure will return the value of `privateVariable`. Closures can also be used to create private methods, which are methods that are only accessible within the closure and are not exposed to the outside world.

```js
function createCounter() {
  let count = 0
  return {
    increment: function () {
      count++
    },
    decrement: function () {
      count--
    },
    getCount: function () {
      return count
    },
  }
}
let counter = createCounter()
counter.increment()
console.log(counter.getCount()) // Output: 1
```

In this example, the `createCounter` function returns an object with 3 methods, `increment`, `decrement` and `getCount`. These methods have access to the count variable which is private to the closure, and thus the user cannot directly modify it.

Closures are powerful and versatile JavaScript feature, they can be used in a wide range of programming scenarios, such as event handlers, callbacks, and functional programming.

#### Prototype-based Inheritance:

In JavaScript, prototype-based inheritance is a way for objects to inherit properties and methods from other objects, rather than classes. Every JavaScript object has a prototype, which is another object that it inherits properties and methods from.
When a property or method is accessed on an object, JavaScript first looks for it on the object itself. If it's not found, it looks for it on the object's prototype, and so on, until it reaches the top of the prototype chain, which is the `Object.prototype` object.
Here's an example of how prototype-based inheritance works:

```js
let animal = {
  eat: function () {
    console.log('Eating')
  },
}

let dog = {
  bark: function () {
    console.log('Barking')
  },
}

// Assign animal as the prototype of dog
Object.setPrototypeOf(dog, animal)

dog.eat() // Output: "Eating"
dog.bark() // Output: "Barking"
```

In this example, we have created two objects, `animal` and `dog`. The `animal` object has a method `eat()`, and the `dog` object has a method `bark()`. We then use the `Object.setPrototypeOf()` method to set `animal` as the prototype of `dog`. This means that the `dog` object inherits the `eat()` method from the `animal` object.

We can also use the `Object.create()` method to create an object with a specific prototype:

```js
let dog = Object.create(animal)
dog.bark = function () {
  console.log('Barking')
}
```

In JavaScript, we can also use `__proto__` property to access an object's prototype, but it's not recommended to use it because it's not standard, and it's not supported in all the browsers.
Prototype-based inheritance is a powerful and flexible way to share properties and methods between objects, and it is widely used in JavaScript. It allows for easy code reusability and encapsulation, however, it can be a bit more difficult to understand and reason about than class-based inheritance.

#### Asynchronous programming:

In JavaScript refers to the ability to execute code that doesn't block the execution of other code. As mentioned previously, JavaScript is a single-threaded language, which means that it can only execute one piece of code at a time. However, it provides several ways to perform asynchronous operations such as callbacks, promises, and async/await.
Callbacks are functions that are passed as arguments to other functions and are executed after the main function has completed. Here's an example of using callbacks to perform an asynchronous operation:

```js
function doSomething(callback) {
  setTimeout(function () {
    console.log('I am doing something')
    callback()
  }, 1000)
}

doSomething(function () {
  console.log('I am callback function')
})
console.log('I am doing something else')
```

In this example, the `doSomething` function takes a callback function as an argument and uses the `setTimeout` function to perform an asynchronous operation that takes 1 second to complete. The callback function is executed after the `setTimeout` function completes.
**Promises** are objects that represent the eventual completion of an asynchronous operation. They provide a way to register callbacks to be called when the operation completes, and they can be used to handle errors. Here's an example of using promises to perform an asynchronous operation:

```js
let promise = new Promise(function (resolve, reject) {
  setTimeout(function () {
    console.log('I am doing something')
    resolve()
  }, 1000)
})

promise.then(function () {
  console.log('I am callback function')
})
console.log('I am doing something else')
```

In this example, the `Promise` constructor takes a function as an argument that contains the asynchronous operation. The function is passed two arguments, resolve and reject, which are used to signal the completion or failure of the operation. The `then` method is used to register a callback that is executed when the promise is resolved. **Async/await** is a syntax feature built on top of promises, it allows us to write asynchronous code that looks and behaves like synchronous code.
Here's an example of using async/await to perform an asynchronous operation:

```js
async function doSomething() {
  await new Promise((resolve) => setTimeout(resolve, 1000))
  console.log('I am doing something')
}

;(async function () {
  await doSomething()
  console.log('I am callback function')
})()
console.log('I am doing something else')
```

In this example, the `doSomething` function is declared as `async`, it creates a promise and uses the `await` keyword to wait for it to resolve before executing the next line of code. This way, the function looks like a synchronous function, however it's actually waiting for the promise to resolve.

These are some examples of how to use `callbacks`, `promises`, and `async/await` to perform asynchronous operations in JavaScript. Each one has their own advantages and disadvantages, it depends on the use-case and personal preference on which one to use.

#### Event loop:

The JavaScript event loop is a mechanism that allows the execution of code to be non-blocking and handle multiple tasks at the same time. It is a single-threaded mechanism, which means that it can only process one task at a time, but it allows the execution of multiple tasks by using a queue of messages.
The event loop works by constantly checking the message queue for new messages, also called tasks or events. When a message is added to the queue, the event loop starts processing it. A message can be a function call, an HTTP request, a timer, or any other asynchronous operation.
When the event loop starts processing a message, it runs the corresponding code, and when it finishes, it checks the message queue again for new messages. If there are no new messages in the queue, the event loop will wait for new messages to arrive. This way, the event loop allows the execution of multiple tasks at the same time without freezing the UI or blocking the execution of other code.

Here's an example of how the event loop works:

```js
console.log('Start of the script')

setTimeout(function () {
  console.log('Timeout function')
}, 0)

console.log('End of the script')
```

In this example, the script starts by logging "Start of the script" to the console. Then it sets a timer with a timeout of 0 milliseconds, and it schedules a function to be executed when the timer expires. Finally, it logs `End of the script` to the console.

When the script runs, the event loop starts processing the first message, which is the `console.log` statement that logs `Start of the script`. Then it processes the next message, which is the `setTimeout` function. The `setTimeout` function schedules the function to be executed after 0 milliseconds, but it doesn't block the execution of the next line of code.

Finally, the event loop processes the last message, which is the console.log statement that logs `End of the script`. After that, the event loop checks the message queue for new messages and finds the scheduled function from the `setTimeout` call. Then it processes that message, and logs `Timeout function` to the console.

The event loop is an important mechanism in JavaScript that allows us to create interactive and responsive web pages, handle user input and perform asynchronous operations without freezing the UI.

#### Higher-order functions:

In JavaScript are functions that either take one or more functions as arguments, or return a function as a result. This allows for powerful functional programming techniques, such as map, filter, and reduce. Here's an example of a higher-order function in JavaScript:

```js
function multiplyBy(factor) {
  return function (number) {
    return number * factor
  }
}

let double = multiplyBy(2)
console.log(double(5)) // Output: 10
```

In this example, the `multiplyBy` function is a higher-order function that takes a single argument `factor` and returns a new function that takes a single argument `number` and returns the product of `number` and `factor`. The returned function is then assigned to the variable `double`, which can be used to double any number passed to it.
Another example is the `Array.prototype.map` method, which is a higher-order function that takes a callback function as an argument, applies it to each element of an array, and returns a new array with the results.

```js
let numbers = [1, 2, 3, 4, 5]
let doubledNumbers = numbers.map(function (number) {
  return number * 2
})
console.log(doubledNumbers) // Output: [2, 4, 6, 8, 10]
```

The `Array.prototype.filter` method is another example of a higher-order function, it takes a callback function as an argument, applies it to each element of an array, and returns a new array with the elements that pass the test.

```js
let numbers = [1, 2, 3, 4, 5]
let evenNumbers = numbers.filter(function (number) {
  return number % 2 === 0
})
console.log(evenNumbers) // Output: [2, 4]
```

The other one is `Array.prototype.reduce()`, it is a higher-order function in JavaScript that is used to iterate over an array and reduce it to a single value. The function takes two arguments: a callback function and an initial value (also known as an accumulator). The callback function is passed two arguments: the accumulator and the current array element.

The `reduce()` method applies the callback function to the accumulator and the first value in the array, then the callback function is applied to the result and the second value in the array, and so on. The result of each of these calls is then passed along as the accumulator to the next call. Once all the elements have been processed, the final accumulator value is returned.
For example:

```js
let numbers = [1, 2, 3, 4]
let sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue)
console.log(sum) // 10
```

This will reduce the array of numbers to a single value, 10, which is the sum of all the numbers in the array.

The initial value is an optional parameter, if it is not provided the first element of the array will be used as the initial accumulator value and the callback function will start processing on the second element of the array.

```js
let numbers = [1, 2, 3, 4]
let sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0)
console.log(sum) // 10
```

This will also reduce the array of numbers to a single value, 10, which is the sum of all the numbers in the array and the initial accumulator value is 0.

#### Generators:

In JavaScript, a generator is a special type of function that can be paused and resumed multiple times, allowing it to generate a sequence of values over time. They are defined using the `function*` syntax and can be paused using the `yield` keyword. Once paused, a generator's state is saved, including its local variable values, and can be resumed later on where it left off.
Here's an example of a simple generator function that generates the Fibonacci sequence:

```js
function* fibonacci() {
  let [prev, curr] = [0, 1]
  while (true) {
    ;[prev, curr] = [curr, prev + curr]
    yield curr
  }
}

const sequence = fibonacci()
console.log(sequence.next().value) // 1
console.log(sequence.next().value) // 1
console.log(sequence.next().value) // 2
console.log(sequence.next().value) // 3
```

**Generators** can also take input in the form of `next()` method calls with arguments. These arguments are passed as the value of the `yield` expression when the generator is resumed.

**Generators** are often used in situations where it is useful to generate a sequence of values over time, such as iterating over large data sets, implementing infinite scrolling, and handling asynchronous operations. Here's another example of a generator function that generates a sequence of numbers between a given range:

```js
function* range(start, end) {
  for (let i = start; i <= end; i++) {
    yield i
  }
}

const sequence = range(5, 10)
console.log(sequence.next().value) // 5
console.log(sequence.next().value) // 6
console.log(sequence.next().value) // 7
console.log(sequence.next().value) // 8
console.log(sequence.next().value) // 9
console.log(sequence.next().value) // 10
console.log(sequence.next().done) // true
```

In this example, the generator takes two arguments, `start` and `end`, and uses a `for` loop to generate a sequence of numbers between these two values. Each time the generator's `next()` method is called, the loop variable is incremented and its current value is returned using the `yield` keyword. When the loop has completed and there are no more values to generate, the done property of the returned object is set to `true`.

Alternatively, we can also use `for-of` loop with generator to get the values

```js
for (let value of range(5, 10)) {
  console.log(value)
}
```

The generator can be used in conjunction with the spread operator, to convert the generator into an array

```js
const numbers = [...range(5, 10)]
console.log(numbers) // [5, 6, 7, 8, 9, 10]
```

In this example, the generator function can be used in different ways, whether it's used to generate the values one by one or to convert them into an array or used as an iterator.

#### Web APIs:

JavaScript can interact with browser APIs such as the DOM, Web Storage, Web Workers, Web Sockets, WebRTC, and many others.

A web API in JavaScript allows us to make requests to a server from a web application using JavaScript. This can be done using the `XMLHttpRequest` object or the fetch API. The API will typically return data in a format such as JSON, which can then be parsed and used to update the contents of the web page.
Examples of web APIs include the Twitter API, which allows developers to access tweets and user information, and the Google Maps API, which allows developers to add maps and location-based functionality to their applications.
To use a web API in JavaScript, normally need to sign up for an API key and make requests to the API's endpoint using JavaScript's built-in `fetch()` function or `XMLHttpRequest` object. The returned data can be processed using JavaScript and used to update the contents of a web page

Here's an example of using the fetch API to make a GET request to the JSONPlaceholder API, which is a simple online REST API for testing and prototyping:

```js
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error))
```

This code makes a GET request to the URL https://jsonplaceholder.typicode.com/todos/1, which returns a JSON object representing a to-do item. The `fetch()` function returns a promise that resolves with a Response object. In this example we use the json() method on the response object to parse the returned JSON data and log it in the console.

Here is another example for post request using the same API

```js
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  body: JSON.stringify({
    title: 'foo',
    body: 'bar',
    userId: 1,
  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json))
```

This example makes a POST request to the URL https://jsonplaceholder.typicode.com/posts, with a JSON object containing the data to be sent to the server as the request body. The headers object is also set to specify that the content type is JSON.

In both examples above, the returned data can be further processed and used to update the contents of a web page.
