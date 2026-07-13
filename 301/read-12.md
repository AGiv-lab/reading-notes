# CRUD Reading Notes

## HTTP Status Codes

### 100's – Informational
- Request received
- Server is still processing

### 200's – Success
- Request was successful
- Data was sent or updated correctly

### 300's – Redirection
- Client needs to take another action
- Usually redirects to another URL

### 400's – Client Error
- Problem with the request sent by the client
- Example: bad request, unauthorized, not found

### 500's – Server Error
- Problem on the server
- Client did nothing wrong

---

## Common Status Codes

### 202 Accepted
- Request was accepted
- Processing will happen later
- Not finished yet

### 308 Permanent Redirect
- Resource has permanently moved
- Client should use the new URL

### Update with No Data Returned
- **204 No Content**
- Update succeeded, but nothing is returned

### Resource No Longer Exists
- **410 Gone**
- Resource existed before but has been permanently removed

### Forbidden Status Code
- **403 Forbidden**
- Server understands the request but refuses access

---

# Video Notes (First 20 Minutes)

## 1. Why put the MongoDB connection string in `.env`?

- Keeps sensitive information private
- Prevents passwords from being pushed to GitHub
- Makes it easy to change environments (development vs production)

---

## 2. What is middleware?

Middleware is code that runs **between the request and the response**.

It can:
- Read requests
- Modify requests
- Validate data
- Log information
- Handle errors

---

## 3. What does `app.use(express.json())` do?

- Reads JSON data sent by the client
- Converts it into a JavaScript object
- Stores it in `req.body`

Without it, `req.body` will be empty.

---

## 4. What does `/:id` mean in a route?

It is a **route parameter**.

Example:

```js
GET /users/:id
```

If the URL is:

```text
/users/123
```

Then:

```js
req.params.id
```

equals:

```text
123
```

---

## 5. Difference between `PUT` and `PATCH`

### PUT
- Replaces the entire resource
- Send all fields

### PATCH
- Updates only specific fields
- Send only what changes

---

## 6. How do you make a default value in a schema?

Use the `default` property.

Example:

```js
const userSchema = new mongoose.Schema({
  active: {
    type: Boolean,
    default: true
  }
});
```

If no value is provided, `active` becomes `true`.

---

## 7. What does a `500` status code mean?

- Internal Server Error
- Something went wrong on the server
- Usually caused by a bug or database problem

---

## 8. Difference between `200` and `201`

### 200 OK
- Request succeeded
- Used for GET, PUT, PATCH, DELETE

### 201 Created
- A new resource was successfully created
- Commonly used after a POST request

---

# Quick CRUD Status Code Cheat Sheet

| CRUD Operation | HTTP Method | Common Status Code |
|---------------|------------|--------------------|
| Create | POST | **201 Created** |
| Read | GET | **200 OK** |
| Update | PUT / PATCH | **200 OK** or **204 No Content** |
| Delete | DELETE | **204 No Content** |

---

# Common HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | OK |
| 201 | Created |
| 202 | Accepted |
| 204 | No Content |
| 301 | Moved Permanently |
| 308 | Permanent Redirect |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 410 | Gone |
| 500 | Internal Server Error |
```