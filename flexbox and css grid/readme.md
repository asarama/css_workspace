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

## CSS Grid

Controls how items flow in two dimensions. Flex box lets content size itself, css grid relies on defined gridlines.

### Basics

Items are aligned in rows and columns making cells. Elements can exists in sets of cells.

Defines relationship between grid container and items. The grid is defined by two sets of lines called the grid lines. One set for columns (column axis) and another for rows (row axis). Grid tracks are the space between row column lines. Where row and column lines intersect is what we call cells. Adjacent cells can be combined into grid areas.

### Setting up a grid

Set the property ```display: grid``` on the container.

You can also use ```inline-grid``` if needed.

Define columns ```grid-template-columns: 1fr 1fr 1fr```
Define rows ```grid-template-rows: 1fr 1fr```

Positioning elements is done via the properties:
 - ```grid-column-start```
 - ```grid-column-end```
 - ```grid-row-start```
 - ```grid-row-end```

### Auto grid features

```grid-auto-flow``` : Controls how items fill in the grid
 - row (default)
 - column

```order``` : Controls when items are placed

### Grid Shorthand

```grid: 1fr 1fr 1fr / 1fr 1fr``` : Sets template columns first then rows \
```grid: repeat(3, 1fr) / repeat(2, 1fr)``` : Equivalent to example above \
```grid-column: 2 / 4``` : Sets item to start at column 2 and end at 4 \
```grid-column: 2 / span 2``` : Sets item to start at column 2 and end 2 after the start column \
```grid-row: 2 / 4``` : Sets item to start at row 2 and end at 4 \
```grid-area: row-start / column-start / row-end / column-end``` : Can accept all 4 values from grid-column and grid-row 

### Named Grid Properties

With CSS grid you can name columns and rows to reference them easier without the need of counting lines.

On the container: \
```grid: [sidebar] 1fr [main_content_one] 1fr [main_content_two] 1fr / [row_one] 1fr [row_two] 1fr``` \
On the item: \
```grid-area: row_one / sidebar / row_two / main_content_one```

A better approach is to set the grid normally, add grid-area properties to our items as names, and then use the grid-template-areas property on the container.

1) ```grid: 1fr 1fr 1fr / 1fr 1fr```
2) ```grid-area: some_item```
3) ```grid-template-areas: "some_item . ."```\
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```"some_item . ."```

Now our element with the ```grid-area``` property will be placed in the first column and span both rows. "." is used to signify an empty area.

### Unique Aspects of Grid

Using ```auto``` in our grid template declaration will allow the element to grow and shrink as it's content does.

The ```fr``` unit is used to size grid tracks based on how much space is available in the container. If we set our column definition to ```1fr 1fr``` then both our columns will be of even width. If we set it to ```2fr 1fr``` our first column will take up twice as much space as our second.

You can overlap grid items, but keep in mind items will stack from the first element in the markup to the last. This can be remedied with the z-index property.

### Grid Layout with Box Alignment

The grid container supports properties:
- justify-content: Horizontal control
- justify-items
- align-content: Vertical control 
- align-items

The grid items support properties:
- justify-self
- align-self

