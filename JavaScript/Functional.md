# Functional

BAD:

* Assignment
* Loops
* Callbacks
* Side Effects - Network
* Branching
* Errors - try/catch

```js
// Using assignment to hold temporary states
const contrivedExample = str => {
  const trimmed = str.trim()
  const number = parseInt(trimmed)
  const nextNumber = number + 1
  return String.fromCharCode(nextNumber)
}

// Using closure to hold states
const contrivedExample = str =>
  [str.trim()]
  .map(trimmed => parseInt(trimmed))
  .map(number => number + 1)
  .map(nextNumber => String.fromCharCode(nextNumber))
```