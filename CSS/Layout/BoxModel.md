# Box Model

## Block Formatting Context

## Margin Collapsing

* [Collapsing Margins](https://www.sitepoint.com/web-foundations/collapsing-margins/)
* [W3C spec](https://drafts.csswg.org/css-box-3/#collapsing-margins)

Top an bottom margins combined into a single margin of the largest margins. It occurs in 3 cases:

* Adjacent siblings (except when later sibling needs to be cleared past floats) - Take 2 `<p>` as an example.
* Parent and child
* Empty block - If there is no border, padding, content, height to separate block, then it will collapse.

Margins of floating and absolutely positioned elements NEVER collapse.

> There is only margin-top OR only margin-bottom. Choose one and stick to it!

By only ever using `margin-bottom`, every element is in charge of how much space there should be below it.

## Stacking Context

* [You know a site has its shit together when the highest z-index is 4](https://hackernoon.com/you-know-a-site-has-its-shit-together-when-8ee21040d0bc#.fawru3g9m)

To put element in a new stacking context, use:

```css
.block {
  position: relative;
  z-index: 1;
  
  .jquery-modal {
    z-index: 9999; /* essentially 1.999 in the new context */
  }
}
```