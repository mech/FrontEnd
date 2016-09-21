# State Management

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