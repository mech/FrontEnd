# Source Code

Here are some interesting listing of code. Nothing make sense, btw.

```js
// I like how it is return simple data structure
if (!filter) {
  return [val, [...errs, `Unknown filter: ${name}`]];
}

// I like the errs instead of errors
class Writer {
  constructor(value = null, errs = []) {
    this.value = value;
    this.errs = errs
  }
}

// I like the custom fail()
if (typeof str !== 'string') {
  return fail(str, `Invalid argument to toUpper: ${typeof str}`);
}
```