# Flexbox

Don't always think you need to use media queries. Most of the time a default flexbox can make the site very responsive already.

> Flexbox let the DOM know that elements on the page have a relationship (or relationships)

**Don't force flexbox to be a grid system, it was not designed for that!**

## Browser Support

IE 9 and Opera 12 don't support flexbox. IE 10 has tweener flexbox.

In IE 10-11, flex items ignore their parent container's height if it's set via the `min-height` property.

## Flex Container

A flex container expands items to fill available space, or shrinks them to prevent overflow.

Flexbox is all about alignment and ordering. It is a smart layout mode that calculates and distributes space.

The prime characteristic of the **flex container** is the ability to modify the width or height of its children to fill the available space in the best possible way on different screen sizes.

Flexbox layout algorithm is direction-based unlike the block or inline layout which are vertically and horizontally based.

* Flex container - Parent
* Flex items - Children
* Main axis is horizontal and controlled by `justify-content`.
* Cross axis is vertical and controlled by `align-items`
* Main dimension
* Main size

**Note**: Only direct children of a flex container become flex items, not its descendants.

Flexbox will override floats, table-cell and inline-block. It will not override absolute positioning.

### Body as flex container

Be careful when you mark `body` as `display: flex`, it will screw up all your block-level elements and make them unable to become 100% full-width since you are essentially marking all immediately children as flex items.

## Flex Items

## Hacks

* [Flex-grow 9999 Hack](http://joren.co/flex-grow-9999-hack/)