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

---

[[(2) Session Management - Detection & Exploitation|Go to Session management - Detection & Exploitation]]
