# 100 React Developer Roadmap Reading Notes

## [React Road Map](https://roadmap.sh/react/)

### Conditional Rendering

Components will often need to display different things depending on different conditions. In React, you can conditionally render JSX using JavaScript syntax like `if` statements, `&&` and `? :` operators.

#### Conditional returning JSX

Notice the below code containing `Item` components have their `isPacked` prop set to `true` instead of `false`. You want to add a checkmark (✔) to packed items if `isPacked={true}`.

```javascript
function Item({ name, isPacked}) {
  if (isPacked) {
    return <li className="item">{name} ✔</li>;
  }
  return <li className="item">{name}</li>;
}

export default function PackingList() {
  return (
    <section>
      <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item
        isPacked={true}
        name="Space suit"
        />
        <Item
        isPacked={true}
        name="Helmet with a golden leaf"
        />
        <Item
        isPacked={false}
        name="Photo of Tam"
        />
      </ul>
    </section>
  )
}
```

![Conditional Rendering CheckMark](../Images/conditionalRendering1.png)

Creating branching logic with JavaScript's `if` and `return` statements. In React, control flow (like conditions) is handled by JavaScript.

You can also Conditionally return nothing with `null`. Let's say you don't want to show packed items at all. A component must return something. In this case, you can return `null`:

``` javascript
if (isPacked) {
  return null;
}
  return <li className="item">{name}</li>;
```

If `isPacked` is true, the component will return nothing, `null`. Otherwise, it will return JSX to render.

```javascript
function Item({ name, isPacked }) {
  if (isPacked) {
    return null;
  }
  return <li className="item">{name}</li>;
}

export default function PackingList() {
  return (
    <section>
    <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item
        isPacked={true}
        name="Space suit"
        />
        <Item
        isPacked={true}
        name="Helmet with a golden leaf"
        />
        <Item
        isPacked={false}
        name="Photo of Tam"
        />
      </ul>
    </section>
  );
}
```

![Conditional Rendering Null](../Images/conditionalRendering2.png)

Returning `null` from a component isn't common because it might surprise a developer trying to render it.

In the first example, you may have noticed some duplicate code in the conditional statement:

```javascript
if (isPacked) {
  return <li className="item">{name} ✔</li>;
}
  return <li className="item">{name}</li>
```

This isn't harmful, but you may want to include a little JSX to make your code more [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

#### Conditional (ternary) operator(? :)

JavaScript has a compact syntax for writing a condtional expression - the conditional operator or "ternary operator".

```javascript
return (
    <li className="item">
      {isPacked ? name + ' ✔' : name}
    </li>
);
```

#### Logical AND operator (&&)

Another common shortcut you'll encounter is the JavaScript logical AND (&&) operator. Inside React components, it often comes up when you want to render some JSX when the condition is true, or render nothing otherwise. With `&&`, you could conditionally render the checkmark only if `isPacked` is `true`:

```javascript
return (
  <li className="item">
    {name} {isPacked && '✔'}
  </li>
)
```

You can read this as "if `isPacked`, then (`&&`) render the checkmark, otherwise, render nothing".

```javascript
function Item({ name, isPacked }) {
  return (
    <li className="item">
      {name} {isPacked && '✔'}
    </li>
  );
}

export default function PackingList() {
  return (
    <section>
      <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item
        isPacked={true}
        name="Space suit"
        />
        <Item
        isPacked={true}
        name="Helmet with a golden leaf"
        />
        <Item
        isPacked={false}
        name="Photo of Tam"
        />
      </ul>
    </section>
  );
}

```

![Conditional Rendering &&](../Images/conditionalRendering3.png)

A JavaScript && expression return sthe value of its right side (in our case, the checkmark) if the left side (our condition) is `true`. But if the condition is `false`, the whole expression becomes `false`. React considers `false` as a "hole" in the JSX tree, just like `null` or `undefined`, and doesn't render anything in its place.

##### Don't put numbers on the left side of &&

To test the condition, JavaScript converts the left side to a boolean automatically. However, if the left side is `0`, then the whole expression gets the value (`0`), and React will happily render `0` rather than nothing.

For example, a common mistake is to write code with `messageCount && <p>New messages</p>`. It's easy to assume that it renders nothing when `messageCount` is `0`, but it really renders the `0` itself!

To fix it, make the left side a boolean: `messageCount > 0 && <p>New messages</p>`.

#### Conditionally assigning JSX to a variable

When the shortcuts get in the way of writing plain code, try using an `if` statement and a variable. You can reassign variables defined with `let`, so start by providing the default content you want to display, the name:

```javascript
let itemContent = name;
```

Use an `if` statement to reassign a JSX expression to `itemContent` if `isPacked` is `true`:

```javascript
if (isPacked) {
  itemContent = name + "✔";
}
```

Curly braces open the "window into JavaScript". Embed the variable with curly braces in the returned JSX tree, nesting the previously calculated expression inside of JSX:

```javascript
<li className="item">
  {itemContent}
</li>
```

Lets try it out with some arbitrary JSX:

```javascript
function Item({ name, isPacked }) {
  let itemContent = name;
  if (isPacked) {
    itemContent = (
      <del>
        {name + " ✔"}
      </del>
    );
  }
  return (
    <li className="item">
      {itemContent}
    </li>
  );
}

export default function PackingList() {
  return (
    <section>
      <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item
          isPacked={true}
          name="Space suit"
        />
        <Item
          isPacked={true}
          name="Helmet with a golden leaf"
        />
        <Item
          isPacked={false}
          name="Photo of Tam"
        />
      </ul>
    </section>
  );
}
```

![Conditional Rendering with variables](../Images/conditionalRendering4.png)

[<---BACK](README.md)

##### Citations

- [Conditional Rendering](https://beta.reactjs.org/learn/conditional-rendering)
