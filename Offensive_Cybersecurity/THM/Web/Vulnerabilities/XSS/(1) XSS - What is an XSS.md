#XSS #WEB #WebInjection

# What is an XSS ?

**Cross-Site Scripting (XSS)** is being used to *steal sessions, deliver malware, and escalate attacks within a network*.

- **Document Object Model (DOM)**: The Document Object Model (DOM) is the browser’s structured representation of a web page, essentially a tree of elements (tags, text, attributes) that your JavaScript can read and change. 

- **URL parameters**: URL parameters (query strings) are the bits after `?` in a URL that pass data to the site, for example, `https://site.com/search?q=hello`

- **Cookies**: Cookies store small pieces of data in the browser (session IDs, preferences). If a cookie is readable by JavaScript and an attacker can run JS via XSS, they can steal that cookie and hijack a session. `HttpOnly` is a flag that prevents JavaScript from reading the cookie.

- **Escaping**: Escaping means transforming user data so the browser treats it as plain text, not code, for example, turning `<` into `&lt`; so `<script>` becomes harmless text. 
	- *A filter* checks that the input looks allowed but doesn’t stop data from becoming code when it’s later placed into a page. 

---
# XSS payload usually has two parts:

**Intention**

This is what the attacker *wants the code to do*. 
- displaying a proof of concept, stealing session cookies, logging keystrokes, or performing actions on behalf of the user.

**Modification**

Every web application handles input differently. Because of this, attackers often need to modify the payload so that it executes correctly in a specific location on the page. For example, the payload may need to escape from an HTML tag, attribute, or JavaScript block before executing.