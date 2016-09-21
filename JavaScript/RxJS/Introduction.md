# RxJS Introduction

## Everything is a Stream

You reached Zen mode when you realized everything can be represented as a stream: mouse, keyboard events, arrays, variables, properties, caches, data structures. Practically, everything!

Since a stream is just a collection, it can be mapped over, filtered, merged, concatenated, debounced over, etc.

One element collection like XHR is still a stream. It just contain one element.

```js
const requestStream = Rx.Observable.just('api.jobline.com/users');

// Observable is Promise++
Rx.Observable.fromPromise(jQuery.getJSON(requestUrl));
```

Streams are **observables** because they are **observed**.


## Videos

* [RxJS: Destroy the state machine!](https://www.youtube.com/watch?v=1abiJ9VBsDc)