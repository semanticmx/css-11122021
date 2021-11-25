# 2D Transformations

The transform property applies a 2D or 3D transformation to an element. This property allows you to rotate, scale, move, skew, etc., elements.

```
	E { transform: function(value); }
```

## Rotate

It rotates the element around a set point

```
	E { transform: rotate(value); }
```

## Transformation Origin

The origin of a transformation is the point on an element about which that transformation happens. We can change it with the transform-origin property.

```
	E { transform-origin: value; }
```

**Property Values**

- x-axis --left, center, right, length, %
- y-axis --top, center, bottom, length, %

Example:

```
	.origin{
		transform-origin: right top;
		transform: rotate(10deg);
	}
```

## Translate

Which moves the element from its default position along the horizontal or vertical axes.

```
	E { transform: translateX(value) translateY(value); }
```

**Property Values**

- translate(x,y) --Defines a 2D translation, moving the element along the X- and the Y-axis.
- translateX(n) --Defines a 2D translation, moving the element along the X-axis.
- translateY(n) --Defines a 2D translation, moving the element along the Y-axis.

Example:

```
	.translate{
		 transform: translate(20px,15px);
	}
```

## Scale

We can make an element larger or smaller than the original by using scale functions.

```
	E { transform: scaleX(value) scaleY(value); }
```

**Property Values**

- scale(x,y) --Defines a 2D scale transformation, changing the elements width and height.
- scaleX(n) --Defines a 2D scale transformation, changing the element's width.
- scaleY(n) --Defines a 2D scale transformation, changing the element's height.

Example:

```
	.scale{
		transform: scaleX(0.8) scaleY(0.8);
	}
```

## Skew

To skew an element is to alter the angle of its horizontal or vertical axis.

```
	E { transform: skewX(value) skewY(value);}
```

**Property Values**

- skew(x-angle,y-angle) --Defines a 2D skew transformation along the X- and the Y-axis.
- skewX(angle) --Defines a 2D skew transformation along the X-axis.
- skewY(angle) --Defines a 2D skew transformation along the Y-axis.

Example:

```
	.skew{
		transform: skewX(15deg);
	}
```

## Transforming Elements with Matrices

Each of the transformation functions used in this chapter so far can also be expressed as a transformation matrix.

The 2D transformation matrices, and the matrix() function, accept six values, the combination of which can be used to create the functions introduced before.

```
	E { transform: matrix(a,b,c,d,X,Y); }
```

The parameters are: _matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY())_

### Scew with matrix

The angle refers to the degrees (counterclockwise) of the angle you want to skew by. If you want to skew an element by 15 degrees, the value you’re looking for is the tangent of 15.

```
	E { transform: matrix(1,tan(angle),0,1, X,Y); } /* X Axis */
	E { transform: matrix(1,0,tan(angle),1, X,Y); } /* Y Axis */
```

### Rotate with matrix

We can rotate elements with skew functions, for this we need to use sine and cosine functions.

```
	E { transform: matrix(cos(angle),sin(angle),-sin(angle),cos(angle),X,Y); }
```

To rotate 60 degrees we have to calculate cos(60) = 0.5 and sin(60) = 0.87

**Rotation with matrix()**

```
	 transform: matrix(1,0.27,0,1,0,0);
```
