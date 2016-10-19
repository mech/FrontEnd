# HTML5

* [WICG](https://github.com/WICG)

## Anchor

* [Nested links using `<object>`](http://kizu.ru/en/fun/nested-links/)

```html
<a href="">
  Content of the main link...
  <object type="lol/wut">
    <!--[if gte IE 9]><!--><a href=""><!--<![endif]-->
      Content of nested link...
    <!--[if gte IE 9]><!--></​a><!--<![endif]-->
  </object>
</a>
```