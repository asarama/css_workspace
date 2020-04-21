# Flexbox and CSS Grid

Originally started as tables with extra hacks. Then eventually as more display types arose float based layouts became popular, but they too required lots of hacks. Eventually there were too many devices to support and a more flexible :wink: solution was required.

Thus Flexbox and CSS Grid were developed.

## Flexbox

Arrange items in any 1D direction. Enables wrapping and stretching functionality.

### Basics

Manages relationship between flex container and items.

Main axis: Direction of flex \
Main start: Start point \
Main end: End point \
Main size: Distance between main start and end \
Cross axis: Perpindicular to main axis.
* The cross axis has the same properties and main

The flex display element creates our flex container. It itself acts like a normal block element, but all it's children will be inline by default.
```CSS
display: flex 
```

* Inline flex is also available if you are looking for inline behavior for the flex container.

### Flow direction

By default items flow from left to right as defined by the default flex-direction property.

Possible values:
 - row (default)
 - row-reverse
 - column
 - column-reverse