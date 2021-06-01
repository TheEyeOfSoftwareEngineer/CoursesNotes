## CSS

Cascading Style Sheets

### Key concept: Seperate style from content

-   Content (what to display) is in HTML files
-   Formatting information (How to display) is in seperate style sheets (.css files)
-   Use an element attribute named class to link (e.g. <span class="test">)

### CSS Rules

```css
/* 
  body: Selector
  margin: Property
  8px: Value
  Declaration Block: font-family, ..., margin 
*/
body {
    font-family: Tahoma, Arial, sans-serif;
    color: black;
    background: white;
    margin: 8px;
}
```

| CSS Sekector    | CSS                           | HTML                       |
| --------------- | ----------------------------- | -------------------------- |
| Tag name        | `h1 { color: red; }`          | `<h1>today</h1>`           |
| Class attribute | `'large { font-size:16pt; }`  | `<p class="large">...</p>` |
| Tag and Class   | `p.large { ... }`             | `<p class="large>...</p>`  |
| Element id      | `#p20 { font-weight: bold; }` | `<p id="p20">...</p>`      |

### CSS Pseudo Selectors

-   hover: apply rule when mouse is over element (e.g. tooltip)

```css
p:hover,
a:hover {
    background-color: yellow;
}
```

-   a:link, a:visited: apply rule when link has been visited or not visited (link)

```css
a:visited {
    color: green;
}
a:link {
    color: blue;
}
```

### CSS Properities

Control many style properties of an element:

-   Coloring
-   Size
-   Position
-   Visibility
-   Many more: (e.g. `p { text-decoration: line-through; }`)
-   Also used in animation

#### Color: Properties: color & background-color

-   Predefined names: red, blue, green, white, etc
-   8-bit hexadecimal numbers for red, green, blue: #ff0000 (R:ff, G:00，B:00)
-   0-255 decimal intensities: rgb(255, 255, 0)
-   Percentage intensities: rgb(80%, 80%, 100%)

```css
h1 {
    color: red;
}
```

### CSS Box Model

`Total element width = width + left padding + right padding + left border + right border + left margin + right margin`

### CSS distance units
- Absolute
  - 2px: pixels
  - 1mm: millimeters
  - 2cm: centimeters
  - 0.2in: inches
  - 3pt: printer point 1/72 inch
- Relative
  - 2em: 2 times the element's current font size
  - 3rem: 3 times the root element's current font size

### Size Properties- Element, pad, margin, border
- width
- height

- padding-top
- padding-right
- padding-bottom
- padding-left

- margin-top
- margin-right
- margin-bottom
- margin-left

- border-bottom-color
- border-bottom-style
- border-bottom-width
- etc.
```css
p {
  border: 5px solid red;
}
```

### position property
- position: 
  - static; - (default) - Position in document flow
  - relative; - Position relative to default position via top, left, right, bottom properties
  - fixed; - Position to a fixed location on the screen via top, right, left, bottom properties
  - absolute; - Position relative to ancestor absolute element via top, right, left, bottom properties
- Fixed position (0,0) is top left corner

### Some more common properties
- background-image: image for element's background
- background-repeat: should background image be displayed in a repeating pattern (versus once only)
- font, font-family, font-size, font-weight, font-style: font information for text
- text-align, vertical-align: Alignment: center, left, right
- cursor - set the cursor when over element (e.g. help)

### Element visibility control properties
- display
  - none; - element is not displayed and takes no space in layout
  - inline; - element is treated as an inline element
  - block; - element is treated as a block element
  - flex; - element is treated as a flex container
  - grid; - element is treated as a grid container
- visibility:
  - hidden; - element is hidden but space still allocated
  - visible; - elements is normally displayed

### Flexbox and Grid layout
- display: flex; (Flexbox)
- display: grid; (Grid) newer lauyout method
  - items flex to fill additional space and shrink to fit into smaller spaces
  - useful for web app layout
    - divide up the available space equally among a bunch of elements
    - align of different sizes easily
    - key to handling different window and display sizes
- Flexbox: layout one dimension (row or column) of elements
- Grid: layout in two dimensions (rows or columns) of elements
- Covered in discussion section

### Some other CSS issues
- inheritance
  - some properties (e.g. font-size) are inherited from parent elements
  - Other (border, background) are not inherited
- Multiple rule matches
  - general idea: most specific rule wins
  ```css
  span.test { color: green; }
  span { color: red; }
  ```
  ```html
  <!-- red color -->
  <span>Text1</span> 
  <!-- green color -->
  <span class="test">Text2</span>
  ```

### Adding Styles to HTML
```html
<head>
  <!-- Seperate style sheet (best way) -->
  <link rel="stylesheet" type="text/css" href="myStyles.css" />
  <style type="text/css">
  body {
    /* Page-specific styles */
    font-family: Tahoma, Arial, sans-serif;
  }
 </style>
</head>
<body>
  <!-- Element-specific styles -->
  <div style="padding:2px;">
</body>
```

```html
<body>
  <h1>First Section Heading</h1>
  <p>
    Here is the first paragraph, containing
    text that really doesn't have any use
    or meaning; it just prattles on and on,
    with no end whatsoever, no point to
    make, really no purpose for existence
    at all.
  </p>
  <div class="shaded">
    <h1>Another Section Heading</h1>
    <p>
      Another paragraph.
    </p>
  </div>
</body>
```

```css
body {
  font-family: Tahoma, Arial, sans-serif;
  font-size: 13px;
  color: black;
  background: white;
  margin: 8px;
}
h1 {
  font-size: 19px;
  margin-top: 0px;
  margin-bottom: 5px;
  border-bottom: 1px solid black
}
.shaded {
  background: #d0d0ff;
}
```