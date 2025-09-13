#eJPT #WEB #INE #HTTP

*HTTP (Hypertext Transfer Protocol) is a stateless application layer protocol used for the transmission of resources like web application data and runs on top of TCP.*

**HTTP has 2 versions; HTTP 1.0 & HTTP 1.1**, <u>HTTP 1.1 is the most widely used version of HTTP</u> and has several advantages over HTTP 1.0 such as the ability to re-use the same connection and can request for multiple URI’s/Resources.

# HTTP Methods

![[HTTP_methods.png]]

---
# HTTP Request Structure

### Request Line
*The request line is the first line of an HTTP request and contains the following three components:*
○ **HTTP method** (e.g., GET, POST, PUT, DELETE, etc.): Indicates the type of request being made.
○ **URL** (Uniform Resource Locator): The address of the resource the client wants to access.
○ **HTTP version**: The version of the HTTP protocol being used (e.g., HTTP/1.1).

### Request Headers
*Headers provide additional information about the request. Common headers include:*
○ **User-Agent**: Information about the client making the request (e.g., browser type, machine format to display on).
○ **Host**: The hostname of the server.
○ **Accept**: The media types the client can handle in the response (e.g., HTML, JSON).
○ **Authorization**: Credentials for authentication, if required.
○ **Cookie**: Information stored on the client-side and sent back to the server with each request.

### Request Body (Optional)
*Some HTTP methods (like POST or PUT) include a request body where data is sent to the server, typically in JSON or form data format.*

---

# HTTP Response Structure

### Request Headers
*Common headers include:*
○ **Content-Type**: The media type of the response content (e.g., text/html,application/json).
○ **Content-Length**: The size of the response body in bytes.
○ **Set-Cookie**: Used to set cookies on the client-side for subsequent requests.
○ **Cache-Contro**l: Directives for caching behavior.

### Response Body (Optional)
*The response body contains the actual content of the response. For example, in the case of an HTML page, the response body will contain the HTML markup.*

### Cache Control Header

![[cache_control.png]]

---
# HTTP Request special characters
![[carriage_return&linefeeds.png]]