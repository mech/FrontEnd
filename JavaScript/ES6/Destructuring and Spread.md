# Destructuring and Spread

## Object Destructuring

## Array Spread

```js
// New way
const state = []
const todo = { id: 123, title: 'hello' }
[...state, todo]

// Old way
const newState = state.slice()
newState.push(todo)
```

**Remove**

```js
// Remove last item
items.slice(0, -1)

// Remove first item and return the rest
const [last, ...rest] = items

// Remove by predicate
const removeItemById = (items, id) => items.filter(item => item.id != id)
```

## Object Spread (In proposal as of Dec 2016)

```js
// Using object spread operator
const toggleTodo = (todo) => ({
  ...todo,
  completed: !todo.completed
})

// Using Object.assign, another alternative
const toggleTodo = (todo) => (Object.assign({}, todo, {
  completed: !todo.completed
}))
```

`Object.assign` is implemented as:

```js
var _extends = Object.assign || function(target) {
  for (var i = 1; i < arguments.length; i++) {
    var source = arguments[i];
    for (var key in source) {
      if (Object.prototype.hasOwnProperty.call(source, key)) {
        target[key] = source[key];
      }
    }
  }
  
  return target;
}
```

**Remove property from object**

```js
const removeTodo = (state = {}, { type, id }) => {
  switch (type) {
    case 'removeTodo':
      // Using object spread, object destructuring and computed property name
      // We are extracting a property from state by name using computed property
      // and storing that in the remove variable. At the same time, we're using
      // the object rest to extract the remaining properties into rest variable.
      const { [id]: remove, ...rest } = state;
      return rest;
    default:
      return state;
  }
}

// Same as
const newState = Object.assign({}, state);
delete newState[id];
```

## Ramda or Lodash

Use Ramda's `merge`, `dissoc`, `prepend`, `without`, etc. can make the intent of our code clearer.

```js
// Ramda library
merge(state, { [payload.id]: payload });

// ES6
Object.assign({}, state, { [payload.id]: payload })

// ES7
{ ...state, [payload.id]: payload }
```