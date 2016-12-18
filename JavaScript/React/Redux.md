# Redux

> Use Redux state for globally interesting states like auth, contract_code, etc. Use React state for complex form that can be isolated like TAKE_LEAVE, etc.

If you're just using local component state, there is no need for any state-management libraries like Redux or MobX.

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
* [Redux Performance](https://github.com/markerikson/react-redux-links/blob/master/react-performance.md#redux-performance)

## Functional Components

Function components cannot have internal state or methods. This is just fine for Redux since call of our state lives inside of Redux (as opposed to local component state), and our actions are defined separated as action creators (as opposed to methods on the component class).

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
* [The M and C in MVC](https://www.youtube.com/watch?v=fUpkYixd03k)
* [Slow performance when there are too many subscribers](https://hackernoon.com/an-artificial-example-where-mobx-really-shines-and-redux-is-not-really-suited-for-it-1a58313c0c70#.myoxg2h43)
* [Reddit discussion on react-redux@5](https://www.reddit.com/r/reactjs/comments/5hf4d4/an_artificial_example_where_mobx_really_shines/)

We need to be careful when using Redux, which is essentially a global state. It will make your component less reusable and isolated because it is link to the Redux global state store.

If every keystroke need to reach out to the global store and re-render, then that is a performance problem. Redux is not suitable for this high interactive behavior.

## Memoization of Props

* [v4](https://github.com/dtinth/pixelpaint/pull/1)

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

**Note: Don't render too many things on the screen, Redux can't handle it.**

With Redux, you can only subscribe to the store as a whole. You can't subscribe to a subtree of your state, because that subtree is just a plain old JavaScript object which can't be subscribed to. You are forced to re-render everything and using immutability for performance issues.

## Dealing with Side Effects

* [Redux side effects and you](https://medium.com/javascript-and-opinions/redux-side-effects-and-you-66f2e0842fc3#.abq09r7kx)
* [#1528 - Reducer Composition with Effects in JavaScript](https://github.com/reactjs/redux/issues/1528)

## State Shape

Normalizr

## Entity Modules

Always encapsulate how you represent entity in a system. Don't couple your application logic to data structures. You can start with `Array` at first and go into `Immutable.Map` later.

> It would be very hard to make this kind of change if our reducer/selector/view code accessed the contents of these data structures directly. - [](https://medium.com/@dtinth/immutable-js-persistent-data-structures-and-structural-sharing-6d163fbd73d2#.qkhvl3cn4)

**Reverse lookup**

- https://medium.com/@thisismissem/how-did-you-do-about-doing-this-fbbd730ccfb5#.amo4avft0
- https://github.com/ThisIsMissEm/mesos-dashboard-challenge/blob/master/src/reducers/index.js

## Authentication

* [react-redux-jwt-auth-example](https://github.com/joshgeller/react-redux-jwt-auth-example)
* [redux-auth-wrapper](https://github.com/mjrussell/redux-auth-wrapper)

## Provider

Only one Provider is necessary, and ideally it should be as high-up in your component tree as possible. This is done to avoid trying to connect a component outside of Provider's scope.

## Thunk

* [What is a thunk?](https://daveceddia.com/what-is-a-thunk/)
* [Why doesn't Redux support AJAX out of the box?](http://goshakkk.name/redux-no-ajax-by-default/)

Action is just an object. Almost nobody want to type out the object over and over again, so they use Action Creator. When you want to perform Ajax call, you cannot possibly do it at the Reducer since it is a pure function (after all, the reducer is a predictable state container).

## Replace Reducer?

## People

* [Jack Hsu](http://jaysoo.ca/)