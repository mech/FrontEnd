# PostCSS

* [browserslist](http://browserl.ist/)
* [Smarter CSS builds with Webpack](https://www.bensmithett.com/smarter-css-builds-with-webpack/)

SASS in 2006, followed by Less in 2009. Provides variables, mixins, functions, and more.

Essential plugins:

* **postcss-cssnext** - will include postcss-apply, postcss-nesting, postcss-media-minmax, etc.
* **postcss-nested** - may be worth to use since postcss-nesting will add empty rule for now.
* [Rucksack](https://simplaio.github.io/rucksack/)
* [postcss-opacity](https://github.com/iamvdo/postcss-opacity)
* [postcss-css-variables](https://github.com/MadLittleMods/postcss-css-variables)
* [postcss-custom-properties](https://github.com/postcss/postcss-custom-properties)
* [postcss-simple-vars](https://github.com/postcss/postcss-simple-vars)
* [postcss-at-rules-variables](https://github.com/GitScrum/postcss-at-rules-variables)

## Against

* [CSS solution for create-react-app](https://github.com/facebookincubator/create-react-app/issues/130#issuecomment-246801178)

## Custom Properties & `var()`

`postcss-custom-properties` can only be used in the `:root` selector, while `postcss-css-variables` can be anywhere.

* [Why I am excited about native CSS variables](https://philipwalton.com/articles/why-im-excited-about-native-css-variables/)
* [Let's talk about CSS Variables](http://www.xanthir.com/blog/b4KT0)
* [Issue#99 - How postcss-css-variables is different from postcss-custom-properties](https://github.com/MoOx/postcss-cssnext/issues/99)

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

## Nesting (Avoid if possible, only use it for grouping)

Nesting can reduce and DRY up code (as we don't write repeated references to the same selector), but too much of it is never a good thing. Don't nest all the stuffs, it will lead to trouble understanding. Matter of fact, try not to use nesting at first.

You may want to consider only nesting pseudo-classes and pseudo-elements.

Typically, nesting happen when you try to mimic your HTML structure in your CSS. This will lead to non-reusable code due to extreme specificity of selectors.

Never nest rules purely for code organization. Only nest when the outputted CSS is what you want.

```css
/* It is too easy to style an element such as this: */
.module > h2 {
}
```

If the markup is as follow:

```html
<div class="module">
  <h2 class="unique"></h2>
</div>
```

then it will be difficult to override `h2` next time:

```css
.module > h2 {
  /* normal styles */
}

.unique {
  /* this will lose the specificity war */
}

.module .unique {
  /* win the war again, but specificity creep in! */
}
```

```css
/* BAD nesting - result in high specificity */
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

## Mixins

Never use a mixin if you're not passing an argument.

## Color functions

* [Lightness is Sass's darken](https://github.com/postcss/postcss-color-function/issues/30)

## Media Queries

* [CSS MQPacker](https://github.com/hail2u/node-css-mqpacker)
* [postcss-media-minmax](https://github.com/postcss/postcss-media-minmax)

```css
@custom-media --foo (width >= 20em) and (width <= 50em);

@media (--foo) {
}
```

Page 104