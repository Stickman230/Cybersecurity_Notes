#eJPT #WEB #INE 

# How does a web application work ?

**● This Client-Server Architecture**
**● User Interface (UI)**
**● Internet Connectivity**
**●Cross-Platform Compatibility**
**●Statelessness:** HTTP, the protocol used for communication between web browsers and servers, is stateless. Web applications must manage user sessions and state to remember user interactions and ensure continuity.

*Users interact with the application by sending  requests to the server, which processes those requests and sends back the appropriate responses.*

The primary objective of web application security is to ensure the ***Confidentiality, integrity, and availability*** of data processed by web applications while mitigating the risk of unauthorized access, data breaches, and service disruptions.

Web app is a good target because = gain of  personal information, financial data, or intellectual property.

---
# Web Application Security Practices

● **Authentication and Authorization**
● **Input Validation** = prevent common attacks like SQL injection and cross-site scripting (XSS).
● **Secure Communication**: Using encryption protocols like HTTPS (TLS/SSL) 
● **Secure Coding Practices**
● **Least Privilege Principle**
● **Web Application Firewalls (WAF)**: Implementing a WAF to filter and monitor HTTP requests, blocking malicious traffic and protecting against known attack patterns.
● **Session Management**

### Threat vs Risk

| Risk                                                                                                                                                                                                                                                                                                                                                                                                         | Threat                                                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <br>○ Risk is the potential for a loss or harm resulting from a threat exploiting a vulnerability in a system or organization.<br><br>○ It is a combination of the likelihood or probability of a threat occurrence and the impact or severity of the resulting adverse event.<br><br>○ Risk is often measured in terms of the likelihood of an incident happening and the potential magnitude of its impact | <br>○ A threat refers to any potential source of harm or adverse event that may exploit a vulnerability in a system or organization's security measures.<br><br>○ Threats can be human-made, such as cybercriminals, hackers, or insiders with malicious intent, or they can be natural, such as floods, earthquakes, or power outages.<br> |
|                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                             

---
# Common Threats and Risk

![[common_threats1.png]]
![[common_threats2.png]]

To address these challenges, organizations should adopt a **multi-layered security approach**, including secure coding practices, regular security testing, user education on security best practices, and the continuous monitoring and updating of web application components and infrastructure.

---
# Web Application Security Testing

*Web application security testing is the process of evaluating and assessing the security aspects of web applications to identify vulnerabilities, weaknesses, and potential security risks.*

- conducting various tests and assessments to ensure that web applications are resistant to security threats and can effectively protect sensitive data and functionalities from unauthorized access or malicious activities.

### Types of Web Application Security Testing

| Name                                             | Explaination                                                                                                                                                                                                      |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Vulnerability Scanning**                       | Using automated tools to scan the web application for known vulnerabilities, such as SQL injection, Cross-Site Scripting (XSS), insecure configurations, and outdated software versions.                          |
| **Penetration Testing**                          | Simulating real-world attacks to assess the application's defenses and identify potential security weaknesses. This involves ethical hacking to gain insights into how an attacker might exploit vulnerabilities. |
| **Code Review and Static Analysis**              | Manual examination of the application's source code to identify coding flaws, security misconfigurations, and potential security risks.                                                                           |
| **Authentication and Authorization Testing**     | Evaluating the effectiveness of authentication mechanisms and access control features to ensure that only authorized users have appropriate access levels.                                                        |
| **Input Validation and Output Encoding Testing** | Assessing how the application handles user inputs to prevent common security vulnerabilities like XSS and SQL injection.                                                                                          |
| **Session Management Testing**                   | Verifying how the application manages user sessions and related tokens to prevent session-related attacks.                                                                                                        |
| **API Security Testing**                         | Assessing the security of APIs (Application Programming Interfaces) used by the web application for data exchange and integration with other systems.                                                             |
