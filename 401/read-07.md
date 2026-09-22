# Reading 07 — Bearer Authorization

## Introduction to JWT

### What is a JSON Web Token?

A JSON Web Token, or JWT, is a compact and URL-safe way to transfer information between two parties as a JSON object.

JWTs are commonly used to represent a user's identity and permissions after the user successfully signs in.

A JWT is pronounced **“jot.”**

### When should we use JSON Web Tokens?

JWTs are commonly used for:

* Authentication
* Authorization
* Sharing verified information between systems
* Protecting API routes
* Maintaining a user's signed-in state without storing a traditional server session

After a user signs in, the server can create a JWT and send it to the client. The client sends that token with later requests to protected routes.

A bearer token is commonly sent through the request header:

```text
Authorization: Bearer <token>
```

Anyone possessing a valid bearer token may be able to use it, so tokens must be protected.

### Where are claims stored?

Claims are stored in the **payload**, which is the second section of a JWT.

Claims are pieces of information about the subject of the token. Examples include:

* User ID
* Username
* Role
* Permissions
* Issued time
* Expiration time

Sensitive information such as passwords should not be placed in the payload.

---

## JWT Structure

A standard signed JWT contains three sections separated by periods:

```text
header.payload.signature
```

Example:

```text
xxxxx.yyyyy.zzzzz
```

### 1. Header

The header normally identifies:

* The token type
* The signing algorithm

Example:

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

### 2. Payload

The payload contains the claims.

Example:

```json
{
  "sub": "1234567890",
  "username": "agiv",
  "role": "user"
}
```

### 3. Signature

The signature allows the receiving server to verify that the header and payload have not been changed.

With an HMAC algorithm, the signature is created using:

```text
encoded header
+
encoded payload
+
secret
```

The result is approximately:

```text
HMACSHA256(
  base64UrlEncode(header) + "." + base64UrlEncode(payload),
  secret
)
```

---

## Are JWTs Secure?

### If the payload can be decoded, how is a JWT secure?

A standard signed JWT payload is encoded, not encrypted. Anyone who obtains the token may be able to decode and read its payload.

The security comes from the signature. Someone without the signing secret or private key cannot change the contents and produce a valid signature.

If an attacker changes the payload, the signature verification should fail.

For this reason:

* Do not store passwords in a JWT.
* Do not store private or highly sensitive information in an unencrypted JWT.
* Always verify the signature before trusting the payload.
* Send tokens over HTTPS.
* Give tokens an expiration time.

### What must the sender and receiver both know?

When using a symmetric algorithm such as HMAC, the sender and receiver must both know the same secret used to create and verify the signature.

With an asymmetric algorithm, the sender signs with a private key and the receiver verifies with the corresponding public key. They do not share the private key.

### Non-technical explanation

Imagine placing a readable note inside a clear container and sealing it with a special tamper-evident seal.

Anyone holding the container can read the note, but they cannot change it and reproduce the valid seal without the secret used to create it.

When the receiver gets the container, they check the seal. If the contents were changed, the seal no longer matches, and the receiver rejects it.

The JWT payload is the readable note, and the signature is the tamper-evident seal.

---

## Why Use JWT?

JWTs are useful because they are:

* **Compact:** They are small enough to send in an HTTP request header.
* **Self-contained:** The token can contain the claims needed to identify the user and determine allowed actions.
* **Portable:** They can be passed between different applications and services.
* **Verifiable:** The signature lets a server detect unauthorized changes.
* **Stateless:** A server may verify the token without maintaining a traditional session for every user.

### Compact and self-contained explained simply

A JWT works like a compact digital identification card.

The card contains useful information about its owner, such as an ID or role. Because the important information travels with the card, another authorized service can inspect and verify it without repeatedly asking the original system for basic details.

Self-contained does not mean that every piece of user information should be stored in the token. Tokens should remain small and contain only necessary claims.

---

## Using the `jsonwebtoken` Package

Install the package:

```bash
npm install jsonwebtoken
```

Import it with CommonJS:

```javascript
const jwt = require('jsonwebtoken');
```

Create a signed token:

```javascript
const token = jwt.sign(
  { username: 'agiv' },
  process.env.SECRET,
  { expiresIn: '1h' }
);
```

Verify a token:

```javascript
const decodedToken = jwt.verify(
  token,
  process.env.SECRET
);
```

`jwt.verify()` checks the signature before returning the decoded payload.

Simply decoding a JWT does not prove that the token is authentic.

---

## Key Takeaways

* JWT stands for JSON Web Token.
* A JWT commonly supports authentication and authorization.
* A JWT contains a header, payload, and signature.
* Claims are stored in the payload.
* The payload is normally readable because encoding is not encryption.
* The signature detects changes to the header or payload.
* A bearer token is commonly sent in the `Authorization` header.
* JWT signatures must be verified before their claims are trusted.
* Passwords and other sensitive information should not be stored in a normal JWT payload.


* [npm `jsonwebtoken` documentation](https://www.npmjs.com/package/jsonwebtoken)
