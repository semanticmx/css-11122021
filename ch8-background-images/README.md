# Background Images

The background-image property sets one or more background images for an element.

## Upload an image

To upload a background image we can do it from css, just selecting the element where it'll go.

```
	 body {
	 background-image: url("paper.gif");
	}
```
## background-size

Change the size of the background image.

```
	.grupo{
		background-image: url("images/download.png");
		background-size: 50%;
	}
```

**Property Values**
- cover 		--Resize the background image to cover the entire container, even if it has to stretch the image or cut a little bit off one of the edges.
- contain 		--Resize the background image to make sure the image is fully visible
- percentage 	--Sets the width and height of the background image in percent of the parent element. Example: 10px 10px.
- auto 			--Default value. The background image is displayed in its original size

## background-repeat

By default, the background image repeats itself to fill the blank space. To avoid this, we can change the default value to no-repeat.

```
	.no-repeat{
		background-repeat: no-repeat;
	}
```
**Property Values**

- repeat 		--The background image is repeated both vertically and horizontally
- no-repeat 	--The background-image is not repeated
- space 		--The background-image is repeated as much as possible without clipping
- round 		--The background-image is repeated and squished or stretched to fill the space (no gaps)
- repeat-x or y --The background image is repeated on the x- axis or y- axis.

## background-position

Can move the image anywhere within the div element.

```
	.position{
		background-position: top right;
	}
```

**Property Values**

- top		--move to top
- bottom	-- move to bottom
- left 		--move to left
- right 	-- move to right
- center 	-- move to center

Also, we can be even more specific setting length measures.

```
	.position{
		background-position: top 20px right 20px;
	}
```

## Multiple background

Loads multiple images.

```
	E { background-image: value, value; }
```

## background-attachment

The background-attachment property sets whether a background image scrolls with the rest of the page, or is fixed.

```
	.attachment{
		background-attachment: fixed;
	}
```

## Background Clip

Sets the background in relation to the container.

```
	.clip{
		background-clip: content-box;
	}
```

**Property Values**

border-box 		--Default value. The background extends behind the border.
padding-box		--The background extends to the inside edge of the border.
content-box		--The background extends to the edge of the content box.


## Background Origin

The background-origin property specifies the origin position (the background positioning area) of a background image.

```
	.origin{
		background-origin: border-box;
	}
```

**Property Values**

border-box 		--The background image starts from the upper left corner of the border.
padding-box		--Default value. The background image starts from the upper left corner of the padding edge.
content-box		--The background image starts from the upper left corner of the content.