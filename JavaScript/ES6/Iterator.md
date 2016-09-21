# Iterator

```js
Array.prototype[Symbol.iterator] = function* () {
  for (let i = 0; i < this.length; i++) {
    yield this[i];
  }
}

// Using for-of
for (const elem of ['a', 'b', 'c']) {
  console.log(elem);
}
```

```js
class TupleArray extends Array {
  *[Symbol.iterator]() {
    for (let i = 0; i < this.length; i++) {
      yield [i, this[i]];
    }
  }
}

// Will return tuples
// [0, 'a']
// [1, 'b']
// [2, 'c']
```

```js
Number.prototype[Symbol.iterator] = function* () {
  let i = 0;
  while (i < this) { // Notice the this here
    yield i++;
  }
}

// Using spread operator directly on a number primitive
console.log(...5);
```

Iterables implement `[Symbol.iterator]()`

Iterators implement `next()` and `throw()`

## Videos

* [Untangle your code with yield](https://www.youtube.com/watch?v=B15sTBSAotk)