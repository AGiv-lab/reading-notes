# Readings: Express REST API

## Review: ES6 Classes

1. **Classes are a template for creating:**  
   Objects.

2. **Can a class declaration be hoisted?**  
   No. A class must be declared before it can be used.

3. **How would you describe a constructor and contextual `this` to a non-technical friend?**  
   A constructor sets up a new object when it is created. `this` refers to the specific object currently being created or used.

## Using Express Routing

1. **Within Express, what does routing refer to?**  
   Routing determines how the server responds to requests made to specific endpoints.

2. **What is the difference between a route path and a route method?**  
   The **path** is the URL endpoint, such as `/books`. The **method** is the HTTP action, such as `GET`, `POST`, `PUT`, or `DELETE`.

3. **When is it appropriate to add `next` as a parameter to a route handler and what must you do if `next` has been passed to your middleware as a parameter?**  
   Use `next` when the request needs to continue to another middleware or handler. If middleware receives `next`, call `next()` when its work is complete so processing can continue.

## Express Routing

1. **What is an Express Router?**  
   An Express Router is a way to organize related routes into separate, manageable groups.

2. **By what means do we initialize `express.Router()` in an Express server?**  
   ```js
   const router = express.Router();

  3. **What do we use route middleware for?**
  Route middleware performs tasks during a request, such as validation, logging, authentication, or error handling. 

  ###Reflection
  **What are your learning goals after reading and reviewing the class README?**
  My goal is to better understand REST API structure, Express routing, middleware, and how classes can be used to organize application data and behavior.