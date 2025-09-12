#eJPT #WEB #INE #Client #Server

*Web application architecture refers to the structure and organization of components and technologies used to build a web application.*
# Client-Server Model

In this architecture, the web application is divided into two main components:

- **Client:** The client represents *the user interface and user interaction with the web application*. It is the front-end of the application that users access through their web browsers. The client is *responsible for displaying the web pages, handling user input, and sending requests to the server for data or actions*.

- **Server:** The server represents *the back-end of the web application*. It processes client requests, *executes the application's business logic, communicates with databases and other services, and generates responses to be sent back to the client.*

![[Client_Server.png]]

#### Key characteristics of client-side processing:
○ **User Interaction**: Client-side processing is well-suited for tasks that require immediate user interaction and feedback, as there is no need to send data back and forth to the server.

○ **Responsive User Experience:** Since processing happens locally, client-side operations can provide a smoother and more responsive user experience.

○ **JavaScript:** JavaScript is the primary programming language used for client- side processing. It allows developers to manipulate the web page's content, handle user interactions, and perform validations without involving the server.

○ **Data Validation:** Client-side validation ensures that user input meets specific criteria before it is sent to the server, reducing the need to make unnecessary server requests.

#### Key characteristics of server-side processing:
○ **Data Processing**: Server-side processing is ideal for tasks that involve sensitive data handling, complex computations, and interactions with databases or external services.

○ **Security:** Since server-side code is executed on a trusted server, it is more secure than client-side code, which can be manipulated by users or intercepted by attackers.

○ **Server-side Languages**: Programming languages like PHP, Python, Java, Ruby, and others are commonly used for server-side processing.

○ **Data Storage**: Server-side processing enables secure storage and management of sensitive data in databases or other storage systems.

---
# Components

![[we_components.png]]

## Client-Side Technologies

- **HTML** (Hypertext Markup Language)
- **CSS** (Cascading Style Sheets)
- **JavaScript** -  used to create dynamic and responsive UI elements, handle user interactions, and perform client-side validations.
- **Cookies and Local Storage** - often used for session management and remembering user preferences.

## Server-Side Technologies

- **Web Server** - (Apache2, Nginx, Microsoft IIS etc)
- **Application Server** - The application server runs the business logic of the web application. It processes user requests, accesses databases, and performs computations to generate dynamic content that the web server can serve to clients.
- **Database Server** - (MySQL, PostgreSQL, MSSQL, Oracle etc)
- **Server-side Scripting Languages** - (e.g., PHP, Python, Java, Ruby) are used to handle server-side processing. They interact with databases, perform validations, and generate dynamic content before sending it to the client.





#### Definitions

***Data interchange*** : It refers to the process of exchanging data between different computer systems or applications, allowing them to communicate and share information.
					- *Data interchange involves the conversion of data from one format to another, making it compatible with the receiving system*.
					- *This ensures that data can be interpreted and utilized correctly by the recipient, regardless of the differences in their data structures, programming languages, or operating systems.*