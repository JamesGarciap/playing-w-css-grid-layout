# Playing with: CSS Grid Layout

>The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

*Definition from: [w3schools](https://www.w3schools.com/css/css_grid.asp).*

### Useful links

* https://css-tricks.com/snippets/css/complete-guide-grid/
* https://www.w3schools.com/css/css_grid.asp

### Some docs:

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
