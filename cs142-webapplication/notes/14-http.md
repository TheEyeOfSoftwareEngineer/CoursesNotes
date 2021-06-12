## Hypertext Transport Protocol (HTTP)

### HTTP 
Simple request-response protocol layered on TCP/IP
1. Establish a TCP/IP connection to www.example.com:80
2. Send a http GET request along connection
3. Read from the connection the response from the web server

### Send HTTP Request - Write lines to socket
- Header
  - first line: Method URL Protocol Version
  - second: Host
  - User-Agent
  - Accept
  - Accept-Language
  - Accept-Charset
  - Connection
- Blank line
- Body(Optional)

### HTTP Methods (Verbs)
- GET - Fetch a URL
- HEAD - Fetch information about a URL
- PUT - Store to an URL
- POST - Send form data to a URL and get a response back
- DELETE - Delete a URL
GET and POST (forms) are commonly used. 
REST APIs used GET, PUT, POST, and DELETE

### HTTP Response - Read lines from socket
- Header
  - First line: Version Status Status Message
  - Date
  - Server
  - Content-Type
  - Content-Length
- blank line
- Body

### Common HTTP Response Status Codes
- 200 OK Success
- 307 Temporary Redirect Redirection - Browser retries using Location header
- 404 Not Found Famous one
- 503 Service Unavailable Something crashed on the server
- 500 Internal Server Error Something is messed up on the server
- 501 Not Implemented Coming
- 400 Bad Request Use if web app sends bogus request
- 401 Unauthorized Use if user isn't logged in
- 403 Forbidden Use if even logging in wouldn't help
- 550 Permission denied Not allow to perform request

### Browser caching control
- HTTP Response Header: Cache-Control: max-age=<Seconds>
Browser can reuse reply younger than the max-age
Cache-Control: max-age=120 - Age out in two minutes.
- Frequently used on fetches of static content like images, templates, CSS,
JavaScript.
- Good: Reduce app startup latency and server load
- Bad: Changes might not be picked up right away

### Browser spends its life fetching things using HTTP
- Some fetched immediately (processing paused while waiting for HTTP reply)
<link href="angular-material.css" rel="stylesheet" />
<script src="compiled/p2.bundle.js" type="text/javascript" />
window.location = "http://www.example.com";
- Some asynchronous and in parallel
<img src="smiley.gif">
<img src="foobar.jpg">
<img src="foobar2.jpg">
- Some can be in background
<a href="http://www.example.com"></a>
GET http://localhost:3000/favicon.ico 404 (Not Found)
