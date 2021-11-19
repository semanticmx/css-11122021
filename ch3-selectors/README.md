# Selectors

Selectors can be broadly separated into two categories. The first are
those that act directly on elements defined in the document tree, this category contains class, type, and attribute selectors. The second category contains pseudo-selectors that act on elements or information that sits outside of the document tree.

We are going to review the first group.

## Attribute Selectors

they allow you to specify rules that match elements based on
their attributes.

```
	E[attr] {...} /* Simple Attribute Selector */
	E[attr='value'] {...} /* Exact Attribute Value Selector */
	E[attr~='value'] {...} /* Partial Attribute Value Selector */
	E[attr|='value'] {...} /* Language Attribute Selector */
```

Applies color to all rel attribute

```
	a[rel]{
		color: darkcyan;
	}
```

Applies color to all rel attribute that have the word 'friend' in it.

```
	a[rel~='friend']{
		color: darkred;
	}
```

Applies color to all rel that match exactly with the designated value.

```
	a[rel='friend']{
		color: darksalmon;
	}
```

Applies background color to all lang="es" attributes.

```
	a[lang|='es']{
		background-color: lightgrey;
	}
```

## New Attribute Selectors in CSS3

CSS3’s new selectors provide flexibility with the power to match substrings within an attribute value.

### Beginning Substring Attribute Value Selector

Finds elements whose chosen attribute begins with the string supplied to it as an argument.

```
	E[attr^='value'] {...}
```

Applies to all atributes that begin with 'example'

```
	a[rel^='example']{
		color: darkblue;
	}
```

### Ending Substring Attribute Value Selector

Like the beggining selector, this one selects only the end of the value.

```
	E[attr$='value'] {...}
```

### Arbitrary Substring Attribute Value Selector

It searches anywhere inside the value for the match word.

```
	E[attr*='value'] {...}
```

Applies purple color if it has "https://" insdie the href attribute, and if it has the number 2 at the end.

```
	a[href^='https://'][rel$='2']{
		color: purple;
	}
```

### General Sibling & Adjacent Sibling Combinator

**Adjacent Sibling**

The adjacent sibling selects the (F) element that is immediately preceded by element (E) _on the same level of the document tree_.

```
	E + F {...} /* Adjacent Sibling Combinator */
```

**General Sibling**

The general sibling selects any element (F) that is preceded by element (E) _on the same level of the document tree_.

```
	E ~ F {...} /* General Sibling Combinator */
```

Example:

```
	h2 + p { font-weight: bolder; } /* Adjacent Sibling */
	h2 ~ p { font-style: italic; } /* General Sibling */
```

The (p) element that adjacent (h2) is going to be bolder, and all the (p) that comes after (h2) is going to be Italic.

The (p) element that is inside the blockquote element, is not going to have any style, because is not on the same level as (h2). And the (p) element that is before the (h2), as before, is not going to have any style, because is before the (h2) element.
