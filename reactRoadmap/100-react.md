# 100 React Developer Roadmap Reading Notes

## [React Road Map](https://roadmap.sh/react/)

### Create React App

`Create React App` is a CLI based tool and is the best way to start building a new single-page application in React.

This development environment can be used to serve the latest JavaScript features, provides a nice developer experience, and optimizes your app for production.

### Components

`Components` are the building blocks of React applications. They let us split the UI into independent, reusable pieces, and think about each piece in isolation.

Components accept arbitrary inputs (called `props`) and return React elements describing what should appear on the screen.

The below is a function that is a valid React component because it accepts a single `props` (which stands for properties) object argument with data and returns a React element. This is an example of `function components` because they are literally JavaScript functions.

```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
const root = 
ReactDOM.createRoot(document.getElementById('root'));
const element = <Welcome name="Matt"/>;
root.render(element);
```

What's happening in this example:

1. We call `root.render()` with the `<Welcome name="Matt"/>` element.
2. React calls the `Welcome` component with `{name: 'Matt'}` as the props.
3. Our `Welcome` component returns a `<h1>Hello, Matt</h1>` element as the result.
4. React DOM efficiently updates the DOM to match `<h1>Hello, Matt</h1>`.

#### The Component Lifecycle

Each component has several `lifecycle methods` that you can override to run code at particular times in the process. Use this [lifecycle diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/) as a cheat sheet. In the list below, commonly used lifecycle methods are marked as **bold**. The rest of them exist for relatively rare use cases.

##### Mounting

These methods are called in the following order when an instance of a component is being created and inserted into the DOM:

- **constructor()**
  - Initializing `local state` by assigning an object to `this.state`.
  - Binding `event handler` methods to an instance.
  - Do *not*:
    - call **setState()** in the `constructor()`.
    - Copy props into state.
      - `this.state = { color: props.color };`
- static getDerivedStateFromProps()
- **render()**
  - Only method that is required in a class component.
- **componentDidMount()**
  - Invoked immediately after a component is mounted (inserted into the tree). Initialization that requires DOM nodes should go here.

#### Class Components

Components can either be created using the class based approach or a functional approach. These components are simple classes (made up of multiple functions that add functionality to the components are child classes for the Component class of ReactJS.

Although the class components are supported in React, it is encouraged to write functional components and make use of hooks in modern React applications.

The downside of Class components is that you will be downloading a bunch of preloaded libraries whether you want them or not. As your code base grows bigger and bigger this means more data must be transferred on each page load and longer and longer rendering times.




#### Functional Components

`Functional Components` are some of the more common components that will come across while working in React. These are simply JavaScript functions. We can create a functional component to React by writing a JavaScript function. These functions may or may not receive data as parameters. in the functional Components, the return value is the JSX code to render to the DOM tree. Functional components can also have state which is managed using React hooks.

Hooks are special functions that allow ReactJS features to be used in **functional components**.

`Functional Components` do not have access to dedicated state variables like `class-based components`. ReactJS has access to a special hook called `useState()` that cna be used for giving the illusion of working with the state in functional components. The `useState()` is used to initialize only one state variable to initialize multiple state variables, multiple `useState()` declarations are required. The first value returned is the initial value of the state variable, while the second value returned is a reference to the function that updates it. When the state variable needs to be updated, it can be done by calling the update function and by updating the state variable directly inside it.

```javascript
import React, { useState } from 'react';

const Example=()=> {
  // initializing state at `change` then updating state `setChange` starting at true to false
const [change, setChange] = useState(true); 
 return (
  <div>
  // once the button is clicked, setChange will be called and change will update to false...
  <button onClick = {() => setChange(!change)}>
  Click Here!
  </button>
  // ... which will update our ternary from true to false, which is the latter choice after the colon (:).
  {change?<h1>Welcome to Geeks for Geeks</h1>:
    <h1>A Computer Science Portal for Geeks</h1>}
  </div>
  );
}

export default Example;

```

Lifecycle functions like class-based components are not accessible to Functional components since lifecycle functions need to be defined within the boundaries of a class. If lifecycle functions need to be used with functional components, a special React hook called `useEffect()` isn't an exact duplicate of the lifecycle functions - it works and behaves in a slightly different manner.

```javascript
import React, { useEffect } from 'react';

const Example=()=> {
useEffect(() => {
 console.log("Mounting...");
});
 return (
 <h1>
  Geeks....!
 </h1>
 );
}

export default Example;

```

Data is passed from the parent component to the child components in the form of props. ReactJS does not allow a component to modify its own props as a rule. The only way to modify the props is to change the props being passed to the child component. This is generally done by passing a reference of a function in the parent component to the child component. Props have more significance in functional components for the simple reason that functional components do not have access to a state, unlike class-based components.

1. ****
2. ****
3. ****
4. ****
5. ****
6. ****
7. ****

## Things I want to know more about

[<---BACK](README.md)
