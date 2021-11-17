# Flexible Box Layout

The flexbox was created to create columns and rows. Unlike float, which was only created to wrap text around images, flexbox allows us to manage columns and rows without using a lot of hacks to manage them, as does float.

On the other hand, to avoid using a lot of hacks to make a layout in our webpage, we use _grid_ to make it easier. In the ch. 17 we are going to review _grid_.

## Declaring the flexible box model

The first step in using Flexbox is to create the flex container. The flex container is specify in the parent element that will create a new formatting context for its contents.

```
	E { display: flex; }
```

For example, in the following code,if #container is set as the flex container, the two children items will become flex items:

```
	<div id="container">
	 <div id="a">...</div>
	 <div id="b">...</div>
	</div>
```

**Display Values**

- block --for sections in a webpage
- inline --for text
- Table --for two-dimensional table data
- Positioned --for explicit position of an element

## flex-direction

Flex-direction is used to alter the layout direction.

```
	E {
	 display: flex;
	 flex-direction: column;
	}
```

### Alignment

Flexbox uses two axes for alignment. The main axis goes in the direction that items are placed, from left to right or top to bottom. When the value of flex-direction is row, the main axis is horizontal; when it is a column, the main axis is vertical.

### Reversing the Content Order

To reverse the content order we just need to use the flex-direction property with the value row-reverse.

```
	E { flex-direction: row-reverse; }
```

### Reordering Content

To re-order the content, we can use the "order" property, and we specify the value from 0, that is the first element, to the last element number.

```
	#a {
	  order: 1;
	}
	#b {
	  order: 0;
	}
	#c {
	  order: 2;
	}
```

_Note: Also we can use pseudo classes as :nth-child()._

## Adding flexibility

We can use different properties to allow flex items to grow or shrink to fill their container.

### flex-grow Property

Flex-grow lets us expand the items inside the flex parent to fill the container.

```
	.flex-item { flex-grow: 1; }
```

The values are ratios, an 1 ratio will divide the empty space into equal parts between the elements. But, also we can use other ratios to adjust the distribution.

### flex-shrink

Just as flex-grow is used to expand flex items to fill their container, flex-shrink is used to shrink items.

```
	.flex-item { flex-shrink: 1; }
```

_Note: Higher numbers reduce the elements by a greater factor._

### flex-basis

The flex-basis property specifies the initial length of a flexible item.

The width of flex items can be set either by the content they contain or by an explicit width value, and any growth or shrinkage is calculated from that base width. To change how the width adjustment is calculated, we can set a flex-basis value on an element.

```
	.flex-item { flex-basis: 100px; }
```

_note: If the element is not a flexible item, the flex-basis property has no effect._

### Flex Shorthand

The order is: flex-grow, flex-shrink, and flex-basis.

```
	E { flex: 1 2 150px; }
```

## Alignment inside the container

### Horizontal Alignment with justify-content

_justify-content_ allows us to horizontally align content inside the flexbox.

```
	.flex-container { justify-content: keyword; }
```

**Property Values**

- flex-start --Default value. Items are positioned at the beginning of the container
- flex-end --Items are positioned at the end of the container.
- centering --Items are positioned in the center of the container.
- space-between --Items will have space between them.
- space-around --Items will have space before, between, and after them.
- space-evenly --Items will have equal space around them.

### Vertical Alignment with align-items

_align-item_ property allows us to vertically align content inside the flexbox.

```
	.flex-container { align-items: keyword; }
```

**Property Values**

- stretch --Default. Items are stretched to fit the container.
- center --Items are positioned at the center of the container.
- flex-start --Items are positioned at the beginning of the container.
- flex-end --Items are positioned at the end of the container.
- baseline --Items are positioned at the baseline of the container.

## Wrap and Flow

Wrap allows us to break the items into multiple lines.

```
	.flex-container { flex-wrap: wrap; }
```

The value wrap-reverse changes the direction of the cross-axis so new lines appear above (or to the left).

**Property Values**

- nowrap --Default value. Specifies that the flexible items will not wrap
- wrap --Specifies that the flexible items will wrap if necessary
- wrap-reverse --Specifies that the flexible items will wrap, if necessary, in reverse order

### flex-flow Shorthand

```
	E { flex-flow: column wrap-reverse; }
```

## align-content

The align-content property modifies the behavior of the flex-wrap property. It is similar to align-items, but instead of aligning flex items, it aligns flex lines.

```
	E{align-content: keyword;}
```

This property works like justify-content but, the justify property works on the horizontal axis, and align-content works on the cross axis. It has the same possibilities and adds stretch, which resizes the items to fill all unused space

_Note: There must be multiple lines of items for this property to have any effect_
