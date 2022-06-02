# Values and Sizing


## Relative length units

This units are relative to another property.


### Font relative units

#### em
em is relative to the font-size of the current element  (2em means 2 times the size of the current font).

#### ex
ex is relative to the x-height of the current font (rarely used).

#### ch
ch is relative to the width of the "0" (zero).

#### rem
rem is relative to font-size of the root element (html element).


#### em vs rem

em have troubles when we're nesting elements, the size of the font if they're nested will be multiply.

### Viewport-Relative Units

#### Percentages

Percentages are used to give values to layouts elements for a responsive develop. But as em, percentages cross with problems. 

We can set 75% of the viewport width to an element. But if we want to set 65% of the viewport width (not the width of its parent) to a child element we have to do some maths. We have to divide 65 by 75 giving us a result of 86.666%. But if we go into a deper nesting the calculations are going to be more complex.

```
	.parent{
		width: 75%;
	}

	.child{
		width: 86.6%;
	}
```

#### vh and vw

represent viewport height and width. Each unit of value represents 1 percent of the appropriate viewport dimension: 1vh is 1 percent of the viewport height, and 1vw is 1 percent of the viewport width.

following the previous example instead of dividing we just set the number:

```
	.parent2{
		width: 75vw;
	}

	.child2{
		width: 65vw;
	}
```

**Property Values**

- vmin 		--Relative to 1% of viewport's* smaller dimension.
- vmax		--Relative to 1% of viewport's* larger dimension.

For instance, if the viewport were 480×640, the height would be greater, so vmax would be equivalent to vh, and vmin would be equal to vw. 

## Sizing Elements

### Box Sizing

The box-sizing property defines how the width and height of an element are calculated: should they include padding and borders, or not.

**Property Values**

- content-box 		--Default. The width and height properties (and min/max properties) includes only the content. Border and padding are not included.
- border-box		--The width and height properties (and min/max properties) includes content, padding and border.

### max-content and min-content

max-content and min-content, are intrinsic values that make an element as wide or as high as the largest (max-content) or smallest (min-content) item of content it contains.

```
	E{width: min-content;}
```

### fit-content

Allows an element to expand to be just wide enough to contain its content, unless the maximum width of the element is reached, in which case, the content will wrap.

```
	E{width: fit-content;}
```