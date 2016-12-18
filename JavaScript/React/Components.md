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

## PropTypes

```js
class MatchInfo extends Component {
  static propTypes = {
    tournament: PropTypes.shape({
      active: PropTypes.shape({
        type: TournamentTypeShape
      })
    }),
    match: PropTypes.shape({
      active: PropTypes.shape({
        scores: MatchScoresShape,
        teams: MatchTeamsShape
      })
    })
  }
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

* `sort()` - Make a copy before sorting as `sort()` mutate the original array
* `filter()` - You need to save original copy so that you won't lose the data forever.
* `concat()` - add a new item, return a new array

```js
// Copy the data
var data = this.state.data.slice()

// Or in ES6
var data = Array.from(this.state.data)
```

Having a list naming convention like `TimerList`, `ProductList`, `XXXList` make it easier to know that component only renders a list of children and no more.

```js
// Object.assign is used to create new object instead of modifying existing ones.
// Notice we map over and do a total replacement for the affected timer,
// while leaving the others untouched.
updateTimer(attrs) {
  this.setState({
    timers: this.state.timers.map((timer) => {
      if (timer.id === attrs.id) {
        return Object.assign({}, timer, {
          title: attrs.title,
          project: attrs.project
        })
      } else {
        return timer
      }
    })
  })
}
```

## Deleting Lists

There are many ways to delete an item from an array. You can use `filter()` or `splice()`.

```js
// filter() returns new array!
deleteTimer(timerId) {
  this.setState({
    timers: this.state.timers.filter(t => t.id !== timerId)
  })
}
```
