# PostCSS

* [browserslist](http://browserl.ist/)

SASS in 2006, followed by Less in 2009. Provides variables, mixins, functions, and more.

Essential plugins:

* **postcss-cssnext** - will include postcss-apply, postcss-nesting, postcss-media-minmax, etc.
* **postcss-nested** - may be worth to use since postcss-nesting will add empty rule for now.

## Against

* [CSS solution for create-react-app](https://github.com/facebookincubator/create-react-app/issues/130#issuecomment-246801178)

## Custom Properties & `var()`

* [Why I am excited about native CSS variables](https://philipwalton.com/articles/why-im-excited-about-native-css-variables/)
* [Let's talk about CSS Variables](http://www.xanthir.com/blog/b4KT0)

Custom properties is not Sass variables. They are more dynamic and scoped to the DOM.

Immutable.

```css
:root { --gutter: 1.5em; }

@media (min-width: 30em) {
  :root { --gutter: 2em; }
}

@media (min-width: 48em) {
  :root { --gutter: 3em; }
}

.Container {
  margin: 0 auto;
  max-width: 60em;
  padding: var(--gutter);
}

.Grid {
  --gutterNegative: calc(-1 * var(--gutter));
  display: flex;
  margin-left: var(--gutterNegative);
  margin-top: var(--gutterNegative);
}

.Grid-cell {
  flex: 1;
  margin-left: var(--gutter);
  margin-top: var(--gutter);
}
```

## Nesting (Avoid if possible)

Don't nest all the stuffs, it will lead to trouble understanding. Matter of fact, try not to use nesting at first.

```css
/* BAD nesting */
.phone {
  &_title {
    width: 500px;
    @media (max-width: 500px) {
      width: auto;
    }
    body.is_dark & {
      color: white;
    }
  }
}
```

## Media Queries

* [CSS MQPacker](https://github.com/hail2u/node-css-mqpacker)
* [postcss-media-minmax](https://github.com/postcss/postcss-media-minmax)

```css
@custom-media --foo (width >= 20em) and (width <= 50em);

@media (--foo) {
}
```