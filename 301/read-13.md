[# 📚 CRUD - Class Notes

## Reading: CRUD Basics

### 1. Which HTTP method would you use to update a record through an API?

- **PUT** → Replace the entire resource.
- **PATCH** → Update only specific fields.

> Both are used for updating data.

---

### 2. Which REST methods require an ID parameter?

Methods that work with a **specific resource** usually require an ID.

| HTTP Method | ID Required? | Example |
|-------------|:------------:|---------|
| GET (all) | ❌ | `/books` |
| GET (one) | ✅ | `/books/:id` |
| POST | ❌ | `/books` |
| PUT | ✅ | `/books/:id` |
| PATCH | ✅ | `/books/:id` |
| DELETE | ✅ | `/books/:id` |

---

# Video Notes: Speed Coding - Building a CRUD API

## 1. What's the relationship between REST and CRUD?

- **CRUD** describes the **actions** you perform on data.
- **REST** is a way to organize an API that uses HTTP methods to perform those actions.

### CRUD → REST Mapping

| CRUD | HTTP Method |
|------|-------------|
| Create | POST |
| Read | GET |
| Update | PUT / PATCH |
| Delete | DELETE |

> **Easy to remember:** CRUD = *what* you want to do. REST = *how* you do it over HTTP.

---

## 2. Creating a RESTful API in 5 Steps

### 1. Create the Server
- Set up Express.
- Connect to the database.

### 2. Create a Model
- Define the data structure (schema).
- Example: `Book`, `User`, or `Product`.

### 3. Create Routes
- Add API endpoints.
- Example:
  - `GET /books`
  - `POST /books`
  - `PATCH /books/:id`
  - `DELETE /books/:id`

### 4. Write CRUD Logic
- Read from the database.
- Create new records.
- Update existing records.
- Delete records.

### 5. Test the API
- Use Postman, REST Client, or the frontend.
- Verify requests return the correct data and status codes.

---

# RESTful API Workflow

```text
Client (React)
      │
      ▼
HTTP Request
(GET, POST, PUT, PATCH, DELETE)
      │
      ▼
Express Route
      │
      ▼
Controller / Route Handler
      │
      ▼
MongoDB (Mongoose)
      │
      ▼
Database
      │
      ▼
HTTP Response
(Status Code + JSON)
      │
      ▼
Client (React)
```

---

# Key Takeaways

- **PUT** and **PATCH** update data.
- Routes that target one item usually use an **ID**.
- **CRUD** defines the database operations.
- **REST** maps those operations to HTTP methods.
- A RESTful API follows a predictable structure, making it easier to build, test, and maintain.

---

# Quick Reference

| CRUD | HTTP Method | Route |
|------|-------------|-------|
| Create | POST | `/books` |
| Read All | GET | `/books` |
| Read One | GET | `/books/:id` |
| Update | PUT / PATCH | `/books/:id` |
| Delete | DELETE | `/books/:id` |

---

  

](read-13.md)# 📚 More CRUD (Create, Read, Update, Delete) - Class Notes

## What is CRUD?

CRUD represents the **four basic operations** performed on data in nearly every web application.

| Letter | Meaning | HTTP Method | Example |
|--------|---------|------------|---------|
| C | Create | POST | Add a new user or book |
| R | Read | GET | View users or books |
| U | Update | PUT / PATCH | Edit user information |
| D | Delete | DELETE | Remove a user or book |

> **Remember:** If an app stores data, it almost certainly uses CRUD.

---

# Why CRUD Matters

CRUD is the foundation of most web applications because users need to:

- Create new information
- View existing information
- Update incorrect or outdated information
- Delete information they no longer need

Without CRUD, applications couldn't manage data effectively.

---

# Real-World Examples

## 🛒 E-Commerce (Amazon)

| CRUD | Example |
|------|---------|
| Create | Create an account, place an order |
| Read | Browse products, view order history |
| Update | Change shipping address, edit cart |
| Delete | Remove item from cart |

---

## 🏦 Banking

| CRUD | Example |
|------|---------|
| Create | Open a bank account |
| Read | Check account balance |
| Update | Change contact information |
| Delete | Cancel a scheduled payment |

---

## 📚 Library System

| CRUD | Example |
|------|---------|
| Create | Add a new book |
| Read | Search for books |
| Update | Edit book information |
| Delete | Remove damaged books |

---

## 🎵 Spotify

| CRUD | Example |
|------|---------|
| Create | Create a playlist |
| Read | Browse artists and songs |
| Update | Rename a playlist |
| Delete | Delete a playlist |

---

## 💬 Social Media

| CRUD | Example |
|------|---------|
| Create | Create a post |
| Read | View posts and comments |
| Update | Edit a post |
| Delete | Delete a post |

---

# CRUD in Web Development

As a developer, you'll build CRUD features regularly.

Common examples:

- User accounts
- Products
- Books
- Blog posts
- Orders
- Employees
- Events
- Messages
- Comments

---

# CRUD in REST APIs

| CRUD | HTTP Method | Typical Route |
|------|------------|---------------|
| Create | POST | `/books` |
| Read | GET | `/books` |
| Read One | GET | `/books/:id` |
| Update | PUT / PATCH | `/books/:id` |
| Delete | DELETE | `/books/:id` |

---

# CRUD in MongoDB

| CRUD | Mongoose Example |
|------|------------------|
| Create | `Book.create()` |
| Read | `Book.find()` |
| Read One | `Book.findById()` |
| Update | `Book.findByIdAndUpdate()` |
| Delete | `Book.findByIdAndDelete()` |

---

# CRUD in Express

```js
// Create
app.post('/books')

// Read all
app.get('/books')

// Read one
app.get('/books/:id')

// Update
app.put('/books/:id')

// Delete
app.delete('/books/:id')
```

---

# CRUD in Code Fellows Projects

## 🌤️ City Explorer

- Read weather data
- Read movie data

This project mainly uses **GET** requests.

---

## 📖 Can of Books

- Create a book
- Read books
- Update book information
- Delete a book

This is a full **CRUD application**.

---

# Common HTTP Status Codes Used with CRUD

| Code | Meaning | Used For |
|------|---------|----------|
| 200 | OK | Successful GET or UPDATE |
| 201 | Created | Successful POST |
| 204 | No Content | Successful UPDATE or DELETE with no data returned |
| 400 | Bad Request | Invalid client request |
| 403 | Forbidden | Client does not have permission |
| 404 | Not Found | Resource doesn't exist |
| 410 | Gone | Resource existed but was permanently removed |
| 500 | Internal Server Error | Server problem |

---

# Quick Memory Trick

CRUD is similar to managing sticky notes on a bulletin board:

- ➕ **Create** → Add a new note
- 👀 **Read** → Look at the notes
- ✏️ **Update** → Edit a note
- 🗑️ **Delete** → Throw away a note

---

# Key Takeaways

- CRUD = **Create, Read, Update, Delete**
- CRUD is the backbone of most web applications.
- REST APIs map CRUD operations to HTTP methods.
- MongoDB and Mongoose provide methods for each CRUD operation.
- Express routes handle CRUD requests from the frontend.
- You'll use CRUD in nearly every full-stack application you build.
```