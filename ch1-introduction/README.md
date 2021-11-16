# What's CSS?

CSS is the language we use to style a Web page. It describes how HTML elements are to be displayed on the screen.

## CSS3

CSS3 is divided into various modules, each module could be worked on by different authors at different paces. Each module has designated a level to mark how many revisions it has been through. Some of them are at level 4 and, some of them are only at level 1.

CSS3 is not a complete package, it has modules, and each module will move at its peace.

## Syntax

First, we use a selector. To know which element we are going to edit. After it, we use a property. The property tells the browser which edition is going to apply. In the end, we use the value.

```
	.selector {property: value;}
```

For this example, I selected the body element, the property is to change background color and the value is the color "grey".

```
	body{
		background-color: grey;
	}
```

## Vendor Prefixes

On occasion, each browser can interpret the property in different ways, so we have to specify for which browser is each property.

```
	E {
		-moz-monkeys: value; /* Firefox */
		-ms-monkeys: value; /* Internet Explorer */
		-webkit-monkeys: value; /* Chrome/Safari */
	}
```
