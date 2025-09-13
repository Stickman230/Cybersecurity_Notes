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
# HTTPS
*HTTPS (Hypertext Transfer Protocol Secure) is a secure version of the HTTP protocol*

Advantages:
- **Encryption of Data in Transit** - *When data is sent over an HTTPS connection, it is encrypted using strong cryptographic algorithms*. This ensures that even if an attacker intercepts the data while it's in transit, <u>they cannot decipher or read its contents</u>.
- **Protection Against Eavesdropping** - HTTPS prevents unauthorized parties from eavesdropping on the data exchanged between the user's browser and the web server. This is particularly *crucial when users input sensitive information, such as login credentials, credit card numbers, or personal details*.

![[HTTPS.png]]

---
# HTTP Request special characters
![[carriage_return&linefeeds.png]]