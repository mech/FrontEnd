# Components

```js
// List of React.DOM HTML tags
Object.keys(React.DOM)
```

```js
componentDidMount() {
  document.title = 'No need to use helmet'
}
```

## Small

Keep your components small, like very small, small. If your `render()` has more than 10 lines, it is probably way too big. The whole idea of React is code reusability so if you throw everything in one file you are losing it.

## Best Practices

* [React Best Practices and Useful Functions](https://medium.com/@nesbtesh/react-best-practices-a76fd0fbef21#.l2hcddyp7)
* Avoid Refs - when you use refs you are manipulating the VDOM directly, which means that the component will have to re-render the whole DOM tree.

## Context

* [How to safely use React context](https://medium.com/@mweststrate/how-to-safely-use-react-context-b7e343eff076#.495c4jfrr)

## Iterating Lists

* `sort()` - Make a copy before sorting as it will mutate the array
* `filter()` - You need to save original copy so that you won't lose the data forever.

```js
// Copy the data
var data = this.state.data.slice()

// Or in ES6
var data = Array.from(this.state.data)
```