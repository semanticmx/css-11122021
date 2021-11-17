# Gradients

CSS gradients let you display smooth transitions between two or more specified colors.

## linear

A linear gradient gradually transitions between colors over the length of a straight line connecting two points.

```
	E { background-image: linear-gradient(black, white); }
```

### setting gradient direction

To set a different gradient line, specify a target side or corner of the box. If we add "to top" it'll go from bottom to top. Also, we can specify from to point to make it diagonal.

```
	E { background-image: linear-gradient(to right bottom, black, white); }
```

### adding extra color-stop values

We can add extra color. In this example, we added another black value, so the gradient starts with black, goes to white, and then again to black.

```
	E { background-image: linear-gradient(black, white, black); }
```

**Setting a percentage**

We can also set percentages or px to the gradient. In this way, we can move the gradient.

```
	E { background-image: linear-gradient(black, white 75%, black); }
```

## Repeating Linear Gradients

We can repeat the same gradient until the element is filled using the repeating-linear-gradient() function.

```
	E { background-image: repeating-linear-gradient(white, black 25%); }
```

## Radial Gradients

A radial gradient is a gradual transition between colors that moves out from a central point in all directions.

```
	E { background-image: radial-gradient(white, black); }
```

### Shapes

We can set the shape of a radial gradient by adding a keyword before the color-stops.

```
	E { background-image: radial-gradient(circle, white, black); }
```

**Values**

- ellipse (default)
- circle

### Positioning

The default center of a radial gradient (from which the gradient radiates) is at the center of the element it’s applied to. We can change this point by adding a position argument to the radial-gradient() function.

```
	E { background-image: radial-gradient(circle at 100% 50%, white, black); }
```

### Size

We can also set the extent of a gradient—that is, the point where the gradient ends—using a length or position value or one of four extant keywords.

```
	E { background-image: radial-gradient(circle 50px, black, white); }
```

**Values**

- farthest-corner (default).
- closest-side.
- closest-corner.
- farthest-side.
- measurement units "px".

### Multiple color-stop

As the linear gradient we just have tu add an extra value "color" to have multiple colors.

```
 E {
	background-image: radial-gradient(circle 80px, white, black,
	white, black);
}
```

### Repeating Radial Gradients

Just as the linear-gradient() function has repeating-linear-gradient(). Can be used to repeat the supplied arguments until the limits are reached.

```
	 E{
	 	background-image: repeating-radial-gradient(circle farthest-corner at right top,black, white 10%, black 15%);
	 }
```

## Multiple Gradients

Because gradients are applied with the background-image property, you can use CSS3’s multiple background values’ syntax to apply multiple gradients to an element using comma-separated values.

```
	.mltradial{
		background-image:
	  	radial-gradient(42px circle at 20% 50%, white, black 95%, transparent),
	 	radial-gradient(42px circle at 50% 50%, white, black 95%, transparent),
	 	radial-gradient(42px circle at 80% 50%, white, black 95%, transparent),
	 	linear-gradient(to right bottom, darkred, white 80%);
	}
```
