# Block Bindings

C-base languages, variables (more formally known as *bindings*, as a name is bound to a value inside a scope) are created at the spot where the declaration occurs.

> The `let` and `const` block bindings introduce lexical scoping to JavaScript.

Use `const` to ensure certain level of immutability and use `let` if you need to change value.

## `var` and Hoisting

Variable declarations using `var` are treated as if they're at the top of the function (or in the global scope, if declared outside of function) regardless of where the actual declaration occurs; this is called hoisting.

The declaration is hoisted to the top, and the initialization remains in the same spot.

## Block-level Declarations

Block-level declarations declare bindings that are inaccessible outside a given block scope. Block scopes, also called lexical scopes, are created in the following places:

* Inside a function
* Inside a curly braces block

```js
if (condition) {
  const maxItems = 30; // Must also be initialized on declaration and can't be modified
  const obj = {}; // Can be modified later if it is an object
  let value = 'value';
} else {
  // value don't exist here
}
```

`const` prevent modification of the binding, not modification of the bound value. This is why you can modify a constant holding an object.

## Temporal Dead Zone

You cannot access variables before they're declared, even with safe operators, such as `typeof`. Attempting to access a block binding before its declaration results in an error due to the binding's presence in the TDZ.

```js
if (condition) {
  console.log(typeof value); // TDZ - will throws reference error
  let value = 'blue';
}
```