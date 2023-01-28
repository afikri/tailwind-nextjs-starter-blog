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

1. Create a new folder for your project and navigate to it in the command line.
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

- Understanding the concept of state in React
- Using the setState() method to update state
- Using state in a functional component
- Understanding the useState() hook

## 🛠️ Working with Props:

- Understanding the concept of props in React
- Passing data from parent to child components
- Understanding the use of context

## Handling Forms and User Input:

- Building form components
- Handling form submissions
- Understanding controlled and uncontrolled components

## Building a Complete Application:

- Setting up a routing system
- Creating a CRUD application
- Using external APIs with React
- Understanding the useEffect() hook

## Debugging and Troubleshooting:

- Common debugging techniques
- Understanding the browser developer tools
- Troubleshooting common React errors

## Deployment and Optimization:

- Preparing the application for production
- Understanding the use of webpack
- Optimizing the performance of a React application

## Advanced Topics:

- Server-side rendering
- Code splitting
- Higher-order components
- Render props
- Concurrent mode
