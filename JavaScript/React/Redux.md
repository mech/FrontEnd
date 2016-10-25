# Redux

* [React/Redux Links](https://github.com/markerikson/react-redux-links)
* [Normalizing State Shape](https://github.com/markerikson/redux/blob/structuring-reducers-page/docs/recipes/reducers/06-NormalizingStateShape.md)
* [Structuring Reducers Recipe](https://github.com/reactjs/redux/issues/1784)
* [10 Tips for Better Redux Architecture](https://medium.com/javascript-scene/10-tips-for-better-redux-architecture-69250425af44#.uawb0d7ag)
* [Jumpsuit](https://github.com/jumpsuit/jumpsuit)
* [Redux like Dan Abramov](https://medium.com/@hackupstate/redux-like-dan-abramov-7f4184979219#.pkwk1n2eg)

## Why Redux?

If you are unhappy to pass data down and down and down to children, you should use Redux earlier. Also, do not couple data fetching with rendering. See the Full-stack React book's Timer example for passing pros up and down the chain problem.

The props approach makes it hard to verify that all these combinations and permutations of properties work as expected.

Also, sometimes you end up in scenarios where you need to "pipe through" properties from a parent to a child to a grandchild to a great-grandchild, and so on.

## Against

* [You might not need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367#.hp3iux52h)

## Dealing with Side Effects

* [Redux side effects and you](https://medium.com/javascript-and-opinions/redux-side-effects-and-you-66f2e0842fc3#.abq09r7kx)
* [#1528 - Reducer Composition with Effects in JavaScript](https://github.com/reactjs/redux/issues/1528)

## State Shape

Normalizr

## Authentication

* [react-redux-jwt-auth-example](https://github.com/joshgeller/react-redux-jwt-auth-example)
* [redux-auth-wrapper](https://github.com/mjrussell/redux-auth-wrapper)

