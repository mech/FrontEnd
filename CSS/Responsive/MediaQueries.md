# Media Queries

Minimize media queries breakpoints. If you find yourself needing a boatload of media queries to make your design adapt to smaller/larger screens, take a step back and reexamine your code structure.

* [Basecamp - Experimenting with responsive design in Iterations](https://signalvnoise.com/posts/2661-experimenting-with-responsive-design-in-iterations)
* [7 habits of highly effective media queries](http://bradfrost.com/blog/post/7-habits-of-highly-effective-media-queries/)
* [The 100% correct way to do CSS breakpoints](https://medium.freecodecamp.com/the-100-correct-way-to-do-css-breakpoints-88d6a5ba1862#.l9ygnjpvj)

Don't let media queries method throws off your content hierarchy.

```css
.container {
  width: 100%;
  @media (min-width: $M) {
    width: 50%;
  }
  @media (min-width: $L) {
    width: 75%;
  }
}
```

## REM and Media Queries

* [REM unit is unless in Media Queries](http://fvsch.com/code/bugs/rem-mediaquery/)