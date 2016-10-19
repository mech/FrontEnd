# State Management

You declare how your UI will look like in the `render` method and the rest is just state management. There is no DOM manipulation anymore.

> If a parent needs to know about it, the parent should own it.

Here are 2 red flags:

```js
// If the child change state and also tell parent, it is a red flag.
// Might as well let the parent own the state.
handleClick() {
  this.props.onClick();
}

// Anything to do with a refs is also a red flag.
getClickedState() {
  return this.refs.child.hasBeenClicked();
}
```

### Initial States

Using props in your initial state is actually an anti-pattern. But sometimes it is still a valid use-case. In such cases, it is better to tweak the naming to `defaultXXX` or `initialXXX`.

```js
getInitialState() {
  return {
    text: this.props.defaultText,
    data: this.props.initialData,
    edit: null // { row: index, cell: index }
  }
}
```

## Bad Practices

* Do not update `this.state` directly as this can have unpredictable or unexpected behavior. React uses batch updating and is asynchronous.

## Best Practices

* [Avoiding Accidental Complexity When Structuring Your App State](https://hackernoon.com/avoiding-accidental-complexity-when-structuring-your-app-state-6e6d22ad5e2a#.n7448vuau)

---

* Avoid modelling state after server REST API.
* Prefer maps to arrays. Iterating over a large array to find specific product ID is much less convenient than just querying the map's key.
* Avoid modelling state after what views like to consume.
* Never hold duplicate data in the app state.
* Never store derived data in the state.

```js
{
  "productById": {
    "88cd7621-d3e1": { "title": "Blue Shirt", "price": 9.99 },
    "aec17a8e-4793": { "title": "Red Shirt", "price": 7.99 }
  },
  "productIds": [
    "aec17a8e-4793",
    "88cd7621-d3e1"
  ]
}
```

## Props

```js
// Properties are immutable and read-only
Object.isFrozen(this.props) === true
```

Props are immutable, once defined it is unlikely you want to change that. However if you do want to change props mid-flight you can use `componentWillReceiveProps` lifecycle hooks to adjust your internal state.

### Default Property Values

If you take optional props, make sure that the component still works with missing props. Defensive programming.

