# Reading 09 — Authorization/Authentication

## Readings

### Today's Lab Requirements

The lab focuses on combining concepts from our previous API and authentication work into a small project.

The project should be manageable within approximately one lab session and completed with a partner.

The main concepts involved include:

- Express servers
- REST APIs
- Data models
- CRUD operations
- Authentication
- Authorization
- Routes
- Middleware
- Testing
- Working collaboratively with Git and GitHub

---

## Two Possible Project Ideas

### 1. Movie Database

A small movie database application where users can create an account and keep track of movies.

A movie could contain:

```javascript
{
  title: 'Alien',
  genre: 'Science Fiction',
  year: 1979
}
```

Possible features:

- Sign up and sign in
- Browse movies
- Add movies
- Update movie information
- Delete movies
- Protect certain routes with authentication
- Give different users different permissions

Example authorization:

```text
User
├── Read movies
└── Add movies

Editor
├── Read movies
├── Add movies
└── Update movies

Admin
├── Read movies
├── Add movies
├── Update movies
└── Delete movies
```

This would be a good project because it uses CRUD, authentication, authorization, and database concepts we have already practiced.

---

### 2. Small Business Product Inventory

A small API for a business that sells four or five products.

A product could contain:

```javascript
{
  name: 'Product Name',
  description: 'Product description',
  price: 20,
  quantity: 5
}
```

Possible features:

- Customers can view products
- Employees can add or update products
- Administrators can delete products
- Users can create accounts and sign in
- Protected routes can require a valid JWT
- Roles can determine which CRUD operations are allowed

Example authorization:

```text
Customer → Read

Employee → Read + Create + Update

Admin → Read + Create + Update + Delete
```

This would provide a simple way to practice RBAC while keeping the database small.

---

# API Server Review

An **API server** provides routes that allow a client to communicate with application data.

A REST API commonly uses:

| HTTP Method | Purpose |
| --- | --- |
| `GET` | Read data |
| `POST` | Create data |
| `PUT` | Update data |
| `DELETE` | Delete data |

Example:

```text
GET    /movies
GET    /movies/:id
POST   /movies
PUT    /movies/:id
DELETE /movies/:id
```

The general request flow is:

```text
Client Request
      ↓
Express Route
      ↓
Middleware
      ↓
Model / Database
      ↓
Response
```

The API server separates the application's data and server logic from the frontend.

---

# Auth Server Review

An **authentication server** determines who a user is and can help determine what that user is allowed to do.

The general process is:

```text
User
 ↓
Sign Up / Sign In
 ↓
Authentication
 ↓
JWT Token
 ↓
Protected Route
 ↓
Authorization
 ↓
Allow or Deny Access
```

## Authentication

Authentication answers:

> **Who are you?**

Examples include:

- Username and password
- Basic Authentication
- Bearer tokens
- JWTs

After successful authentication, the server can issue a token that represents the authenticated user.

---

## Authorization

Authorization answers:

> **What are you allowed to do?**

After authentication, the application can check the user's role or capabilities before allowing access to a protected route.

For example:

```text
User → authenticated
          ↓
       Role: editor
          ↓
Capabilities:
read, create, update
          ↓
DELETE request
          ↓
DENIED
```

Authentication and authorization work together, but they solve different problems.

---

## Authentication vs. Authorization

| Authentication | Authorization |
| --- | --- |
| Confirms identity | Controls permissions |
| "Who are you?" | "What can you do?" |
| Happens first | Happens after authentication |
| Can use passwords or tokens | Can use roles and capabilities |

---

# Reflection

## What Are My Learning Goals?

After reviewing the class material, my learning goals are to:

- Better understand how authentication and authorization work together
- Understand how JWTs are used to access protected routes
- Practice creating protected Express routes
- Understand how roles and capabilities control access
- Connect authentication middleware with authorization middleware
- Apply CRUD operations to authenticated users
- Understand how API servers and authentication servers work together
- Practice assigning roles appropriately when working with different types of users
- Write tests that confirm users can only access routes they have permission to use
- Practice combining concepts from previous labs into one application
- Improve working with a partner using Git branches, commits, and pull requests

---

## Things I Want to Know More About

### How should roles be assigned?

Roles should be based on what a user needs to accomplish rather than simply giving everyone the highest level of access.

```text
User → Basic access
Editor → Content management
Admin → System management
```

This follows the **principle of least privilege**, where users receive only the permissions necessary to perform their responsibilities.

### How do JWTs work with authorization?

A JWT can identify an authenticated user and may contain information that helps the server determine their role or capabilities.

The server verifies the token before trusting its claims.

```text
JWT
 ↓
Verify Token
 ↓
Identify User
 ↓
Check Role / Capability
 ↓
Allow or Deny
```

### How do we test authorization?

Tests should check both successful and unsuccessful access.

For example:

```text
User tries GET    → Allowed
User tries DELETE → Denied
Admin tries DELETE → Allowed
No token          → Denied
Invalid token     → Denied
```

Testing denied requests is especially important because authorization is responsible for preventing users from accessing functionality they should not have.

---

## Resources

- [Class 09 Lab Requirements](https://codefellows.github.io/code-401-javascript-guide/curriculum/class-09/lab/)
- [API Server Build Review](https://codefellows.github.io/code-401-javascript-guide/curriculum/apps-and-libraries/api-server/)
- [Auth Server Build Review](https://codefellows.github.io/code-401-javascript-guide/curriculum/apps-and-libraries/auth-server/)