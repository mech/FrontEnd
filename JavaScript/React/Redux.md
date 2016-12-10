# Redux

> Use Redux state for globally interesting states like auth, contract_code, etc. Use React state for complex form that can be isolated like TAKE_LEAVE, etc.

* [React/Redux Links](https://github.com/markerikson/react-redux-links)
* [Normalizing State Shape](https://github.com/markerikson/redux/blob/structuring-reducers-page/docs/recipes/reducers/06-NormalizingStateShape.md)
* [Structuring Reducers Recipe](https://github.com/reactjs/redux/issues/1784)
* [10 Tips for Better Redux Architecture](https://medium.com/javascript-scene/10-tips-for-better-redux-architecture-69250425af44#.uawb0d7ag)
* [Jumpsuit](https://github.com/jumpsuit/jumpsuit)
* [Redux like Dan Abramov](https://medium.com/@hackupstate/redux-like-dan-abramov-7f4184979219#.pkwk1n2eg)
* [Making sense of Redux](https://medium.freecodecamp.com/why-redux-makes-sense-to-me-and-how-i-conceptualize-it-c8a3a9db15ca#.rd78c8v6k)
* [Redux Step by Step: A Simple and Robust Workflow for Real Life Apps](https://hackernoon.com/redux-step-by-step-a-simple-and-robust-workflow-for-real-life-apps-1fdf7df46092#.43zajz8e6)
* [Rules for structuring Redux applications](http://jaysoo.ca/2016/02/28/organizing-redux-application/)
* [Why Redux need reducers to be "pure functions"](https://medium.freecodecamp.com/why-redux-needs-reducers-to-be-pure-functions-d438c58ae468#.lm1nbvubo)
* [Redux-ORM??](http://blog.isquaredsoftware.com/2016/10/practical-redux-part-1-redux-orm-basics/)

## Why Redux?

Redux aims to decouple state mutation (state transformation) and asynchronicity (side-effect), separating them so that you can reason about them individually.

> Separation of asynchronous logic from state mutation.
> 
> Predictability and testability

If you are unhappy to pass data down and down and down to children, you should use Redux earlier. Also, do not couple data fetching with rendering. See the Full-stack React book's Timer example for passing pros up and down the chain problem.

The props approach makes it hard to verify that all these combinations and permutations of properties work as expected.

Also, sometimes you end up in scenarios where you need to "pipe through" properties from a parent to a child to a grandchild to a great-grandchild, and so on.

## Against

* [You might not need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367#.hp3iux52h)

## Core Principles

1. Single source of truth
2. State is read-only
3. Changes are made with pure function

## Reducers - Stateless Stores

```js
const reducer = (state = {}, action) => ({
  trey: treyReducer(state.trey, action),
  billing: billingReducer(state.billing, action)
})

const store = createStore(reducer)

store.dispatch(takeLeave(leaveSpec))

const newState = store.getState()
```

## Dealing with Side Effects

* [Redux side effects and you](https://medium.com/javascript-and-opinions/redux-side-effects-and-you-66f2e0842fc3#.abq09r7kx)
* [#1528 - Reducer Composition with Effects in JavaScript](https://github.com/reactjs/redux/issues/1528)

## State Shape

Normalizr

## Authentication

* [react-redux-jwt-auth-example](https://github.com/joshgeller/react-redux-jwt-auth-example)
* [redux-auth-wrapper](https://github.com/mjrussell/redux-auth-wrapper)

## Thunk

* [What is a thunk?](https://daveceddia.com/what-is-a-thunk/)
* [Why doesn't Redux support AJAX out of the box?](http://goshakkk.name/redux-no-ajax-by-default/)

Action is just an object. Almost nobody want to type out the object over and over again, so they use Action Creator. When you want to perform Ajax call, you cannot possibly do it at the Reducer since it is a pure function (after all, the reducer is a predictable state container).

## People

* [Jack Hsu](http://jaysoo.ca/)