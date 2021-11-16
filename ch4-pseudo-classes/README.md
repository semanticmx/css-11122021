# Pseudo-classes and Pseudo-elements

Pseudo-classes and pseudo-elements are selectors that act on information about elements that extend (or sit outside of) the document tree.

## Link States

**:link**
Normal, unvisited link.

```
	.enlace:link {
	  color: rgb(27, 27, 216);
	}
```

**:hover**
A link when the user mouses over it.

```
	.enlace:hover {
	  color: rgb(255, 145, 0);
	}
```

**:active**
Change the color the moment it's clicked.

```
	.enlace:active {
  		background: black;
	}
```

**:visited**
A link the user has visited.

```
	.enlace:visited {
		color: #a53d3d;
	}
```

## :first-child / :last-child

Allows us to select the first or the last element from a container

**:first-child**

```
	.parrafos p:first-child {
	  background: blueviolet;
	  color: #fff;
	}
```

**:last-child**

```
	.parrafos p:last-child {
  		background: black
  		color: #fff;
	}
```

## :first-of-type / :last-of-type

Allows us to select the first or the last element of the same type from a container.

```
	.elementos p:first-of-type {
		background: blueviolet;
		color: #fff;
	}
```

## :nth-child() / :nth-last-child

### :nth-child()

**Select an element with a specific number**

Allows selecting elements based on either their position in the document tree with their parent element.

```
	.lista :nth-child(2) {
  		background: blueviolet;
  		color: #fff;
	}
```

From the parent "ul" element, we are going to select the second child element.

**Select an element with odd or even**

```
	.lista :nth-child(odd){
	  background: darkred;
	  color: #fff;
	}
```

**Select an element every certain value**

```
	.lista :nth-child(4n) {
	  background: darkcyan;
	  color: #fff;
	}
```

### :nth-last-child

It's the same as _:nth-child()_ the only difference is that start counting from the last to the first element.

```
	.lista :nth-last-child(3) {
	  background: #000;
	  color: #fff;
	}
```

## :nth-of-type() / :nth-last-of-type()

It's the same as _:nth-child()_. The only difference is instead of selecting from the same element, selects from types of elements

**:nth-of-type()**

```
	.lista2 p:nth-of-type(2) {
		background: blueviolet;
		color: #fff;
	}
```

**:nth-last-of-type()**

```
	.lista2 div:nth-last-of-type(2) {
	  background: black;
	  color: #fff;
	}
```

## :only-child

This pseudo-class allows a selection of only one element from the parent element, and this element must be the only child.

```
	.lista3 p:only-child {
	  background: blueviolet;
	  color: #fff;
	}
```

## :only-of-type

This one allows selecting only one element of his kind in the section.

```
	.lista4 p:only-of-type {
	  background: blueviolet;
	  color: #fff;
	}
```

## Other Pseudo-classes

### :target

Selects an element with the ID matching the URL fragment identifier (#identifier).


```
	#my_id:target {
	  background-color: rgb(128, 128, 128);
	  color: white;
	  padding: 5px;
	  text-align: center;
	  width: 100%;
	}
```

### :empty

Selects the empty elements.

```
	.empty:empty {
	  background-color: red;
	  height: 30px;
	  width: 30px;
	}
```

### :root

Selects the first element in a document tree, which is the HTML element.

```
	:root {
	  background-color: darkcyan;
	}
```

### :not()

Selects all the elements except those that are given as the value.

```
	.pick:not(.not){
	  background-color: yellow;
	}
```

### UI Element State

Elements relating to forms and user input can have various states; they can be disabled or checked.

```
	:checked {...}
	:disabled {...}
	:enabled {...}
```

examples:

```
	input[type='text']:disabled{
	  border: 1px dotted black;
	  background-color: gray;
	  color: white;
	}
```

```
	input[type='text']:enabled{
	  border: 1px solid black;
	}
```

```
	input[type='checkbox']:checked{
	  cursor: crosshair;
	}
```

### Constraint Validation Pseudo-Classes

You can style elements depending on whether they’re required or optional by using their namesake pseudo-classes:

```
	:required {...}
	:optional {...}
```

Each form field can be in one of two states of validation: either valid or invalid. If no specific constraints are applied, either by the browser or the author, a form field is valid by default.

```
	:valid {...}
	:invalid {...}
```

```
	input[type='text']:invalid{
	  border-color: red;
	}
```

Some HTML5 elements can have a permitted range of values, set by using the min and max attributes. We can style these elements depending on whether the current value is in or out of range.

```
	:in-range {...}
	:out-of-range {...}
```

```
	input[type='number']:in-range{
	  background-color: green;
	}
```

## Pseudo Elements

Like pseudo-classes, pseudo-elements provide information that is not specified in the document tree. But where pseudo-classes use “phantom” conditions such as an element’s position in the tree or its state, pseudo-elements go further and allow you to apply styles to elements that don’t exist in the tree at all.

### ::after / ::before

Adds an element before or after the selected element, but the added element is going to be within the selected element.

```
	::after {...}
	::before {...}
```

### ::first-line / ::first-letter

**::first-letter**

Selects the first letter from an element.

```
	.article > p::first-letter{...}
```

**::first-line**

Selects the first line from an element.

```
	.article2 > p::first-line{...}
```

### ::selection

Change the style when a text is selected.

```
	.article2 > p::selection{
		background-color: black;
		color: white;
	}
```
