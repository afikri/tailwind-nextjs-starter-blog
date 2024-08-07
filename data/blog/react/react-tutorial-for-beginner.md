---
title: React JS Tutorial for Beginner
date: '2023-01-27'
tags: ['code', 'reactjs', 'web-development']
draft: false
summary: 'React is a JavaScript library for building user interfaces. It allows developers to create reusable UI components and manage the state of the application. The React tutorial covers the basics of creating components, rendering them to the DOM, and handling events and updates. It also covers more advanced topics like hooks, context, and performance optimization. Overall, the tutorial is designed to help developers learn how to build efficient and scalable web applications with React'
---

## 🤝 Introduction to React

**Overview of React and its features** <br/>
React is javascript libraries which used to create user interfaces.
It was developed and is maintained by Facebook. React's main feature is the ability to build reusable components, which can be combined to create complex user interfaces. React uses a virtual DOM, which improves performance by reducing the amount of changes that need to be made to the actual DOM. Additionally, React also has a feature called **jsx** which makes possible to write HTML-like elements in the JavaScript code, making it easier to understand and write. React also supports server-side rendering, which possible to pre-render pages on the server before they are sent to the client, improving the initial load time.

**Setting up a development environment**<br/>
To set up a development environment for React, a _Node.js_ and _npm_ (Node Package Manager) are needed to be installed on the computer.
The steps to do it

1. Install _Node.js_ from the [official website](https://nodejs.org/en/)
2. Verify the installation by running `node -v` and `npm -v` in the command line to check the **version**.

Once _Node.js_ and _npm_ are installed, follow these steps to set up a new _React_ project:

1. Create a new folder for the project and navigate to it in the command line.
2. Run the command `npx create-react-app my-app` to create a new React project. Replace **my-app** with the name of the project.
3. Navigate to the project folder by running `cd my-app`.
4. Start the development server by running `npm start` or `yarn start`
5. Open a browser and go to `http://localhost:3000/` to see the app.

Now, it is time to start building the React app in the **src** folder of the project. To see the changes in the browser, be sure to save the files and then refresh the browser <br/>
Almost forgot to mention that there is a build tool that is similar to Create React App (CRA) called **Vite** but with a focus on faster development and a more lightweight setup. It can be used to create a new React project just like CRA.

**Understanding JSX and components**<br/>
JSX is a syntax extension for JavaScript that makes possible to write HTML-like elements in the JavaScript code which is used to describe the structure and content of a component.
The component is a reusable piece of code that represents a part of a user interface. It is responsible for rendering a specific portion of the UI and managing its state and behavior. Components can be either **functional** or **class-based**.

- Functional components are simple JavaScript functions that accept **props** (short for properties) as an argument and return a JSX element.
- Class-based components are JavaScript classes that extend the **React.Component** class and have a render method that returns a JSX element.
  Both types of components can have their own state, lifecycle methods, and handle events.

## 🏗️ Building React Components

- Creating and styling basic components
  To create component, either a functional or a class-based approach can be used.<br/>
  Example of Functional Component:

```js
import React from 'react'

function MyComponent(props) {
  return <div>Hello, {props.name}</div>
}

export default MyComponent
```

Example of Class based Component

```js
import React, { Component } from 'react'

class MyComponent extends Component {
  render() {
    return <div>Hello, {this.props.name}</div>
  }
}

export default MyComponent
```

To use this component in another file by importing it

```js
import MyComponent from './MyComponent'

function App() {
  return <MyComponent name="John" />
}

export default App
```

To style a component in React, CSS stylesheets can be used, inline styles, or CSS-in-JS libraries like styled-components or emotion.

Using CSS stylesheets:
Create a CSS stylesheet and import it into component file:

```js
import './MyComponent.css'

function MyComponent(props) {
  return <div className="my-component">Hello, {props.name}</div>
}
```

and in the css file

```css
.my-component {
  color: blue;
  font-size: 20px;
}
```

Using inline styles:

```js
function MyComponent(props) {
  const styles = {
    color: 'blue',
    fontSize: '20px',
  }
  return <div style={styles}>Hello, {props.name}</div>
}
```

Using CSS-in-JS libraries like styled-components or emotion:

```js
import styled from 'styled-components'

const MyComponent = styled.div`
  color: blue;
  font-size: 20px;
`

export default MyComponent
```

- Handling events and state
  Components can manage their own state, which is an object that stores data that affects the component's behavior or rendered output. Components can also handle events, such as user input or actions, which can change the component's state and trigger a re-render of the component.
  To handle events, event handlers can be used, functions that are called in response to a specific event. In React, event handlers are usually passed as props to a component. For example, to handle a button click, pass a `onClick` prop to the button component and set it to a function that will be called when the button is clicked.

To manage state, use the useState hook, which make possible to add state to a functional component. useState returns an array containing the current state and a function to update it. For example, the following code defines a component that has a count state and a button that increments the count when clicked:

```js
import { useState } from 'react'

function Example() {
  const [count, setCount] = useState(0)

  return (
    <>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </>
  )
}
```

Also use the `useEffect` hook to handle side effects like fetching data, setting up a subscription, or manually changing the DOM in response to a component’s props or state.

It's important to note that state should only be modified by calling the setter function returned by `useState`, never by modifying the state object directly. Additionally, it's important to avoid direct mutation of state by creating a new copy of the state with the updated value

- Understanding the component lifecycle
  In React, a component goes through several lifecycle stages as it is created, updated, and destroyed. Understanding these stages can help you write more efficient and effective code.

The main lifecycle stages are:

- **Mounting**: This is the process of initializing a component and rendering it on the page for the first time. The following methods are called in this stage:

  - `constructor`: This is called before the component is mounted. It's a good place to set up the initial state and bind event handlers.
  - `render`: This is called to determine what should be rendered on the screen.
  - `componentDidMount`: This is called after the component is mounted and rendered. It's a point to set up any non-React logic, such as fetching data or setting up a timer.

- **Updating**: This is the process of updating a component with new props or state, and re-rendering it on the page. The following methods are called in this stage:

  - `render`: This is called to determine what should be rendered on the screen.
  - `componentDidUpdate`: This is called after the component is updated and re-rendered. It's a good place to update non-React logic based on the updated props or state.

- **Unmounting**: This is the process of removing a component from the page. The following method is called in this stage:
  - `componentWillUnmount`: This is called before the component is unmounted and destroyed. It's a good place to clean up any non-React logic, such as canceling a timer or clearing an interval.

It's important to note that the methods are not always called. For example, `componentDidUpdate` and `componentWillUnmount` are only called if the component is updated or unmounted.

It's also important to note that when a component is updating, React will first call the `render` method to determine what should be rendered on the screen, and then it will call `componentDidUpdate` to update non-React logic. This means that any changes you make in `componentDidUpdate` will not affect the component's rendered output.
It is also possible to use other hooks such as `useEffect` to handle lifecycle events, which is a more modern way of handling and it's more declarative

By understanding the component lifecycle, we can write code that runs at the right time and avoids unnecessary updates.

## 🏷️ Managing Application State:

There are several ways to manage application state in React:

- Using `state` and `setState()`
- Using `Context API`
- Using a state management library like `Redux` or `MobX`
- Using `React Hooks` <br/>

It depends on the complexity and size of the application to determine which method is best for managing state. However, for most cases, the first method (using `state` and `setState()`) is sufficient.

Now, let's deep dive on it

- **Understanding the concept of state in React**<br/>
  It is an _object_ that _holds data_ and changes in response to _user events_. The state of a React component determines what is displayed on the screen.

  **State** is managed within a _component_ and can only be changed using the `setState()` method. When state changes, React will _re-render_ the component and update the UI accordingly. This helps maintain the separation of concerns and promotes good code organization.

  It's important to note that state should only be modified using `setState()`, as directly modifying state can cause unexpected behavior. It's also good practice to keep state data as minimal as possible and **pass data down** to child components as **props**.

  Here's a simple example to demonstrate how state works in React:

  ```js
  import React, { useState } from 'react'

  const MyCounter = () => {
    // Declare a state variable named "count"
    const [count, setCount] = useState(0)

    return (
      <div>
        <p>You clicked {count} times</p>
        <button onClick={() => setCount(count + 1)}>Click me</button>
      </div>
    )
  }
  ```

  In the above example, `count` is the state variable and `setCount` is a function that updates the state. The initial value of count is 0.

  When the button is clicked, the `setCount` function is called with an updated value of `count + 1`. This updates the state and triggers a re-render of the component, causing the displayed value of `count` to change.

## 🛠️ Working with Props:

- **Understanding the concept of props**<br/>
  In React, `props` are short for **"properties."** They are data passed down from a parent component to its child component(s).
  The parent component passes the data as attributes on a component's **JSX tag**, and the child component accesses the data through its `props` object.
  Props are used to make components more flexible and reusable by allowing them to receive data from the parent component and dynamically rendering based on that data.
  Here's an example of using props:

  ```js
  import React from 'react'
  const Welcome = (props) => {
    return <h1>Hello, {props.name}</h1>
  }

  const App = () => {
    return (
      <div>
        <Welcome name="Hannah" />
        <Welcome name="Zara" />
        <Welcome name="Abe" />
      </div>
    )
  }
  ```

  In this example, the `Welcome` component is a child component that receives a `name` prop from its parent component, `App`. The `Welcome` component then uses the `name` prop in its render method to display a personalized greeting. The `App` component uses the `Welcome` component three times, each with a different `name` prop, demonstrating how the same component can be reused with different data.

- **Understanding the use of context** <br/>
  Context in React is a way to pass data down the component tree **without having to pass props down through every level of the tree**. It provides a way to share data between components that are not directly connected in the component tree hierarchy.<br/>
  Context can be thought of as a global state for the React application that can be accessed by any component in the application without the need for props drilling. The context data is stored in a "provider" component, and any component that needs access to the context data can **consume** it by using a **consumer** component.
  Here is the simple of example:

  ```js
  import React, { useState, useContext } from 'react'
  // Define the context and its initial value
  const MyContext = useContext({ theme: 'light' })

  // Provider component
  const MyProvider = ({ children }) => {
    const [theme, setTheme] = useState('light')
    return <MyContext.Provider value={{ theme, setTheme }}>{children}</MyContext.Provider>
  }

  // Consumer component
  const MyConsumer = () => {
    const { theme, setTheme } = useContext(MyContext)

    return (
      <div>
        <div>Current theme: {theme}</div>
        <button onClick={() => setTheme('dark')}>Switch to dark</button>
      </div>
    )
  }
  // Usage of context
  const App = () => {
    return (
      <MyProvider>
        <MyConsumer />
      </MyProvider>
    )
  }
  ```

## 📝 Handling Forms and User Input:

- **Building form components**<br/>
  To build form components in ReactJS, you need to use state and event handling. Here's a basic example of how to create a form with a text input and a submit button:

  ```js
  import React, { useState } from 'react'

  const FormExample = () => {
    const [inputValue, setInputValue] = useState('')
    const handleSubmit = (event) => {
      event.preventDefault()
      console.log('Input value: ', inputValue)
    }

    return (
      <form onSubmit={handleSubmit}>
        <label>
          Input:
          <input type="text" value={inputValue} onChange={(e) => setInputValue(e.target.value)} />
        </label>
        <button type="submit">Submit</button>
      </form>
    )
  }
  export default FormExample
  ```

  This example above uses the `useState` hook to manage the state of the input value and the `onSubmit` event to handle the form submission. The `handleSubmit` function logs the value of the input to the console.

- **Handling form submissions**<br/>
  Handling form submissions in ReactJS involves using event handlers. The most common event handler for handling form submissions is the onSubmit event.<br/>
  Here's an example of how to handle a form submission in ReactJS:

  ```js
  import React, { useState } from 'react'
  const FormExample = () => {
    const [inputValue, setInputValue] = useState('')
    const handleSubmit = (event) => {
      event.preventDefault()
      console.log('Input value: ', inputValue)
      return (
        <form onSubmit={handleSubmit}>
          <label>
            Input:
            <input type="text" value={inputValue} onChange={(e) => setInputValue(e.target.value)} />
          </label>
          <button type="submit">Submit</button>
        </form>
      )
    }
  }
  export default FormExample
  ```

  In this example, the `handleSubmit` function is passed to the `onSubmit` event of the form. The `event.preventDefault()` method is used to prevent the default form submission behavior. Then, the `inputValue` is logged to the console.

- **Understanding controlled** and **uncontrolled components**<br/>
  In React, components can be classified as either **controlled** or **uncontrolled**. A controlled component is a component that is fully controlled by React, meaning its state and behavior are determined by React and React alone. The value of a controlled component is set by the component's state and updated through event handlers, such as onChange.

  On the other hand, an uncontrolled component is a component that is not controlled by React and its state is managed by the DOM. An uncontrolled component does not have a value set by the component's state, and its value is only updated through user interaction such as typing in a form input.

  In general, it's recommended to use controlled components for most use cases, as they provide more consistent behavior and make it easier to manage the state and behavior of the components. However, there are some cases where using uncontrolled components may be more appropriate, such as for performance reasons or for dealing with legacy code.

  Here's a simple example to demonstrate the difference between controlled and uncontrolled components in React:

  **Uncontrolled Component**:

  ```js
  class MyForm extends React.Component {
    handleSubmit = (event) => {
      event.preventDefault()
      console.log(this.input.value)
    }

    render() {
      return (
        <form onSubmit={this.handleSubmit}>
          <label>
            Name:
            <input type="text" ref={(input) => (this.input = input)} />
          </label>
          <button type="submit">Submit</button>
        </form>
      )
    }
  }
  ```

  **Controlled Component**:

  ```js
  class MyForm extends React.Component {
    state = {
      name: '',
    }

    handleChange = (event) => {
      this.setState({ name: event.target.value })
    }

    handleSubmit = (event) => {
      event.preventDefault()
      console.log(this.state.name)
    }

    render() {
      return (
        <form onSubmit={this.handleSubmit}>
          <label>
            Name:
            <input type="text" value={this.state.name} onChange={this.handleChange} />
          </label>
          <button type="submit">Submit</button>
        </form>
      )
    }
  }
  ```

  In the uncontrolled component example, the input's value is managed by the DOM and retrieved using the `ref` attribute. In the controlled component example, the input's value is managed by the component's state, and updated through the `handleChange` function.

## 🐛 Debugging and Troubleshooting:

- **Common debugging techniques**<br/>
  There are some common debugging techniques for React:

  - Use the React Developer Tools: The React Developer Tools is a browser extension that provides a deeper insight into the React component tree and makes possible to inspect and modify the component state and props.<br/>

  2. Check the component's state and props: Ensure that the component's state and props are correctly set and passed down. React Developer Tools also can be used to inspect the state and props of a component.
  3. Use console.log statements: Place console.log statements in the code to see the values of variables and expressions. This is especially useful for understanding how event handlers and lifecycle methods are being executed. <br/>
  4. Use the browser's debugging tools: The browser's debugging tools provide a wealth of information and allow us to step through the code, set breakpoints, and inspect the call stack.<br/>
  5. Check for errors in the JavaScript console: The browser's JavaScript console displays any error messages that occur while executing the code. Make sure to check the console for any error messages and stack traces that may indicate the source of the problem.<br/>
  6. Verify that event handlers are being called: Verify that the correct event handlers are being called and that they are being passed the correct arguments.
  7. Use the `setState` callback function: If update the state based on the previous state is needed, use the second argument to `setState`, which is a callback function that provides access to the previous state.

- **Understanding the browser developer tools**

  1.  The browser developer tools are a set of built-in tools that come with modern web browsers such as Google Chrome, Mozilla Firefox, Microsoft Edge, and Apple Safari and allow for the inspection, debugging, and optimization of web applications.

  2.  In the context of React, the use of these tools can be incredibly useful for the understanding and fixing of issues with components and applications.

  3.  Common features of the browser developer tools that can be used when working with React include:
      - The Element Inspector
      - The Console
      - The Network Tab
      - The Performance Tab
      - The Sources Tab
  4.  Access to the browser developer tools in a web browser can typically be obtained by right-clicking anywhere on a web page and selecting "Inspect" or "Inspect Element".
  5.  From there, various tabs and features can be navigated to in order to inspect and debug components and applications.

- **Troubleshooting common React errors**<br/>
  Here are some common errors in React and suggestions on how to troubleshoot them:

  1. **"Uncaught TypeError: Cannot read property 'map' of undefined"**


      - This error occurs when we are trying to map over a data structure that is undefined. To fix this, make sure that the data structure is properly initialized and that it is not undefined before we attempt to map over it.

  2. **"Uncaught ReferenceError: [variable name] is not defined"**


      - This error occurs when we are trying to access a variable that has not been defined. Make sure that the variable is properly declared and that it is in the correct scope.

  3. **"Element type is invalid: expected a string (for built-in components) or a class/function (for composite components) but got: [variable type]"**


      - This error occurs when we are trying to render an element that is not a valid React component. Make sure that the component we are trying to render is a properly constructed React component and that it is imported correctly.

  4. **"Can only update a mounted or mounting component"**


      - This error occurs when you are trying to update a component that has not yet been mounted. Make sure that the component has been successfully mounted before attempting to update it.

  5. **"Invalid prop [prop name] of type [prop type] supplied to [component name], expected [expected prop type]"**


      - This error occurs when you are passing a prop to a component with the wrong type. Make sure that the prop you are passing is the correct type and that it matches the expected prop type for the component.
