# CSS Architecture

* [CSS Guidelines by Harry Roberts - A high-level advice and guidelines for writing sane, manageable, scalable CSS](http://cssguidelin.es/)
* [Probably too extreme approach to styling?](https://medium.com/maintainable-react-apps/journey-to-enjoyable-maintainable-styling-with-react-itcss-and-css-in-js-632cfa9c70d6#.fvzqui8rt)
* [CSS at BBC Sport - Using BEM, OOCSS and ITCSS](https://medium.com/@shaunbent/css-at-bbc-sport-part-1-bab546184e66#.5x90b9sh8)
* [CSS Architecture by Philip Walton](https://philipwalton.com/articles/css-architecture/)

You need to know how Specificity, Inheritance and Cascade work in CSS.

```css
/* Cascade is good for fallback */
background: rgb(255, 128, 0);
background: linear-gradient(90deg, yellow, red);

/* Specificity should be easy to grasp. Just use classes and no ID */
.safe {}
#not-safe {}
```

## Contextual Styling

* [Harry's post on contextual styling](http://csswizardry.com/2015/06/contextual-styling-ui-components-nesting-and-implementation-detail/)

> If you need to change the cosmetics of a UI component based on where it is placed, your design system is failing.

Things should be designed so that we always just have "this component" and not "this component when inside...".

We need to choose to ignore context:

```css
/* Incorrect: we have a button that needs to be full width when in a modal overlay */
.modal .btn { width: 100%'; }

/* Correct: we have a variant of a button that is full width that we are able to use wherever we like */
.btn--full { width: 100%'; }
```

When designing a composable UI, we have to be wilfully ignorant. Cosmetics should not change depending on the location of the component. As far as cosmetic changes are concerned, there is no such thing as context.

## Principles

> At the heart of CSS architecture is **DRY** and maintainability. To achieve that require that we write **Flexible CSS**, make it easier to write once and then create variations with very little code afterward, as there are only a few values you need to override.

### DRY & Single Source of Truth

DRY increases code confidence, it makes maintenance easier. We can use variables and mixins for our single source of truth in CSS.

However, do not DRY things that are purely coincidental. The same `12px` does not mean it should all be abstracted away and store in one single variable. That is the wrong kind of abstraction.

```css
--unit: 12px; /* Single source of truth */

.u-margin-top { margin-top: var(--unit); }
```

### Single Responsibility Principles

Provide developers with the ingredients (food), the modules to compose stuffs.

CSS responsibilities can be split into:

1. Base - display
2. Structural - margin, padding
3. Cosmetic - color, background-color

```css
/* Too many responsibilities */
.btn-login {
  display: inline-block;
  padding: 2em;
  background-color: green;
  color: white;
}

/* Separate responsibilities */
.btn {
  display: inline-block;
}

.btn--large {
  padding: 2em;
}

.btn--positive {
  background-color: green;
  color: white;
}
```

### Separation of Concerns

Each thing is responsible for itself and nothing more. Reason about and study features in complete isolation.

```css
/* Anti-pattern: Not SOC, as we cannot reason this in isolation */
header nav ul li a {}
[role="navigation"] {}
[role="navigation"] > ul > li {}
```

### Immutability

* [Immutable CSS](http://csswizardry.com/2015/03/immutable-css/)

Minimizing side effects. Provides confidence. Make things predictable.

```css
/* Anti-pattern: Mutation! Increases cognitive overhead */
.col-6 {
  width: 50%;
}

@media screen and (max-width: 480px) {
  .col-6 {
    float: none;
    width: 100%;
  }
}

/* Better? */
@media screen and (max-width: 480px) {
  .col-6@sm {
    float: none;
    width: 100%;
  }
}
```

```css
/* For utility classes, it is okay to use !important */
.u-text-center {
  text-align: center !important;
}
```

### Mobile-First

> Rulesets should only ever inherit and add to previous ones, never undo. - Harry Roberts

```css
@media only screen and (min-width: 64em) {
  /* For larger screen only */
}
```

## Videos

* [CSS for Software Engineers for CSS Developers - Harry Roberts](https://www.youtube.com/watch?v=wFn5nel3j6w)
* [dotCSS 2014 - Nicolas Gallagher - Thinking Beyond Scalable CSS](https://www.youtube.com/watch?v=L8w3v9m6G04)