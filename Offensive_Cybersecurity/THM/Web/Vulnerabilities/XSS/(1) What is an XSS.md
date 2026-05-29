#XSS #WEB #WebInjection

**Cross-Site Scripting (XSS)** is being used to *steal sessions, deliver malware, and escalate attacks within a network*.

- **Document Object Model (DOM)**: The Document Object Model (DOM) is the browser’s structured representation of a web page, essentially a tree of elements (tags, text, attributes) that your JavaScript can read and change. 

- **URL parameters**: URL parameters (query strings) are the bits after `?` in a URL that pass data to the site, for example, `https://site.com/search?q=hello`

- **Cookies**: Cookies store small pieces of data in the browser (session IDs, preferences). If a cookie is readable by JavaScript and an attacker can run JS via XSS, they can steal that cookie and hijack a session. `HttpOnly` is a flag that prevents JavaScript from reading the cookie.

- **Escaping**: Escaping means transforming user data so the browser treats it as plain text, not code, for example, turning `<` into `&lt`; so `<script>` becomes harmless text. 
	- *A filter* checks that the input looks allowed but doesn’t stop data from becoming code when it’s later placed into a page. 