# React Element vs Component

## React Elements, Components, and Instances

React Element, Component, and Instances are different terms in React which work closely together.

```javascript
const App = () => {
  return <p>Hello React</p>;
}
```

A **React component** is literally the declaration of a component as we see it in the previous code snippet. In our case, it's a function component but it could be any other kind of React component (e.g. React Class Component) too.

In the case of a function component, it is declared as a JavaScript function which returns React's JSX. While more complex JSX is a mixture of HTML and JavaScript, here we are dealing with a simple example which return sjust one HTML element whi an inner content.

```javascript
(props) => JSX
```

We can extract a component from another component and render it the following way. Rendering a component happens whenever we use this component as a **React element** with angle brackets (e.g. <Greeting />) in another component:

```javascript
const Greeting = ({ text }) => {
  return <p>{text}</p>;
};

const App = () => {
  return <Greeting text="Hello react"/>;
}
```

We can render a component as React element multiple times too. Whenever a component gets renderedd as element, we create an **instance of this component:**

```javascript
const Greeting = ({ text }) => {
  return <p>{text}</p>;
};

const App = () => {
  return (
    <>
      <Greeting text="Hello Instance 1 of Greeting" />
      <Greeting text="Hello Instance 2 of Greeting" />
    </>
  );
};
```

While a React Component is declared once, it can be used multiple times as a React element in JSX. When it is used, it becomes an instance of the component and lives in React's component tree. Essentially that's the explanation of React components, element, and instance in a nutshell. However, in order to understand everything on a deeper level, we need to understand how React displays HTML with JSX.

------------

## React Elements in Depth

Taking on step back and start with a simple example again:

```javascript
const App = () => {
  return <p>Hello React</p>;
};
```

Whenever a React component gets called (rendering), React calls its `React.createElement()` method internally which returns the following object:

```javascript
console.log(App());
// {
//   $$typeof: Symbol(react.element)
//   "type": "p",
//   "key": null,
//   "ref": null,
//   "props": {
//     "children": "Hello React"
//   },
//   "_owner": null,
//   "_store": {}
// }
```

1. ****
2. ****
3. ****
4. ****
5. ****
6. ****
7. ****

## Things I want to know more about

### Citation: [What is the difference between components, elements, and instances?](https://www.robinwieruch.de/react-element-component/)

[<---BACK](README.md)
