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

1. ****
2. ****
3. ****
4. ****
5. ****
6. ****
7. ****

## Things I want to know more about

[<---BACK](README.md)
