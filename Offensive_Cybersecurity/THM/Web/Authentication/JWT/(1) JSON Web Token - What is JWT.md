#JWT #WEB #WebAuthentication

# What are JWT ?

JWTs are *self-contained tokens* that can be used to securely transmit session information. It is an [open standard](https://tools.ietf.org/html/rfc7519), providing information for any developer or library creator who wants to use JWTs. 

They are passed through the `Authorization: Bearer` header. However, as we are not using the browser's built-in cookie management features, there are standards but nothing is forcing anyone from sticking to these standards. Tokens like JWTs are a way to *standardise token-based session management*.

## JWT Structure

**3 components, each Base64Url encoded and separated by dots**:

- **Header** - The header usually indicates the type of token, which is JWT, as well as the signing algorithm that is used.

- **Payload** - The body of the token, which contain the claims. 
	- A claim is a piece of information provided for a specific entity. 
	- In JWTs, there are registered claims, which are claims predefined by the JWT standard and public or private claims. The public and private claims are those which are defined by the developer.0
	*It is worth knowing the difference between public and private claims*.

- **Signature** - The signature is the part of the token that provides a method for verifying the token's authenticity. The signature is created by using the algorithm specified in the header of the JWT

## Signing Algorithms

*3 Main Algorithms standard for JWT signature.*

- **None** - The None algorithm means no algorithm is used for the signature.

- **Symmetric Signing** - A symmetric signing algorithm, *such as HS256*, creates the signature by appending a secret value to the header and body of the JWT before generating a hash value. Verification of the signature can be performed by any system that has knowledge of the secret key.

- **Asymmetric Signing** - An asymmetric signing algorithm, *such as RS256*, creates the signature by using a private key to sign the header and body of the JWT. This is created by generating the hash and then encrypting the hash using the private key. Verification of the signature can be performed by any system that has knowledge of the public key associated with the private key that was used to create the signature.

---

[[(2) JSON Web Token - Detection & Exploitation|See JWT Detection & Exploitation]]