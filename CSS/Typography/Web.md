# Web Typography

* [Font Face Observer](https://fontfaceobserver.com/)

```js
document.fonts.ready.then(() => {
  let body = document.body;
  body.classList.toggle('fontzL0ad3d');
});

body {
  font-family: 'Helvetica', 'sans-serif';
}

body {
  font-family: 'T0t411y-R4D-Sans';
}
```

## Typography Scale

* [Type Scale](http://type-scale.com/)

Smaller screen often need smaller font-size, like iPhone display or the small MacBook display. Larger 27" display naturally need bigger font-size. In order for your font to be responsive, you need a system of typography scale.

Instead of defining our typography with an absolute unit like the pixel, we can better design our typography as a scale, as a ratio.

## REM

REM is designed not to be flexible. It is tied to the root (html) element. People sometime just want to be lazy and use the [62.5% hack](https://vasilis.nl/nerd/weird-62-5-antipattern/) to make everything 10px-based. They then use REM unit to prevent the ensuing inheritance mess.

```css
p, li, td, input {
  font-size: 1.6em;
}

li p, li label {
  font-size: 1em; /* Reset it or else will be 1.6em * 1.6em */
}
```

* [The REM fallback with Sass](https://drublic.de/archive/rem-fallback-sass-less/)
* [REMs And Viewport Measurements — Why You Shouldn't Use Them Yet](http://vanseodesign.com/css/rems-and-viewport-measurements/)
* [Why I dislike REM unit](https://vasilis.nl/nerd/dislike-rem-unit/)
* [Use EM and REM for the right use cases](https://vasilis.nl/nerd/use-em-rem-right-use-cases/)

## Videos

* [Syntax Highlight Everything](https://www.youtube.com/watch?v=s_ooNo2EmMI)