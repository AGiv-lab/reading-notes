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

