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
Cross axis: Perpendicular to main axis.
* The cross axis has the same properties and main

The flex display element creates our flex container. It itself acts like a normal block element, but all it's children will be inline by default.
```CSS
display: flex 
```

* Inline flex is also available if you are looking for inline behavior for the flex container.

### Flow direction

By default items flow from left to right as defined by the default `flex-direction` property.

Possible values:
 - row (default)
 - row-reverse
 - column
 - column-reverse

### Line Wrapping

```flex-wrap``` 

Possible values:
- nowrap (default)
- wrap
- wrap-reverse

```flex-flow```

Used to dictate flex-wrap and flex-direction. First value is direction and second is wrap.

### Display Order

Using ordinal groups items in a flex box can be repositioned. All items in the flex box are given an ordinal group of 0 by default. Setting the property order to a value greater than 0 will move the item to be rendered after the 0th ordinal group and vice versa.

### Flexibility

Used to change the size of the flex items depending on screen size.

```flex-grow```\
```flex-shrink```\
Controls how space is distributed as more or less space is available.

```flex-basis```\
Initial size of item before growing or shrinking.

Shorthand:\
```flex: flex-grow flex-shrink flex-basis```

### Alignment

Uses the box alignment module.

For the flex container
Properties:\
```justify-content``` : Used to align flex container items along the main axis\
```align-items``` : Used to align flex container items along the cross axis\
```align-content``` : Used to control white space within a flex container with multiple lines

For the flex items\
```align-self``` : Used to control alignment module properties on a flex item directly