# Animation for the Web

> When everything vies for our attention, nothing commands our attention - [The Web in Motion](https://www.youtube.com/watch?v=jX_TWlDe-Is)

* [A comparison of various techniques to do animation on the Web](https://sparkbox.github.io/bouncy-ball/)
* [Animating in React](http://slides.com/sdrasner/react-rally#/)

Animation is:

* Context Shifting
* Isolation
* Revealing

**Tools**

* Use plain CSS for simple sequences and simple interactions.
* **GSAP (GreenSock)** for complex movement and great cross-browser consistency.
* React-Motion
* Snap.svg
* Web Animation API - waiting for support
* Velocity - similar to GSAP with less bells and whistles
* Mo.js
* D3.js
* Victory.js

```css
@mixin accelerate($name) {
  will-change: $name;
  transform: translateZ(0);
  backface-visibility: hidden;
  perspective: 1000px;
}

.foo {
  @include accelerate(transform);
}
```

## Videos

* [All The Right Moves by Val Head](https://vimeo.com/channels/alltherightmoves/)