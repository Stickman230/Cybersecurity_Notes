#Authentication #Enumeration #WEB #WebAuthentication
# Authentication Enumeration

Authentication enumeration is like peeling back the layers of an onion. You *remove each layer of a system's security to reveal the real operations* underneath. 

## Identifying Valid Usernames

Observing how the application responds during login or password resets. 
- An error messages that specify "this account doesn't exist" or "incorrect password" can hint at valid usernames, making an attacker's job easier.

## Password Policies

Understanding these policies,  can gauge the potential complexity of the passwords and tailor their strategy accordingly.
- The below PHP code uses regex to require a password that includes symbols, numbers, and uppercase letters:

```php
<?php
  echo "Password is invalid. It must contain at least one uppercase letter, one number, and one symbol.";
?>
```

The application will return an error message revealing the regex code requirement. An attacker might generate a dictionary that satisfies this policy.

---
# Common Places to Enumerate

## Registration Pages

 If a registration attempt results in a message stating that a username or email is already taken, the application is unwittingly confirming its existence to anyone trying to register. 
 - Testing potential usernames or emails,
 - Compiling a list of active users without needing direct access to the underlying database.

## Password Reset Features

 Differences in the application's response can unintentionally reveal sensitive information. For example, variations in an application's feedback about whether a username exists can help attackers verify user identities. 
 - refine their lists of valid usernames, 
 - substantially improving the effectiveness of subsequent attacks.
[[(3) Enumeration & Brute Force - Password Reset Exploitation|See password reset exploitation]]

## Verbose Errors

 These messages differentiate between "username not found" and "incorrect password"
 - Definitive clues about valid usernames, which can be exploited for more targeted attacks.
[[(2) Enumeration & Brute Force - Verbose Errors|See verbose errors for User Enumeration]]

## Data Breach Information

Data from previous security breaches is a goldmine for attackers as it allows them to test whether compromised usernames and passwords are reused across different platforms. 
- Exploit username is reused but also potential password recycling

# HTTP Authentication Header 

- HTTP Basic Authentication is defined in [RFC 7617](https://datatracker.ietf.org/doc/html/rfc7617).
- It specifies that the credentials (username and password) should be transported as a base64-encoded string within the HTTP Authorization header.

This method is straightforward but not secure over non-HTTPS connections, as base64 is not an encryption method and can be easily decoded. The real threat often comes from **weak credentials that can be brute-forced.**