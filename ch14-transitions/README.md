# Transitions and Animations

Transitions only take effect when the property they are applied to changes value, whereas animations are explicitly executed when applied to an element.

## Transitions

Transitions enable you to define the transition between two states of an element.

### transition-property

The transition-property property specifies the name of the CSS property the transition effect is for.

```
	E { transition-property: keyword; }

	.one{transition-property: background-color;}
```

**Property Values**

none --No property will get a transition effect
all -- Default value. All properties will get a transition effect
property --Defines a comma separated list of CSS property names the transition effect is for

If we don't specify this property, by defaulft the browser is going to apply the all value. This can be troublesome because it'll require more processor speed.

### transition-duration

```
	E { transition-duration: time; }

	.two{transition-duration: 1000ms;}
```

The time value is a number with a unit of ms (milliseconds) or s (seconds).

### transition-timing-function

To control how element transitions between states, you use the transition-timing-function property. This property allows for variations in speed along with the duration of the transition, which gives you control over the animation’s pace.

```
	E { transition-timing-function: keyword; }

	.four{transition-timing-function: linear;}
```

**Property Values**

- ease --Default value. Specifies a transition effect with a slow start, then fast, then end slowly.
- Linear --Specifies a transition effect with the same speed from start to end.
- ease-in --Specifies a transition effect with a slow start.
- ease-out --Specifies a transition effect with a slow end .
- ease-in-out --Specifies a transition effect with a slow start and end.

#### Cubic Bézier Curve

A cubic Bézier curve is a smooth, continuous curve that passes through four points plotted on a grid that goes from 0 to 1 along both axes. The four points are known as P0, P1, P2, and P3. They define the curvature and are plotted with pairs of (x, y) coordinates, where the first (P0) is always at (0, 0) and the last (P3) is always at (1, 1). The other two points are defined in the function: (x1, y1) and (x2, y2).

```
	E { transition-timing-function: cubic-bezier(x1, y1, x2, y2); }
```

A linear animation progresses in a straight line from (0, 0) to (1, 1), but we can change the values to specify different speeds.

#### steps()

We also can use the function steps(), which run the animation in a series of staggered intervals.

```
	E {transition-timing-function: steps(count, direction);}
```

### transition-delay

Sets the time when the transition starts.

```
	E{transition-delay: time;}

	.three{transition-delay: 700ms;}
```

### transition shorthand property

```
	h1 {
	 transition-property: font-size;
	 transition-duration: 2s;
	 transition-timing-function: ease-out;
	 transition-delay: 250ms;
	}
```

```
	E { transition: property duration timing-function delay; }
	h1 { transition: font-size 2s ease-out 250ms; }
```

### multiple transitions

We can easily add multiple transitions to an element by providing a list of comma-separated values to the individual or shorthand properties.

```
	.three{
		transition-property: background-color, color, font-size, transform;
		transition-duration: 1000ms;
		transition-delay: 700ms;
	}

	.three:hover{
		background-color: grey;
		color: darkred;
		font-size: 20px;
		transform: rotate(45deg);
	}
```

## Animations

CSS allows animation of HTML elements without using JavaScript or Flash. The CSS3 Animations Module goes beyond what is possible with transitions, allowing animations to be applied directly to elements with a syntax that is more flexible and permits more granular control.

### Keyframes

We can think of CSS animations as a series of transitions, chained into a sequence. keyframes are the points that set the start and end of a transition.

```
	@keyframes name {
	 selector { property : value; }
	}
```

The first value for the @keyframes rule is named; this unique identifier is used to call the animation.

The next value, selector, sets the position along the duration of the animation that the keyframe will occur. The usual value here is a percentage value, but we also can use keywords as "from" or "to", which are analogous to 0 percent and 100 percent.

Example:

```
	@keyframes move{
		from{background-position: bottom left;}
		50%{background-position: bottom center;}
		to{background-position: bottom right;}
	}
```

### animation-name

The animation-name property refers to an animation that’s been defined with the @keyframes rule.

```
	E { animation-name: name; }
	.crate:hover{animation-name: move;}

```

### animation-duration

Sets the animation duration.

```
	E { animation-duration: time; }

	.crate:hover{
		animation-name: move;
		animation-duration: 1s;
	}
```

### animation-timing-function

Does the same as transition-timing-function. Specifies the speed curve of an animation.

```
	E {animation-timing-function: value;}

	.crate:hover{
		animation-name: move;
		animation-duration: 1s;
		animation-timing-function: linear;
	}
```

### animation-delay

The animation-delay property specifies a delay for the start of an animation.

```
	E { animation-delay: time; }

	.crate:hover{
		animation-name: move;
		animation-duration: 1s;
		animation-timing-function: linear;
		animation-delay: 250ms;
	}
```

### animation-iteration-count

The animation-iteration-count property specifies the number of times an animation should be played.

```
	E { animation-iteration-count: count; }

	.nine{animation-iteration-count: 5;}
```

### animation-direction

The animation-direction property defines whether an animation should be played forwards, backward, or in alternate cycles.

```
	E { animation-direction: keyword; }

	.ten{animation-direction: reverse;}
```

### animation-fill-mode

The animation-fill-mode property specifies a style for the element when the animation is not playing (before it starts, after it ends, or both).

```
	E { animation-fill-mode: keyword; }
	.eleven{animation-fill-mode: forwards;}
```

**Property Values**

- forwards --The element will retain the style values that is set by the last keyframe (depends on animation-direction and animation-iteration-count).
- backwards --The element will get the style values that is set by the first keyframe (depends on animation-direction), and retain this during the animation-delay period.
- both --The animation will follow the rules for both forwards and backwards, extending the animation properties in both directions.

### animation-play-state

The animation-play-state property specifies whether the animation is running or paused.

```
	E { animation-play-state: keyword; }

	.twelve:hover{animation-play-state: paused;}
```

### animation shorthand

```
	div {
	 animation-name: expand;
	 animation-duration: 6s;
	 animation-timing-function: ease-in;
	 animation-delay: 2s;
	 animation-iteration-count: 10;
	 animation-direction: alternate;
	 animation-fill-mode: forwards;
	 animation-play-state: running;
	}
```

```
	E { animation: name duration timing-function delay iteration-count direction
fill-mode play-state; }

	iv { animation: expand 6s ease-in 2s 10 alternate both running; }
```
