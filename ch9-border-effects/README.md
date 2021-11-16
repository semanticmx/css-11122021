# Border and Box Effects

The CSS border properties allow you to specify the style, width, and color of an element's border.

## Rounded Corners

We can define rounded corners with the border-radius property. First, we call the border property. After that, we specify the border location, top-left, top-right, and so on, and then we add the value.

```
	E{
		border-top-left-radius: 20px;
 		border-top-right-radius: 20px;
		border-bottom-right-radius: 20px;
		border-bottom-left-radius: 20px;
	}
```

**border-radius Shorthand**

Also, we can do it in one line, just using the border-radius property. The first parameter is top-left, then top-right, bottom-right, and lastly, bottom-left.

```
	div{ 
		border-radius: 10px 20px 40px 80px;
	}
```

### Using Percentage Values

Also, we can use percentages to define the borders.

```
	.circulo{
		border-radius: 50%;
	}
```

## Images as Borders

To use an image as a border, first, we load the image with the border-image-sources property. This property puts the image in the four corners of the element.

```
	.image{
		border-image-source: url("landscape.png");
	}
```

### border-image-slice

After that we use the border-image-slice. The border-image-slice property specifies how to slice the image specified by border-image-source. The image is always sliced into nine sections: four corners, four edges and the middle.

```
	.slice{
		border-image-slice: 33%;
	}
```

The "middle" part is treated as fully transparent, unless the fill keyword is set.

```
	.slice{
		border-image-slice: 33% fill;
	}
```

The border-image-slice property accepts between one and four values, each of which maps to a side of an element. We can specify a number with no units, this allows to the browser use px in bitmap images or coordinates in vector images.


### border-image-repeat

This property allows us to adjust the image.

```
	.repeat{
		border-image-repeat: round;
	}
```

**Property Values**

- repeat 		--The background image is repeated both vertically and horizontally.  The last image will be clipped if it does not fit. This is default.
- no-repeat		--The background-image is not repeated. The image will only be shown once.
- space			--The background-image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images.
- round			--The background-image is repeated and squished or stretched to fill the space (no gaps).


### border-image-width 

The border-image-width property specifies the width (and height) of the border image.

```
	.width{
		border-image-width: 10px;
	}
```

*note: Applies the width to the image not to the border*


### border-image-outset
 
The border-image-outset property specifies the amount by which the border image area extends beyond the border box.

```
	.outset{
		background-color: black;
		border-image-outset: 20px;
	}
```

**The border-image Shorthand Property**

```
	E {
	 border-image-source: url('foo.png');
	 border-image-slice: 25 10 fill;
	 border-image-width: 25px 10px;
	 border-image-outset: 5px;
	 border-image-repeat: round;
	}

	F { border-image: url('foo.png') 25 10 fill / 25px 10px / 5px round; }
```

## Drop shadows

Like the text drop shadow, it uses the x- and y-axis in the first two values, the third one is the blur, and the fourth is the color.

Syntax:
```
	E { box-shadow: inset horizontal vertical blur-radius spread color; }
```

### indent

Also, we can use dropshadow inside the box using indet parameter, the values are first, right, next one top, blur and lastly the color. 

```
	.inset{
		box-shadow: inset 8px 0px 6px rgb(112, 112, 112);
	}
```

*note: if we use negative values we can change to the opposite side. for instance, right to left, and top to bottom.*