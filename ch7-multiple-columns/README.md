# Multiple Columns

You can divide your content into columns using two methods: either prescriptively, by setting a specific number of columns, or dynamically, by specifying the width of columns and allowing the browser to calculate how many columns will fit into the width of the parent element.

## Prescriptive Columns: column-count

The simplest way to divide your content into equally distributed columns is
to use the column-count property:

```
	E { column-count: columns; }
```

Real Example:

```
	.columns{
	  column-count: 3;
	}
```

## Dynamic Columns: column-width

Specify the width of each column, and the browser fills the parent element with as many columns as can fit along its width.

```
	E { column-width: length; }
```

Real Example:

```
	.column-width{
	  column-width: 200px;
	}
```

## Varying Distribution of Content Across Columns

By default, content that’s flowed into multiple columns will be balanced as equally as possible across the columns. If you want to change this default behavior, you can do so with the column-fill property.

```
	E { column-fill: keyword; }
```

**_Values_**

- Balance --Is the default value, tries to make all the columns equal length.
- Auto --Fills collumns sequentially. The content is flowed into the first column to fill the height and then into the next column until that one is filled, and so on.

```
	.varying-dist{
	  column-count: 3;
	  column-fill: auto;
	}
```

## Combining column-count and column-width

You can set both column-count and column-width properties on an element. If both properties are applied to the same element, the column-count value acts as a maximum.

```
	.columns {
	 column-count: 3;
	 column-width: 150px;
	}
```

Real Example:

```
	.count-width{
	  columns: 150px 4;
	}
```

## Column Gaps and Rules

The browser place a default 1em gap between each column. However, we can alter that default and specify our own distances by using: column-gap and column-rule.

### Column Gap

Sets the space between columns

```
	E { column-gap: length; }
```

### Column Rule

column-rule property draws a line between columns.

```
	E {
	 column-rule-width: length;
	 column-rule-style: border-style;
	 column-rule-color: color;
	 column-rule: length border-style color;
	}
```

## Column span

Allows to span ceratin elements in multiple columns.

```
	.span{
	  column-span: all;
	}
```

## Containing Elements Within Columns

There's no role to help us to aling an element within the columns, but, we can set the element, or in this case the image, a max width 100% to avoid collision with the other columns

```
	.image{
	  border: solid 1px black;
	  columns: 3;
	  height: 200px;
	  width: 800px;
	  margin-bottom: 40px;
	  margin-left: 10px;
	}

	img{
	  max-width: 100%;
	}
```
