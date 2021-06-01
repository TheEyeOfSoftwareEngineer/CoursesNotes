### URL
Universal Resource Locator

### Hypertext
- Text with links to other text
  - click on links takes you somewhere else
  - old ideas:
- Web adapted the idea, link specification

### Parts of an URL
`http://host.company.com:80/a/b/c.html?user=Alice&year=2008#p2`
- Scheme(http:): identifies protocol used to fetch the content
- Host name(//host.conpany.com): name of a machine to connect to
- Server's port number(80): allows multiple servers to run on the same machine
- Hierarchical portion(/a/b/c.html): used by server to find content
- Query parameters(?user=Alice&yearo=2008): provides additional parameters
- Fragment(#p2): Have brower scroll page to fragment

### URL: schemes
- http: is the most common scheme; it means use the HTTP protocol
- https: is similar to http: except that is uses SSL encryption
- file: means read a file from the local disk
- mailto: means open an email program composing a message
There are several other schemes, such as ftp:, but they aren't used much
anymore.

### URL: Hierarchical portion
- Passed to the web server for interpretation. Early web servers:
  - Path name for a static HTML file
  - Path name of a program that will generate the HTML content(e.g. foo.php)
- Web server programmed with routing information
  - Map hierarchical position to function to be proformed and possibly the function's parameters
- Application Programming Interface (API) design
  - /user/create
  - /user/list
  - /user/0x23490
  - /user/0x23433
  - /user/delete/0x23433

### Query Parameters
- Traditionally has been to provide parameters to operation
  - `http://www.company.com/showOrder.php?order=4621047`
- FOr modern apps has implications of when the brower switches pages

### Links
- Brower maintain a notion of current location
- Links: content in a page which, when clicked on, causes the brower to go to URL
- Links are implemented with the <a> tag:
  - `<a href="http://www/company.com/news/2009.html">2009 News</a>`

### Different types of links
- Full URL:
  - `<a href="http://www/company.com/news/2009.html">2009 News</a>`
- Absolute URL:
  - `<a href="/stock/quote.html">` same as http://www.xyz.com/stock/quote.html
- Relative URL(intra-site links):
  - `<a href="2008/March.html">` same as http://www.xyz.com/news/2008/March.html
- Define an anchor point(a position that can be referenced with # notation):
  - `<a name="sec3">`
  - Go to a different place in the same page: `<a href="#sec3">`

### Uses of URLS
- Loading a page: type the URL into your brower
- Load a image: `<img src="..." />`
- Load a stylesheet: `<link rel="stylesheet" type="text/css" href="...">`
- Embedded a page: `<iframe src="http://www.google.com">`

### URL Encoding
- What if you want to include a punctuation character in a query value?
  - `http://www.stats.com/companyInfo?name=C&H Sugar`
- Any character in a URL other than A-Z, a-z, 0-9, or any of -_,~ must be represented as %xx, where xx is the hexadecimal value of the character
  - `http://www.stats.com/companyInfo?name=C%26H%20Sugar`
- Escaping is a commonly used technique and also a source of errors

