# Media Queries

Media queries allow content rendering to adapt to different conditions, such as screen resolution.

## Syntax

There're three ways to apply media queries in a document:

**calling an external style sheet using the link element**

```
	<link href="file" rel="stylesheet" media="logic media and (expression)">
```

**calling an external style sheet using the @import directive**

```
	@import url('file') logic media and (expression);
```

**Calling media queries in a style sheet with the @media rule**

```
	@media logic media and (expression){rules}
```

### HTML Link Media Attribute

The media attribute tells the browser the kind of media the CSS style is for. To use it, first, in the link tag, we must declare the media type that the styles are applied:

```
	<link rel="stylesheet" type="text/css" href="style.css" media="screen">
```

Once we specify the media type in the html document we can create our own media querie in the css style sheet. To do this we can use any method from the above, I'm going to use the last one, so we just write `@media logic media (expression){rules}`

The logic medias are:

|	Value	|						Description						|
| all 		| Default. Used for all media types.					|
| print 	| Used for print preview mode/printed pages 			|
| screen 	| Used for computer screens, mobiles, etc. 				|
| speech 	| Used for screenreaders that "reads" the page out loud.|

_Note: If we omit the media type, it defaults to all_

```
	@media all (expression){ rules }

	@media (expression){rules}
```

### Keywords

#### Only

The only keyword prevents older browsers that do not support media queries with media features from applying the specified styles.

```
	@media only mediatype (expression){rules}
```

#### Not

The not keyword inverts the meaning of an entire media query. We use _not_ to apply the styles if the parameters we set are not met.

```
	@media not mediatype (expression){rules}
```

#### and

The and keyword combines a media feature with a media type or other media features.

```
	@media screen and (width: 600px) {
		body {
			color: red;
		}
	}
```

We also can use _and_ to combine media features.

```
	@media (min-width: 600px) and (max-width: 800px) {
		html { background: red; }
	}
```

#### Or

The or keyword sets a rule if any of the specified expressions are met.

```
	@media screen and (min-width: 600px), screen and (orientation: landscape) {
		body {
			color: blue;
		}
	}
```

The text will be blue if the viewport is at least 600 pixels wide OR the device is in landscape orientation.

## Media Features

Media features are information about the device that’s being used to display the web page: its dimensions, resolution, and so on.

In media queries, most media feature expressions require that a value be supplied:

```
	@media (feature: value){ rules }
```

### Width and Height

The width media feature describes the width of the browser. The basic syntax requires a length value:

```
	@media (width: 600px){ rules }
```

To give it a range we use two prefixes, max- and min-:

```
	@media (max-width: 480px){ rules }
	@media (min-width: 640px){ rules }
```

The height media feature works in the same way, except it targets browsers based on their height instead of width.

```
	@media (height: value) { rules }
	@media (max-height: value) { rules }
	@media (min-height: value) { rules }
```

### Pixel Ratio

The CSS pixel unit (px) is a measurement of a single-pixel on the computer screen. We also have a ratio of physical pixels to CSS pixels, known as device pixel ratio. This allows high graphic fidelity on small screens.

A DPR (device pixel ratio) of 2 is equal to 4 physical pixels, 2 horizontally and 2 vertically.

The pixel ratio feature lets us target devices based on their DPR:

```
	@media media and (resolution: value) { rules }
```

**Units**

|	Units	|		Description		|
| 	DPI. 	| Dots per Inch.	 	|
| 	DPCM. 	| Dots per centimeter. 	|
| 	DPPX 	| Dots per pixel. 		|

```
	@media (resolution: 1.5dppx){ rules }
```

**Prefixes**

```
	@media (max-resolution: number){ rules }
	@media (min-resolution: number){ rules }
```

_NOTE (IE)_: IE hasn’t implemented the DPPX value; to accommodate IE, you should use DPI, multiplying the required DPR by 96 (the DPI value of a standard screen).

```
	@media (resolution: 1.5dppx), (resolution: 144dpi){ rules }
```

_NOTE (SAFARI)_: Safari doesn’t support resolution, instead using a proprietary media feature called _-webkit-device-pixel-ratio_.

```
	@media (resolution: 1.5dppx), (resolution: 144dpi), (-webkit-device-pixel-ratio: 2) { rules }
```

### Device Width and Height

The width and height media features are related to the dimensions of the browser viewport. The device-width and device-height targets the screen width and height.

The width media feature is measured in CSS pixels, and device-width, in physical pixels. To make content readable and “natural sized” on a small screen, both dimensions need to match. You do this by adding the viewport meta tag into the head of the document.

```
	<meta name="viewport" content="width=device-width">
```

### Orientation

Orientation helps us to optimize our page for either horizontal or vertical.

```
	@media (orientation: value) { rules }
```

The value can be landscape or portrait.

### Aspect Ratio

We can create queries that apply when a certain width-to-height ratio is met. Can be either browser's aspect ratio or the device's aspect ratio.

```
	@media (aspect-ratio: horizontal/vertical) { rules }
	@media (device-aspect-ratio: horizontal/vertical) { rules }
```

## Multiple Media Features

You can chain multiple queries together on the same media type by adding expressions with the "and" operator.

```
	@media logic media and (expression) and (expression) { rules }
```

You can also use a conditional “or” expression by adding extra queries in a comma-separated list:

```
	@media logic media and (expression), logic media and (expression) { rules }
```

## Mobile-First Web Development

The common best-practice method of building websites today uses a method known as mobile-first development, where we start developing for smaller screens before adding larger assets and more complexity for users accessing the site on larger devices.
