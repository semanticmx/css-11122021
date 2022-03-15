# Color

CSS lets us manipulate the color of the elements within the page. There are many ways to set a color. We can do it with names, "red", or we can do it with RGB values.

**Values**

- By color names
- As RGB values
- As hexadecimal values
- As HSL values (CSS3)
- As HWB values (CSS4)
- With the currentcolor keyword

## Opacity Property

Opacity is the measure of an object’s resistance to light— the more opaque something is, the less light it lets through. An object with no opacity is fully transparent.

The opacity property specifies the opacity/transparency of an element. Syntax:

```
	E { opacity: number; }
```

## Alpha Channel

The Alpha channel (Alpha for short) is the measure of the opacity of a color. Is used in RGBA Value, RGBA color values are an extension of RGB color values with an alpha channel - which specifies the opacity for a color.

```
	.rgba {
	  background-color: rgba(255, 255, 255, 0.5);
	}
```

## Hue, Saturation, Lightness

HSL — which stands for Hue, Saturation, Lightness — is a cylindrical-coordinate representation of color space.

All the possible colors are arranged in a cylinder with a central axis. The angle around the axis is the hue, the distance from the axis is the saturation, and the distance along the axis is the lightness. The combination of those three values creates a unique color.

### Hue

Hue represents the major colors, starting and ending with red (0 or 360) and including all the main colors between. Think of the colors of the visible spectrum.

### Saturation

Saturation is the strength or intensity of that color: 0 percent is zero intensity, which makes the color a shade of gray, and 100 percent is full strength, the most intense version of that color.

### Lightness

Lightness is the brightness or darkness of the color: 50 percent is the true color, 0 percent is black, and 100 percent is white.

### Syntax

First, we use the property hsl, then we specify the values, the first one is the hue, then the saturation, and lastly the lightness.

```
	body {
	  background-color: hsl(30, 100%, 50%);
	}
```

## Current Color

The current-color is a keyword that acts as a variable that allows us to set a color of an element to the current color. So, if the main color change, it'll change automatically.

```
	border: solid 3px currentColor;
```
