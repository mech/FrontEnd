# Pseudo Class

## :not()

* [MDN - :not()](https://developer.mozilla.org/en/docs/Web/CSS/:not)

```css
/* A reminder that the content of your :not() selectors contributes toward their specificity */

/* Defined first, but contains a class */
.foo:not(.bar) {
  color: red;
}

/* Defined last, but gets trumped by the previous class */
.foo:not(div) {
  color: green;
}
```

## :any-link

Match `:link` and `:visited`

```css
nav:any-link {
  color: var(--mainColor);
}

/* Will become */
nav:link,
nav:visited {
  color: #aaa;
}
```

## :enter

```css
nav :enter > span {
  background-color: yellow;
}
```
