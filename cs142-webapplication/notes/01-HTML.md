## HTML
HyperText Markup Language

### HTML tags
- Meaning of text
  - <h1> means top-level heading
  - <p> means paragraph
  - <ul> <li> for unordered (bulleted) list
- Formatting information (<i> for italic)
- Additional information to display (e.g., <img>)

### Document
hierarchical collection of elements, starting with <html>
- Element: start tag, contents, close tag
- Elements may be nested
- Every element must have an explicit start and end
  - can use <foo /> as shorthand for <foo></foo>
- start tags can contain attributes:
  - <img src="face.jpg">
  - <input type="text" value="111" name="zip">
  <div class="header">

### Handle markup characters in content
- `&lt;` -> `<`
- `&gt;` -> `>`
- `&amp;`-> `&`
- `&quot;`-> `"`
- `&nbsp;`-> Nonbreaking space

### common used XHTML tags
- <p>: paragraph
- <br>: Force a line break
- <h1>, <h2>, ..: Headings
- <b>, <i>: Boldface and italic
- <pre>: Typically used for code: indented with a fixed-width font, spaces are significant (e.g., newlines are preserved)
- <img>: Images
- `<a href="...">`: Hyperlink to another Web page
- `<!-- comments -->`: Comment tags
- <table>, <tr>, <td>: Tables
- <ul>, <li>: Unordered list (with bullets)
- <ol>, <li>: Ordered list (numbered)
- <div>: Used for grouping related elements, where the group occupies entire lines (forces a line break before and after) 
- <span>: Used for grouping related elements, where the group is within a single line (no forced line breaks)
- <form>, <input>, <textarea>, <select>, ...: Used to create forms where users can input data

### Commonly used tags: <head> section
- <title>: Specify a title for the page, which will appear in the title bar for the browser window.
- <link>: Include CSS stylesheets
- <script>: `Used to add Javascript to a page (can be used in body as well)`
