# 100 React Developer Road Map Reading Notes

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
const root = ReactDOM.createRoot(document.getElementById("root"));
const element = <Welcome name="Matt" />;
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
  - Do _not_:
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

With functional components the component start out much lighter and you can add capabilities as you need them. Yes it may take a little bit more work when creating the component to go and import the `useState` and `useEffect` hooks, and to set each one up rather than having it reloaded for you, but that little bit of extra work could pay dividends in terms of app loading size and file size when you start expanding your application.

For most application, `useState`, `useEffect`, and `useContext` should cover about 99% of the things you would need a Class Component for. There are also [**several more hooks**](https://reactjs.org/docs/hooks-reference.html) for use in more specific applications.

But if you are a newbie, focus on and master useState, useEffect, and `useContext`.

```javascript
import { useState } from 'react';

function MyComponent() {
  const [age, setAge] = useState(28);
  const [name, setName] = useState('Taylor');
  const [todos, setTodos] = useState(() => createTodos());
```

The convention is to name state variables like [something, setSomething] using array destructing.

##### Parameters for `useState(initialState)`

- `initialState`: The value you want the state to be initially. It can be a value of any type, but there is a special behavior for functions. This argument is ignored after the initial render.
  - If you pass a function as `initialState`, it will be treated as an initializer function. It should be pure, should take no arguments, and should return a value of any type. React will call your initializer function when initializing the component, and store its value as the initial state.

##### Returns

`useState` returns an array with exactly two values:

1. the current state. During the first render, it will match the `initialState` you have passed.
2. The `set` function that lets you update the state to a different value and trigger a re-render.

##### Caveats

- `useState` is a Hook, so you can only call it _at the top level of your component_ or your own Hooks. You can't call it inside loops or conditions. If you need that, extract a new component and move the state into it.
- In Strict Mode, React will _call your initializer function twice_ in order to help you find accidental impurities. This is development-only behavior and does not affect production. If your initializer function is pure (as it should be), this should not affect the logic of your component. The result from one of the calls will be ignored.

##### `set` functions, like `setSomething(nextState)`

The `set` function returned by `useState` lets you update the state to a different value and trigger a re-render.You can pass the next state directly , or a function that calculates it from the previous state:

```javascript
const [name, setName] = useState("Edward");

function handleClick() {
  setName("Taylor");
  setAge((a) => a + 1);
}
```

##### Parameters

- `nextState:`: The value that you want the state to be. It can be a value of any type, but there is a special behavior for functions.
  - If you pass a function as `nextState`, it will be treated as an _updater function_. It must be pure, should take the pending state as its only argument, and should return the next state. React will put your updater function in a queue and re-render your component. During the next render, React will calculate the next state by applying all of the queued updaters to the previous state.

##### **Returns** `set` functions, like `setSomething(nextState)`

`set` functions do not have a return value.

##### **Caveats** `set` functions, like `setSomething(nextState)`

- The `set` function **only updates the state variable for the _next_ render**. If you read the state variable after calling the `set` function, you will still get the old value that was on the screen before your call.
- If the new value you provide is identical to the current `state`, as determined by an `Object.is` comparison, React will skip re-rendering the component and its children. This is an optimization. Although in some cases React may still need to call your component before skipping the children, it shouldn't affect your code.
- React [batches state updates](https://beta.reactjs.org/learn/queueing-a-series-of-state-updates). It updates the screen **after all the event handlers have run** and have called their `set` functions. This prevents multiple re-renders during a single event. In the rare case that you need to force React to update the screen earlier, for example to access the DOM, you can use `flushSync`.
- Calling the `set` function _during rendering_ is only allowed from within the currently rendering component. React will discard its output and immediately attempt to render it again with the new state. This pattern is rarely needed, but you can use it to **store information from the previous renders**.
- In Strict Mode, React will **call your updater function twice** in order to [help you find accidental impurities](https://beta.reactjs.org/reference/react/useState#my-initializer-or-updater-function-runs-twice). This is development-only behavior and does not affect production. If your updater function is pure (as it should be), this should not affect the logic of your component. The result from one of the calls will be ignored.

##### Usage

**Adding state to a component**: Call `useState` at the top level of your component to declare one or more state variables.

```javascript
import { useState } from "react";

function MyComponent() {
  const [age, setAge] = useState(42);
  const [name, setName] = useState("Taylor");
}
```

The convention is to name state variables like `[something, setSomething]` using array destructuring.

`useState` returns an array with exactly two items:

1. The `current state` of this state variable, initially set to the `initial state` you provided.
2. The `set function` that lets you change it to any other value in response to interaction.

To update what's on the screen, call the `set` function with some next state:

```javascript
function handleClick() {
  setName("Robin");
}
```

React will store the next state, render your component again with the new values, and update the UI.

##### 1. Counter (number)

```javascript
import { useState } from "react";

export default function MyInput() {
  const [text, setText] = useState("hello");

  function handleChange(e) {
    setText(e.target.value);
  }
  return (
    <>
      <input value={text} onchange={handleChange} />
      <p>You typed: {text}</p>
      <button onClick={() => setText("hello")}>Reset</button>
    </>
  );
}
```

##### 4. Form (two variables)

```javascript
import { useState } from 'react;

export default function Form() {
  const [name, setName] = useState('Taylor');
  const [age, setAge] = useState(42);

  return (
    <>
    <input
    value={name}
    onChange={e => setName(e.target.value)}
    />
    <button onClick={() => setAge(age + 1)}>
    Increment age
    </button>
    <p>Hello, {name}. You are {age}.</p>
    </>
  );
}
```

Please click [here](https://beta.reactjs.org/reference/react/useState#usestate) for more examples

##### Final Verdict

**99.9% of the time you should be using Functional Components**.

#### Functional Components

`Functional Components` are some of the more common components that will come across while working in React. These are simply JavaScript functions. We can create a functional component to React by writing a JavaScript function. These functions may or may not receive data as parameters. in the functional Components, the return value is the JSX code to render to the DOM tree. Functional components can also have state which is managed using React hooks.

Hooks are special functions that allow ReactJS features to be used in **functional components**.

`Functional Components` do not have access to dedicated state variables like `class-based components`. ReactJS has access to a special hook called `useState()` that cna be used for giving the illusion of working with the state in functional components. The `useState()` is used to initialize only one state variable to initialize multiple state variables, multiple `useState()` declarations are required. The first value returned is the initial value of the state variable, while the second value returned is a reference to the function that updates it. When the state variable needs to be updated, it can be done by calling the update function and by updating the state variable directly inside it.

```javascript
import React, { useState } from "react";

const Example = () => {
  // initializing state at `change` then updating state `setChange` starting at true to false
  const [change, setChange] = useState(true);
  return (
    <div>
      // once the button is clicked, setChange will be called and change will
      update to false...
      <button onClick={() => setChange(!change)}>Click Here!</button>
      // ... which will update our ternary from true to false, which is the
      latter choice after the colon (:).
      {change ? (
        <h1>Welcome to Geeks for Geeks</h1>
      ) : (
        <h1>A Computer Science Portal for Geeks</h1>
      )}
    </div>
  );
};

export default Example;
```

Lifecycle functions like class-based components are not accessible to Functional components since lifecycle functions need to be defined within the boundaries of a class. If lifecycle functions need to be used with functional components, a special React hook called `useEffect()` isn't an exact duplicate of the lifecycle functions - it works and behaves in a slightly different manner.

```javascript
import React, { useEffect } from "react";

const Example = () => {
  useEffect(() => {
    console.log("Mounting...");
  });
  return <h1>Geeks....!</h1>;
};

export default Example;
```

Data is passed from the parent component to the child components in the form of props. ReactJS does not allow a component to modify its own props as a rule. The only way to modify the props is to change the props being passed to the child component. This is generally done by passing a reference of a function in the parent component to the child component. Props have more significance in functional components for the simple reason that functional components do not have access to a state, unlike class-based components.

#### React Hooks Migration

React Hooks were introduced to React to make state and side-effects available in React Function Components. Before it was only possible to have these in React Class Components; but since React's way of implementing Components has changed over the years, we have the class component's features available with React Hooks in React Function Components now.

##### Component State with React's useState hooks

React Class Components were the go-to solution when implementing stateful components. It's possible to allocate initial state in a constructor, write state with the give `this.setState()` method -- which often happened in a class method --, and read state with `this.state` from the component instance.

```javascript
class App extends React.Component {
  constructor(props) {
    super(props);

    this.state = {
      this.setState({ value: e.target.value});

      render() {
        return (
          <div>
          <h1>Hello React ES6 Class Component!</h1>

          <input
          value={this.state.value}
          type="text"
          onChange={this.onChange}
          />

          <p>{this.state.value}</p>
          </div>
        );
      }
    }
}
```

A Function Component is able to do the same now by using a React Hook called useState. The hook let's us allocate initial state (e.g. an empty string) and returns an array which as the state and a function to set the state. By using JavaScript Array Destructuring, we can conveniently extract the reutnr values from the hook in one line of code:

```javascript
const App = () => {
  const [value, setValue] = React.useState("");

  const onChange = (e) => setValue(e.target.value);

  return (
    <div>
      <h1>Hello React Function Component!</h1>

      <input value={value} type="text" onChange={onChange} />
      <p>{value}</p>
    </div>
  );
};
```

By nature React Function Components are way more lightweight than React Class Components. You don't need to deal with a constructor or class methods anymore, because th eReact Hook for state managements let's you initialize component state and other functions can be defined inline in the Function Component (e.g. onChange()).

If the next React Component you are going to implement has to manage state, don't default to a React Class Component, but give React Function Components with React Hooks a shot.

## JSX

`JSX` stands for JavaScript XML. It allows writing HTML in JavaScript and converts the HTML tags into React Elements.

Example:

```javascript
class JSXDemo extends React.Component {
  render() {
    const jsx = <h1>This is JSX</h1>;
    console.log(jsx);
    return jsx;
  }
}

ReactDOM.render(<JSXDemo />, document.getElementById("root"));
```

## Things I want to know more about

[<---BACK](README.md)
