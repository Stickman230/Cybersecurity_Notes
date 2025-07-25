#Authentication #Enumeration #WEB #WebAuthentication
# Inducing Verbose Errors

1. **Invalid Login Attempts**: intentionally entering incorrect usernames or passwords, attackers can trigger error messages that help distinguish between valid and invalid usernames.
- Entering a username that doesn’t exist might trigger a different error message than entering one that does, revealing which usernames are active.

1. **SQL Injection**: slipping malicious #SQL commands into entry fields
 - placing a single quote ( `'`) in a login field might cause the database to throw an error, inadvertently exposing details about its schema.

1. **File Inclusion/Path Traversal**: By manipulating file paths, attackers can attempt to access restricted files, coaxing the system into errors that reveal internal paths. 
- Using directory traversal sequences like `../../` could lead to errors that disclose restricted file paths.

1. **Form Manipulation**: Tweaking form fields or parameters can trick the application into displaying errors that disclose backend logic or sensitive user information. 
- Altering hidden form fields to trigger validation errors might reveal insights into the expected data format or structure.

1. **Application Fuzzing**: Sending unexpected inputs to various parts of the application to see how it reacts can help identify weak points
- eg. Burp Suite Intruder 

[[(3) Enumeration & Brute Force - Password Reset Exploitation|Next we can exploit vulnerable password reset mechanisms]]