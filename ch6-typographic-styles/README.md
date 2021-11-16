# Typographic Styles

## Applying dimensional effects: text-shadow

The position of the shadow is set using the x- and y- coordinates as a cartesian coordinate system. Positive x- to the left, negative x- to the right, positive y- goes downwards, negative y- upwards.

```
	E { text-shadow: x y; }
```
Real example:

```
	h1{ 
		text-shadow: 3px 3px #BBB; 
	}
```

### blur-radius

This option sets the extent of a blur effect on the shadow and must be used after the offset values

```
	#text2{ 
		text-shadow: 3px 3px 3px #BBB; 
	}
```

The blur radius value is, like the two offset values, also an integer with
a length unit; the higher the value, the wider (and lighter) the blur.

### Multiple shadows

Just supply extra values to the property, using commas to separate them.


```
	E { text-shadow: value, value, value; }
```

## Restricting Overflow

Restric text to a single line and a fixed width.

```
	p{
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
```

overflow: hidden; -- Prevent the content showing outside of the border.
white-space: nowrap; -- Prevent from wrapping ove multiple lines.
text-overflow: ellipsis; -- Show three dots.

## Text Aligning

The text aling property let us aling the text in whatever way we want, the syntax is:

```
	#align{
		text-align: justify;
		text-align-last: right;
	}
```
The text-align-last property, lets you set the alignment of the last (or only) line of text in a justified block

## Controlling Line Wrapping

Word-wrap, specifies whether the browser can break long words to make them fit into the parent element.

```
	E { word-wrap: keyword; }
```

Also works with:

```
	#wrap{
		overflow-wrap: break-word;
	}
```

### Hyphends

Hyphens indicate where the break in a word occurs. It has three values; Manual, Auto, None. We have to add &shy; if hyphens: manual; is specified.

```
	#hyphens{
		hyphens: manual;
	}
```
### Resizing ELements

This property lets you control an element’s dimensions by providing a handle with which you can drag the element out to a different size.

```
	#resize{
		overflow: auto;
		resize: both;
	}
```