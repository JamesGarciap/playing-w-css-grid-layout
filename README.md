# Playing with: CSS Grid Layout

>The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

*Definition from: [w3schools](https://www.w3schools.com/css/css_grid.asp).*

### Useful links

* [CSS-TRICKS: A Complete Guide to Grid
](https://css-tricks.com/snippets/css/complete-guide-grid/)
* [W3Schools grid layout](https://www.w3schools.com/css/css_grid.asp)
* [CSS-TRICKS: Introduction to fr css unit](https://css-tricks.com/introduction-fr-css-unit/)
* [CSS-TRICKS: Lengths of css](https://css-tricks.com/the-lengths-of-css/)

### Properties:

***Grid Definition:*** You can define a css grid by using `grid` as value of the display property of a given container:

```
.grid-container {
  display: grid;  
}
```

***Handling columns***: Columns can be defined by using `grid-template-columns` which get the width of every column we want to set up in our grid.

```
.grid-container {
  display: grid;
  grid-template-columns: 50% 50%;
}
```

***Handling rows***: Rows can be defined by using `grid-template-rows` will set the height of the rows in the position of each value.

```
.grid-container {
  display: grid;
  grid-template-columns: 50% 50%;
  grid-template-rows: 50px 100px;
}
```

***Gird template***: Both, columns and rows can be placed in a single property called `grid-template`, which is able to process the number of rows over columns.

```
.grid-container {
  display: grid;
  grid-template: 50px 100px / 50% 50%;
                      ^          ^
                     rows     columns
}
```

***Gap***: You can add an space between rows and columns by using `grid-row-gap` and `grid-column-gap`:

```
.grid-container {
  display: grid;
  grid-template: 50px 100px / 50% 50%;
  grid-row-gap: 10px;
  grid-column-gap: 20px;
}
```

However it is possible to use a single property to group them, which is called `grid-gap`.


```
.grid-container {
  display: grid;
  grid-template: 50px 100px / 50% 50%;
  grid-gap: 10px 20px;
              ^    ^
            rows  columns
}
```

### Working with areas:
CSS grid layout is able to understand areas so that you can divide you layout into the pieces that makes more the sense for you design composition. This is possible by using a combination of `grid-template-areas` and `grid-area`.

Let's define some areas for a common layout.

```
.container {
  display: grid;
  grid-template: 150px 1fr 200px / 200px 1fr;
  grid-gap: 10px;
  grid-template-areas: "header header"
                       "left content"
                       "footer footer";
  height: 100vh;
}
```

Now with the areas defined we can define the selectors with will match with each area.

```
.header {
  grid-area: header;
}

.left {
  grid-area: left;
}

.content {
  grid-area: content;
}

.footer {
  grid-area: footer;
}
```

### CSS functions:
***repeat(times, length):***
You can use repeat to avoid writing the same value as times as columns you want to have in your grid so instead of define:
```
.grid-container {
  display: grid;
  grid-template-columns: 20% 20% 20% 20% 20%;
}
```
you can simplify it this way:
```
.grid-container {
  display: grid;
  grid-template-columns: repeat(5, 20%);
}
```
```
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}
```
***minmax(min, max)***
This function lets you to define a minimum and maximum value for the property which implements it, so that for example a column will keep it's width as min or max as you pass as parameters when call it.
```
.grid-container {
  display: grid;
  grid-template-columns: repeat(4, minmax(200px, 1fr));
}
```
