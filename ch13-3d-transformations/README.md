# 3D Transformations

Three-dimensional objects in CSS are based on the Cartesian coordinate system. In 3D transformations we add a z-axis, the z-axis is based on the viewer.

So the x-axis goes left to right. The y-axis goes up and down. The z-axis goes toward and away.

## Rotation

The 2D rotation has only one axis to rotate around, so the rotate() function requires only a single value. 3D rotation we’ve got three axes to rotate around and, therefore, three properties to control this.

```
	E {
	transform: rotateX(angle);
	transform: rotateY(angle);
	transform: rotateZ(angle);
	}
```

If we want to rotate an element around more than one axis, we can apply multiple functions to an element.

```
	E { transform: rotateX(angle) rotateY(angle) rotateZ(angle); }
```

### rotate3d()

```
	E { transform: rotate3d(x,y,z,angle); }
```

x-axis, y-axis, and z-axis take a number value, which is used to calculate a direction vector. The origin of the vector is the point where all the axes meet, by default, the center of the element, represented by the values 0,0,0.

A direction vector is a line in three-dimensional space, going from the origin to the coordinates given by the x-,y-,z- values provided to the rotate3d() function. The element will be rotated around this line by the amount specified in the angle value.

Example:

```
	.rotate{
		transform: rotate3d(1, 1, 1, 45deg);
	}
```

It's going to rotate 45 degrees in axis x-, y-, z-.

## Perspective

Creates an artificial viewpoint from where you view the object in threedimensional space, providing the illusion of depth.

```
	E { transform: perspective(depth); }

	.grupo{
		perspective: 700px;
	}
```

## Translations

Translate z- moves the element forwards and backward, translate x- moves the element right and left, and translate y- moves the element upwards and downwards.

```
	E { transform: translateZ(length); }
```

## Scaling

To resize an element along the z-axis we use the function.

**scaleZ()**

```
	E { transform: scaleZ(number); }
```

## Matrix

Any time we do a CSS transform, we're affecting the matrix. Even if you use another function such as rotate3d(), you're still affecting the matrix. The matrix determines the coordinates of the element — its position, size, orientation, etc.

matrix() allows us to create linear transformations, while matrix3d() lets us create the illusion of three dimensions in two dimensions using CSS.

The matrix3d() defines a 3D transformation as a 4x4 homogeneous matrix. The matrix3d() function accepts sixteen arguments that determine how the element will be transformed.

```
	E { transform: matrix3d(
	 m01,m02,m03,m04,
	 m05,m06,m07,m08,
	 m09,m10,m11,m12,
	 m13,m14,m15,m16
	); }
```

The values: m01,m02,m03,m04,m05,m06,m07,m08, m09,m10,m11,m12, are numbers describing the linear transformation. The values: m13,m14,m15,m16, are numbres describing the translation.

## Perspective Origin

Besides changing the perspective depth, we also can change the x- and y- positions.

```
	E { perspective-origin: x-position y-position; }
```

The x-position value can be any one of the keywords—left, right, or center—and the y-position value can be top, bottom, or center. Percentage or length values can also be used.

## Transformation Origin

The origin point is the point at which all transformations are applied. The property transform-origin also accepts z- value.

```
	E { transform-origin: x y z; }
```

## Transform-style Property

When elements transformed in 3D are nested, the default behavior is that all descendant elements are flattened to the plane of the parent—that is, any transformation functions applied to child elements are ignored. We can change this behavior with a property called transform-style.

```
	E { transform-style: keyword; }
```

The keyword value can be either flat (the default) or preserve-3d.

## Backface

The backface property allows us to watch or not the back part of an element.

```
	E { backface-visibility: state; }
```

The state value is one of two keywords: hidden or visible.
