# Functional Programming Notes

## Functional Programming

### What is Functional Programming?

A programming style that uses functions to solve problems.

**Goals:**
- Use small functions
- Avoid changing data
- Return new values

---

### What is a Pure Function?

A function that:

- Same input → same output
- No side effects

**Example:**

```js
function add(a, b) {
  return a + b;
}
```

✅ Pure

---

**Not Pure:**

```js
let total = 0;

function addToTotal(num) {
  total += num;
}
```

❌ Changes outside data

---

### Benefits of Pure Functions

- Easier to read
- Easier to test
- Easier to debug
- Easier to reuse
- Predictable results

---

### What is Immutability?

Immutability = data cannot be changed.

Instead of modifying data, create new data.

❌ Modify existing array:

```js
numbers.push(4);
```

✅ Create a new array:

```js
const newNumbers = [...numbers, 4];
```

---

### What is Referential Transparency?

A function call can be replaced with its result.

**Example:**

```js
function multiply(a, b) {
  return a * b;
}

multiply(2, 3);
```

Can be replaced with:

```js
6
```

Program behaves the same.

---

# Node.js Modules

### What is a Module?

A separate JavaScript file.

**Examples:**

```text
math.js
users.js
app.js
```

Benefits:
- Organized code
- Reusable code
- Easier maintenance

---

### What does `require()` do?

Imports code from another file.

**Example:**

```js
const math = require('./math');
```

---

### How do we bring another module into a file?

Use `require()`.

```js
const math = require('./math');
```

Steps:
1. Find file
2. Load file
3. Store in variable
4. Use its code

---

### What do we have to do to make a module available?

Use `module.exports`.

**Export:**

```js
function add(a, b) {
  return a + b;
}

module.exports = add;
```

**Import:**

```js
const add = require('./math');
```

---

# Quick Reference

| Term | Meaning |
|--------|---------|
| Functional Programming | Programming with functions |
| Pure Function | Same input = same output |
| Side Effect | Changes outside data |
| Immutability | Don't modify existing data |
| Referential Transparency | Replace function with result |
| Module | Separate JS file |
| require() | Import code |
| module.exports | Export code |

---

# Learn More

### Why are pure functions useful?
Predictable behavior.

### What is a side effect?
Changing outside data.

### Why avoid mutating data?
Reduces bugs.

### What is state?
Stored application data.

### Why use modules?
Organization and reuse.

### require() vs import?
Different module systems.

### What is CommonJS?
Node.js module system.

### What is ES Modules?
Modern JavaScript modules.

### Can a module export multiple functions?
Yes.

### Why split code into files?
Cleaner projects.

---

# ELI10 Summary

```text
Functions do work.

Pure functions are predictable.

Immutability means don't change old data.

Modules split code into smaller files.

module.exports = share code
require() = use shared code
``` 
# Notes

## 1. What is DRY code?

**DRY** = **Don't Repeat Yourself**

- Avoid duplicate code.
- Write reusable functions.
- Makes code easier to maintain.

---

## 2. Why do we modularize our code?

- Keeps files smaller.
- Makes code easier to read.
- Reuses code in multiple places.
- Easier to debug and maintain.

---

## 3. What is a Promise?

A **Promise** is an object that represents a future value.

It can be:

- Pending
- Fulfilled (success)
- Rejected (error)

Example:

```javascript
axios.get(url);
```

The request takes time, so it returns a Promise.

---

## 4. What is the difference between a Promise and `.then()/.catch()`?

### Promise
The object that represents future data.

### .then() / .catch()
Methods used to handle the Promise result.

Example:

```javascript
axios.get(url)
  .then(result => console.log(result))
  .catch(err => console.error(err));
```

---

## 5. async/await vs .then()/.catch()

### async/await

```javascript
async function doSomething() {
  try {
    const results = await axios.get(url);
  }
  catch (err) {
    console.error(err);
  }
}
```

**Pros**
- Easier to read
- Looks like normal code

**Requires**
- `try/catch` for errors

---

### .then()/.catch()

```javascript
function doSomething() {
  axios
    .get(url)
    .then(results => {
      // use results
    })
    .catch(err => console.error(err));
}
```

**Pros**
- Built-in error handling with `.catch()`

**Note**
- Variables inside `.then()` only exist in that block

---

## 6. Modularizing a File on the Server

Export a function:

```javascript
function doSomething() {
  // does something cool
}

module.exports = doSomething;
```

OR

```javascript
module.exports = () => {
  // does something cool
};
```

Import it:

```javascript
const doSomething = require('./path-to-doSomething');
```

---

## 7. Exporting Multiple Functions

Export an object:

```javascript
module.exports = {
  doSomething: function() {
    // does something cool
  },

  doSomethingElse: function() {
    // does something else
  }
};
```

Import it:

```javascript
const doesStuffObject = require('./path-to-doesStuffObject');
```

Use the functions:

```javascript
doesStuffObject.doSomething();
doesStuffObject.doSomethingElse();
```

---

# Quick Reference

| Term | Meaning |
|--------|---------|
| DRY | Don't Repeat Yourself |
| Module | Separate reusable file |
| Promise | Future value |
| .then() | Handle success |
| .catch() | Handle errors |
| async | Marks async function |
| await | Waits for Promise |
| module.exports | Shares code |
| require() | Imports code |

