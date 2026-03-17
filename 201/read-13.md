# 201-Reading_13

##Local Storage

### Why would a developer use local storage for a web application?

Developers use ***localStorage*** to save *small pieces of data in the browser* so they can be accessed later, even after the page is refreshed or the browser is reopened.

#### Common use cases:
- Storing user preferences (e.g., dark mode, language settings)
- Saving UI settings or customization options
- Remembering which tabs or pages were open last
- Keeping non-sensitive data for a better user experience

#### Key idea:
`localStorage` helps make web apps feel more **persistent and personalized** without needing a database.
small pieces of data so that the dev can come back to it later. Dark mode, language, settings. WHich tabs were open last.

## What information should NOT be stored in local storage?

You should **never store sensitive or security-related information in `localStorage`** because it is not secure and can be accessed by JavaScript.

###  Sensitive Personal Data
- Passwords  
- Credit/debit card information  
- Social Security numbers or IDs  
- Private personal details (if sensitive)

###  Authentication & Security Data
- Session IDs  
- JWT tokens (especially long-lived ones)  
- API keys  

###  Confidential or Financial Information
- Banking details  
- Private business data  
- Internal company information  

###  General Rule
> If the data would cause harm if exposed, do NOT store it in localStorage.

---

## Why is localStorage unsafe for this data?
- It is **not encrypted**
- It is **accessible via JavaScript**
- It is vulnerable to **XSS (cross-site scripting) attacks**
- Data persists even after the browser is closed

---

## Safe things to store in localStorage
- User preferences (e.g., dark mode)
- UI settings
- Non-sensitive cached data
Local storage can store what type of data? How would you convert it to that type before storing?

## What type of data can localStorage store?

`localStorage` can only store **data as strings**.

This means:
- Numbers, objects, arrays, and booleans must be converted into strings before storing.

---

## How do you convert data before storing?

You typically use **JSON methods** to convert and retrieve complex data:

###  Convert to string (before storing)
Use `JSON.stringify()`:
```js
const user = { name: "Alex", age: 25 };
localStorage.setItem("user", JSON.stringify(user));

### Convert back to original type (after retrieving)
-Use JSON.parse():
-const storedUser = JSON.parse(localStorage.getItem("user"));
console.log(storedUser.name); // "Alex"

#### Helpful use case:

localStorage stores strings only

Use JSON.stringify() to store complex data

Use JSON.parse() to convert it back when retrieving