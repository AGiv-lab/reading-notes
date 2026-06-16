# In-Memory Storage Notes

## JavaScript Call Stack

### What is a Call?
- Running a function.

### How many Calls can happen at once?
- One at a time (single-threaded).

### What does LIFO mean?
- **Last In, First Out**
- The most recent function runs first.

### Example Call Stack

```javascript
function first() {
  second();
}

function second() {
  third();
}

function third() {
  console.log("Hello");
}

first();
```

### Call Stack Order

```text
third()
second()
first()
```

### What causes a Stack Overflow?
- Too many function calls.
- Often caused by infinite recursion.


Example:

```javascript
function loop() {
  loop();
}

loop();
```

---
-[JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c){:target="_blank"}


## JavaScript Error Messages

### What is a Reference Error?
- Using a variable that doesn't exist.

```javascript
console.log(myVariable);
```

### What is a Syntax Error?
- Invalid JavaScript syntax.

```javascript
if (true {
  console.log("Hello");
}
```

### What is a Range Error?
- A value is outside the allowed range.

```javascript
new Array(-1);
```

### What is a Type Error?
- Using a value in the wrong way.

```javascript
const num = 5;
num();
```

---

## Debugging

### What is a Breakpoint?
- A place where code pauses during execution.

### What does `debugger` do?
- Pauses code and opens debugging tools.

```javascript
debugger;
```
- [JavaScript errors reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors){:target="_blank"}

---

# Key Terms

| Term | Meaning |
|--------|---------|
| Call | Running a function |
| Call Stack | Functions currently executing |
| LIFO | Last In, First Out |
| Stack Overflow | Too many function calls |
| Reference Error | Using something that doesn't exist |
| Syntax Error | Invalid code syntax |
| Range Error | Value outside allowed range |
| Type Error | Wrong use of a value |
| Breakpoint | Pause point for debugging |
| debugger | Pauses code execution |

---

# Learn More

### What is recursion?
- A function calling itself.

### Why is JavaScript single-threaded?
- One task at a time.

### What is the event loop?
- Manages async tasks.

### How do I read stack traces?
- Start at the first error.

### When should I use breakpoints?
- When tracking bugs.

### debugger vs console.log()?
- Pause vs print values.

### How do I avoid stack overflow?
- Ensure recursion has a stopping condition.