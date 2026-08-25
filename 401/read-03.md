# Reading 03: Express REST API

## Review: ES6 Classes

### 1. Classes are a template for creating what?

Classes are templates for creating **objects**.

**Analogy:** A class is like a blueprint for a house. The blueprint defines the structure, while each house built from it is a separate object.

---

### 2. Can a class declaration be hoisted?

No. A class declaration cannot be used before it is declared.

**Analogy:** You need the blueprint before you can build the house.

---

### 3. How would you describe a constructor and contextual `this`?

A **constructor** is a special method that runs when a new object is created. It gives the object its starting properties.

`this` refers to the specific object currently being created or used.

### Example

```js
class Dog {
  constructor(name) {
    this.name = name;
  }
}

const dog = new Dog('Buddy');
```

**Analogy:** The constructor is like filling out an ID card for a new object. `this` means **this particular object**.

---

## Using Express Routing

### 1. Within Express, what does routing refer to?

Routing determines how an Express server responds to a client request at a particular endpoint.

### Example

```js
app.get('/books', handler);
```

Here, Express receives a `GET` request for `/books` and sends it to the appropriate handler.

**Analogy:** Routing is like a receptionist directing a visitor to the correct department.

---

### 2. What is the difference between a route path and a route method?

A **route path** identifies where the request is going.

Example:

```text
/books
```

A **route method** identifies what type of action the client wants to perform.

- `GET` → Read
- `POST` → Create
- `PUT` → Update
- `DELETE` → Delete

### Example

```js
app.get('/books', handler);
```

- `get` = route method
- `/books` = route path

**Analogy:** The route path is the **address**, while the route method is the **instruction for what you want to do when you arrive**.

---

### 3. When is it appropriate to add `next` as a parameter to a route handler?

Use `next` when the request needs to continue to another middleware function or route handler.

If middleware receives `next` and does not send the final response, it should call:

```js
next();
```

### Example

```js
function logger(req, res, next) {
  console.log('Request received');
  next();
}
```

**Analogy:** Middleware is like a series of checkpoints. Calling `next()` means **"this checkpoint is complete; continue to the next one."**

**Request → Middleware → Next Middleware/Handler → Response**

---

## Express Router

### 1. What is an Express Router?

An **Express Router** organizes related routes into smaller, manageable groups instead of putting every route in one file.

For example, a router for books could organize:

- `GET /books`
- `POST /books`
- `PUT /books/:id`
- `DELETE /books/:id`

**Analogy:** Think of the Express application as a **filing cabinet**. A Router is a folder inside the cabinet that keeps related files together.

---

### 2. By what means do we initialize `express.Router()` in an Express server?

We initialize an Express Router by calling:

```js
const router = express.Router();
```

Routes can then be added to the router:

```js
router.get('/books', (req, res) => {
  res.send('Here are the books');
});
```

The router can be connected to the main Express application using `app.use()`.

### Example

```js
app.use('/books', router);
```

**Analogy:** Creating `express.Router()` is like creating a **new folder** before putting related files inside it.

---

### 3. What do we use route middleware for?

**Route middleware** performs work during the request-response process before the final route handler responds.

Middleware can be used for:

- Logging requests
- Validating data
- Authentication
- Modifying requests or responses
- Handling errors

Middleware receives `req`, `res`, and `next`. If it does not end the request-response cycle, it should call `next()` so processing can continue.

### Example

```js
function logger(req, res, next) {
  console.log('Request received');
  next();
}

router.get('/books', logger, getBooks);
```

**Analogy:** Middleware is like a **security checkpoint at an airport**. The request must pass through the checkpoint before continuing to its destination.

**Request → Middleware → Route Handler → Response**

---

## Reflection

### 1. What are your learning goals after reading and reviewing the class README?

My goal is to understand how Express uses **routes, routers, middleware, and REST methods** to organize communication between a client and server.

I also want to become more comfortable recognizing the request-response flow:

**Client → Request → Route → Middleware → Handler → Response**