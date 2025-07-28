#Session #WEB  #WebAuthentication
# Why do we need sessions 

The HTTP protocol is inherently **stateless**. Sessions are, therefore, used to track users throughout their use of a web application. Session management is the process of managing these sessions and ensuring that they remain secure.

 ---
# Session Lifecycle

**Session Creation**
 - On many web applications, the initial session is already created when you visit the application. This is because some applications want to track your actions even before authentication. 
 - *Once you provide your username and password, you receive a session value that is then sent with each new request*

**Session Tracking**
-  This allows the web application to track your actions even though the HTTP protocol is stateless in nature.
- With each request made, the web application can recover the session value from the request and perform a server-side lookup to understand who the session belongs to and what permissions they have. 
( In the event that there are issues in the session tracking process, it may allow a threat actor to hijack a session or impersonate one. )

**Session Expiry**
- Your session value itself should have a lifetime attached to it.
- If the lifetime expires and you submit an old session value to the web application, it should be denied as the session should have been expired. Instead, *you should be redirected to the login page to authenticate again and start the session management lifecycle all over again!  *

**Session Termination**
- if the user perform a logout action the web application should terminate the user's session.
- While this is similar to session expiry, it is unique in the sense that even if the session's lifetime is still valid, the session itself should be terminated.
( Issues in this termination process could allow a threat actor to gain persistent access to an account. )

---

# IAAA Model
#IAAA

### Identification

**Identification is the process of verifying who the user is.**
- This starts with the user claiming to be a specific identity. In most web applications, this is performed by submitting your username.

### Authentication

**Authentication is the process of ensuring that the user is who they say they are.**
- Where in identification, you provide a username, for authentication, you provide proof that you are who you say you are.
- For example, you can supply the password associated with the claimed username.  
( *This is the point where session creation would kick in.*  )

### Authorization

**Authorization is the process of ensuring that the specific user has the rights required to perform the action requested. **
- For example, while all users may view data, only a select few may modify it. 
( *Session tracking plays a critical role in authorization.* )

### Accountability

**Accountability is the process of creating a record of the actions performed by users. **
- We should track the user's session and log all actions performed using the specific session. 

---
# Cookies vs Tokens

## Cookies
#Cookies

`Set-Cookie: session=12345;`  

Your browser will create a cookie entry for a cookie named `session` with a value of `12345` which will be valid for the domain where the cookie was received from.

**Several attributes can also be added to this header.**

- **Secure** - Indicates to the browser that the cookie may only be transmitted over verified HTTPS channels.

- **HTTPOnly** - Indicates to the browser that the cookie value may not be read by client-side JavaScript.

- **Expire** - Indicates to the browser when a cookie value will no longer be valid and should be removed.

- **SameSite** - Indicates to the browser whether the cookie may be transmitted in cross-site requests to help protect against CSRF attacks.

## Token

It relies on client-side code for the process. After authentication, the web application provides a token within the request body. Using client-side JavaScript code, *this token is then stored in the browser's LocalStorage*.

One of the most common types of tokens **is JSON Web Tokens (JWT),** which are passed through the `Authorization: Bearer` header.
- ***It is a bit of the wild west where anything goes, there are standards but not always followed...***

## Overall

|   |   |
|---|---|
|**Cookie-Session Management**|**Token-Based Session Management**|
|Cookie is automatically sent by the browser with each request|Token has to be submitted as a header with each request using client-side JavaScript|
|Cookie attributes can be used to enhance the browser's protection of the cookie|Tokens do not have automatic security protections enforced and should, therefore, be safeguarded against disclosures|
|Cookies can be vulnerable to conventional client-side attacks such as CSRF, where the browser is tricked into making a request on behalf of the user.|As the token is not automatically added to any request and cannot be read from LocalStorage by other domains, conventional client-side attacks such as CSRF are blocked.|
|As cookies are locked to a specific domain, it can be difficult to use them securely in decentralised web applications.|Tokens work well in decentralised web applications, as they are managed through JavaScript and can often contain all the information required to verify the token itself.|

---

[[(2) Session Management - Detection & Exploitation|Go to Session management - Detection & Exploitation]]
