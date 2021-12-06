# Web Fonts

Web fonts allow Web designers to use fonts that are not installed on the user's computer.

## Font Face Rule

To display web fonts we need to define them by using the @font-face rule.

```
	@font-face {
		font-family: 'Birds';
		src:url('Birds.ttf') format('truetype');
	}

	h1{
		font-family: 'Birds';
	}
```

First, we define the font name with the _font-family_ property.

```
	font-family: 'Birds';
```

Afterwards, we specify the path and the format:

```
	src:url('Birds.ttf') format('truetype');
```

Lastly, we use the name previously defined and, we apply it to an element.

## Defining Different Faces

If we want to use a different face, such as a bolder weight or an italic type, you have to define each font face individually.

```
	@font-face {
		font-family: 'Birds';
		font-style: italic;
		src:url('Birds.ttf') format('truetype');
	}
```

## Bulletproof Font face

To make sure that the web font is going to display in every browser we have to make it compatible, for that we need different web formats.

- eot --This format supports IE8 and bellow.
- ttf --Supports Safari 3+, Chrome 4+, Opera 10+, IE9 (partial).
- woff --Supports Safari 5+, Chrome 6+, Opera 11+, IE9+.

```
	@font-face {
	  font-family: statik;
	  src: url("fonts/static.oet") format("embedded-opentype");
	  src: url("fonts/statik.woff") format("woff");
	  src: url("fonts/statik.ttf") format("truetype");
	}
```

## font-size-adjust

The font-size-adjust property gives you better control of the font size when the first selected font is not available. When a font is not available, the browser uses the second specified font. This could result in a big change for the font size. To prevent this, use the font-size-adjust property.

```
	E { font-size-adjust: number; }
```

The number value is the proportion of the total height that is occupied by a lowercase x character (known as the x-height). In other words, a font might be 16px high in total, but the height of the lowercase x might be half that (8px), which gives an x-height ratio of 0.5 (8 divided by 16):

```
	p { font-size-adjust: 0.5; }
```

_Note: font-size-adjust only works in Firefox_

## font-stretch

The font-stretch property allows you to make text narrower (condensed) or wider (expanded).

```
	E { font-stretch: keyword; }
```

_Note: font-stretch only works in Firefox and IE. Also, If this doesn't appear to work, it's likely that your computer doesn't have a condensed or expanded version of the font being used._

## font-feature-settings

The font-feature-settings property allows control over advanced typographic features in OpenType fonts.

```
	E { font-feature-settings: "parameters"; }
```

## font-variant-ligatures

The font-variant-ligatures CSS property controls which ligatures and contextual forms are used in textual content of the elements it applies to.

```
	E { font-variant-ligatures: no-discretionary-ligatures; }
```
