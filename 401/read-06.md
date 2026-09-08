# Readings: Authentication

## Securing Passwords

### Explain to a non-technical friend how you would safely hash and store a password

I would never store the original password in the database. Instead, I would use a password-hashing algorithm to transform it into a value called a **hash**.

A unique random value called a **salt** is added during hashing. The application stores the resulting hash, not the original password.

When the user signs in:

1. The user enters a password.
2. The application compares it with the stored hash using the hashing library.
3. If they match, the password is accepted.

Hashing is one-way. The application can verify the password without retrieving the original password. Passwords should also be transmitted using HTTPS.

### What is bcrypt?

**bcrypt** is a password-hashing algorithm designed to securely store passwords. It works with a salt and uses a configurable **work factor**, which controls how computationally expensive the hashing process is.

Unlike fast general-purpose hashing algorithms, bcrypt is intentionally slow. This makes it more expensive for an attacker to repeatedly guess passwords.

### Why might you use something like bcrypt?

You might use bcrypt because it:

- Does not store the original password.
- Uses a unique salt when hashing each password.
- Produces different hashes for identical passwords when different salts are used.
- Slows down brute-force password guessing.
- Has an adjustable work factor.
- Provides methods for hashing and comparing passwords.

> **Security note:** OWASP currently prefers Argon2id for new applications. Bcrypt is still commonly used in existing applications and coursework.

---

## Basic Authentication

### What is Basic Authentication?

**Basic Authentication** is an HTTP authentication method in which a client sends a username and password in the request's `Authorization` header.

The credentials are normally sent with every protected request.

### What properties are necessary in the header of a Basic Auth request?

A Basic Authentication request requires:

- The header name: `Authorization`
- The authentication scheme: `Basic`
- A space after `Basic`
- The Base64-encoded credentials

```http
Authorization: Basic <encoded-credentials>
```

### How are `username:password` encoded?

The username and password are joined together in a string with a colon:

```text
username:password
```

The complete string is then encoded using Base64:

```text
Base64(username:password)
```

Base64 is an encoding format. It is **not encryption or hashing**. Anyone who obtains the value can decode it, so Basic Authentication should only be used over HTTPS.

---

## OWASP Authentication Cheat Sheet

### Define the authentication process for a non-technical recruiter

Authentication is the process of confirming that a person or system is who they claim to be.

It is similar to checking someone's identification before allowing them into a restricted building. A website might verify identity using a password, security token, fingerprint, or another credential.

Authentication answers:

> Who are you, and can you prove it?

Authentication is different from authorization:

- **Authentication** verifies identity.
- **Authorization** determines what the verified user permissions are

### How should error messaging respond in both HTTP and HTML? Why?

Authentication failures should return a **generic and consistent response** in both the HTTP response and the displayed HTML.

An appropriate message is:

```text
Invalid username or password.
```

The application should not reveal whether:

- The username exists.
- Only the password was incorrect.
- The account is locked.
- The account is disabled.

HTTP status behavior should also remain consistent for equivalent failed login attempts.

- `401 Unauthorized` normally means authentication is missing or unsuccessful.
- `403 Forbidden` normally means the user is authenticated but does not have permission.

Detailed error messages could help attackers discover valid accounts through **user enumeration**. Response timing should also remain similar so attackers cannot determine whether an account exists by measuring how long the response takes.

---

## Key Terms

| Term | Meaning |
|---|---|
| Authentication | Verifies who a user is |
| Authorization | Determines what a user may access |
| Hash | A one-way result produced from an input |
| Salt | A unique random value added before hashing |
| Work factor | Controls how computationally expensive hashing is |
| Base64 | An encoding format, not encryption |
| Brute-force attack | Repeatedly guessing passwords until one works |
| User enumeration | Discovering whether particular user accounts exist |

---

## Bookmark and Review

- [Securing Passwords with bcrypt](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)
- [Basic Access Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)
- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
- [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
- [bcrypt Documentation](https://www.npmjs.com/package/bcrypt)