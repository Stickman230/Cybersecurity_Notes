#MFA #WEB #WebAuthentication

# What is MFA ?

**Multi-Factor Authentication (MFA)** plays an important role in modern-day applications. Instead of just relying on a password, MFA throws in extra layers of defense. MFA is a combination of different checks:
- *Something you know* 
- *Something you have* 
- *Something you are* 
By using these layers, MFA makes it much tougher for threat actors to access user accounts or applications.

---
# Types of Authentication Factors

MFA typically combines two or more different kinds of credentials from the categories

**Something You Know**
 - A password, a PIN, or any other piece of info you have to remember. 

**Something You Have**
 -  A phone with an authentication app, a security token, or even a smart card. Lately, we’re seeing more use of client certificates

**Something You Are**
-  Biometrics, such as fingerprints, facial recognition, or iris scans. 
- It's important to note that a fingerprint never matches 100%, and a face scan never matches 100%. So this is the one factor that should always be supplemental and never used in pure isolation.

**Somewhere You Are**
-  Origin IP address or geolocation. 

**Something You Do**
- The application typically analyses the way the user types the credentials or moves their mouse, and this is also the most difficult to implement since the application requires a specific amount of processing power.

*2FA specifically requires exactly two of these factors*. So, while all 2FA is MFA, not all MFA is 2FA. .

---
# Conditional Access

Conditional access is typically used by companies to adjust the authentication requirements based on different contexts. It's like a decision tree that triggers extra security checks depending on certain conditions. For example:

**Location-Based**
- If a user is logging in from a new or unfamiliar location, the system could ask for an additional OTP or even biometric verification.

**Time-Based**
-  if someone tries to access the system after working hours, they might be prompted for an extra layer of security, like an OTP or a security token.

**Behavioral Analysis**
- Suppose a user's behavior suddenly changes, like they began accessing data they don't usually view or access at odd hours. In that case, the system can ask for additional authentication to confirm it’s really them.  

**Device-Specific**
- In some cases, companies don’t allow employees to use their own devices to access corporate resources. In these situations, the system might block the user after the initial login step if they’re on an unapproved device.

---
[[(2) Multi-Factor Authentication - Detection & Exploitation|See MFA Detection & Exploitation]]