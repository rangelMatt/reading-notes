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

Focus your attention on the `type` and `props` properties of this object: While the type represents the actual HTML element, the `props` are all HTML attributes (plus the inner content, read: children) which are passed to this HTML element.

When looking at the paragraph HTML element from above, you can see that no attributes are passed to it. However, React treats `children` as pseudo HTML attribute whereas `children` represents everything that's rendered between the HTML tag. This fact becomes clearer when adding an attribute to the paragraph HTML element:

```javascript
const App = () => {
  return <p className="danger">Hello React</p>;
};

console.log(App());

// {
//   $$typeof: Symbol(react.element)
//   "type": "p",
//   "key": null,
//   "ref": null,
//   "props": {
//     "children": "Hello React",
//     "classsName": "danger"
//   },
//   "_owner": null,
//   "_store": {}
// }
```

Essentially React translates all HTML attributes to React props in addition to adding the inner content as `children` property.

As mentioned, React's `createElement()` method is call internally. Therefore we could use it as replacement for the returned JSX (for the sake of learning). React's createElement method takes a type, props, and children as arguments. We provide the HTML tag 'p' as first argument, the `props` as an object with the className as second argument, and the `children` as third argument:

```javascript
const App = () => {
  // return <p className="danger">Hello React</p>;
  return React.createElement(
    'p',
    { className: 'danger' },
    'Hello React'
  );
};
```

Notice how the method call does not reflect 1:1 returned object where the `children` are part of the `props` object. Instead, when calling React's `createElement()` method, the children are provided separately as argument. However, since children are treated as props, we could also ass them in the second argument:

```javascript
const App = () => {
  // return <p className="danger">Hello React</p>;
  return React.createElement(
    'p',
    {
      className: 'danger',
      children: 'Hello React'
    }
  );
};
```

As default children are used as third argument though. The following example shows how a REact Component, which renders a HTML tree as JSX, translates into React element(s) with React's `createElement()` method. The important lines are highlighted:

```javascript
const App = () => {
  return (
    <div className="container">
      <p className="danger">Hello React</p>
      <p className="info">You rock, React</p>
    </div>
  );
};

console.log(App());

{
  $$typeof: Symbol(react.element)
  "type": "div", // <Highlight/>
  "key": null,
  "ref": null,
  "props": {
    "className": "container", // <Highlight/>
    "children": [ // <Highlight/>
      {
        $$typeof: Symbol(react.element)
        "type": "p", // <Highlight/>
        "key": null,
        "ref": null,
        "props": { // <Highlight/>
          "className": "danger", // <Highlight/>
          "children": "Hello React" // <Highlight/>
        }, // <Highlight/>
        "_owner": null,
        "_store": {}
      },
      {
        $$typeof: Symbol(react.element)
        "type": "p", // <Highlight/>
        "key": null,
        "ref": null,
        "props": { // <Highlight/>
          className: "info", // <Highlight/>
          children: "You rock, React!" // <Highlight/>
        }, // <Highlight/>
        "_owner": null,
        "_store": {}
      }
    ] // <Highlight/>
  },
  "_owner": null,
  "_store": {}
}

```

Again internally all JSX gets translated with React's createElement() method. While we return one element as object, it has multiple inner elements as children in this example. This becomes more obvious when calling the method for creating the element ourselves:

```javascript
const App = () => {
  // return (
  //   <div className="container">
  //     <p className="danger">Hello React</p>
  //     <p className="danger">Hello React</p>
  // );

  return React.createElement(  // <Highlight/>
    'div', // <Highlight/>
    { // <Highlight/>
      className: 'container', // <Highlight/>
    }, // <Highlight/>
    [ // <Highlight/>
      React.createElement( // <Highlight/>
        'p', // <Highlight/>
        { className: 'danger' }, // <Highlight/>
        'Hello React'  // <Highlight/>
      ), // <Highlight/>
      React.createElement( // <Highlight/>
        'p', // <Highlight/>
        { className: 'info'}, // <Highlight/>
        'You rock, React!' // <Highlight/>
      ), // <Highlight/>
    ] // <Highlight/>
  ); // <Highlight/>
}
```

### Citation: [What is the difference between components, elements, and instances?](https://www.robinwieruch.de/react-element-component/)

[<---BACK](README.md)
