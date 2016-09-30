# Atomic and Functional

Single-purpose classes which do one thing extremely well.

* [Atomic and Functional CSS](https://blog.colepeters.com/building-and-shipping-functional-css/)
* [f(css)](http://www.jon.gold/2015/07/functional-css/)

Say you have a `.card` to represent question. This card has a nice box shadow that look like Material Paper. Further down the page, you want to use similar card look but with less padding, what will you do? One approach is to use BEM modifier:

```css
.card {}

.card--question {
  padding: 20px;
}

.card--site {
  padding: 10px;
}
```

But what happen if we want a card on a white background, thus we want to eliminate the padding to 0. Or even tone down the box shadow a bit for other scenario. Suddenly we need a lot more modifiers. Is this the fault of BEM?

Functional or atomic CSS can solve this utilities-like problem.

```html
<div class="u-relative u-mt1 u-p2 v-bg-white v-bs2">
  <!-- Card contents -->
</div>
```