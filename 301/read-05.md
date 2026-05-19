# React Study Notes

[React Docs - Thinking in React](https://reactjs.org/docs/thinking-in-react.html){:target="_blank"}

## 1. What is the Single Responsibility Principle?

The **Single Responsibility Principle (SRP)** means that a component should only have **one main job or responsibility**.

### Example

A `Header` component should only handle displaying the header.

A `HornedBeast` component should only handle displaying beast information.

### Why It Matters

Keeping components focused makes them:

- easier to read
- easier to debug
- easier to reuse
- easier to maintain

---

## 2. What Does It Mean to Build a "Static" Version of an Application?

A **static version** means building the UI so it visually works **before adding interactivity or state**.

You create:

- components
- layout
- text
- images
- styling

…but no dynamic behavior yet.

### Example

A page that displays cards and buttons, but the buttons do not do anything yet.

---

## 3. Once You Have a Static Application, What Do You Need to Add?

After the static version is complete, you add:

- **state**
- **event handlers**
- **interactivity**
- dynamic updates

### Examples

- button clicks
- form inputs
- counters
- filters
- toggles

Usually this means using React features like:

```jsx
useState()

# React State Notes

## 4. What Are the Three Questions to Determine if Something is State?

When deciding if data should be stored in React state, ask these three questions:

### 1. Is it passed in from a parent via props?

If the data comes from a parent component through `props`, then it is probably **not state** in the current component.

---

### 2. Does it stay the same over time?

If the value never changes, it usually does **not** need to be state.

Static values can simply be regular variables or props.

---

### 3. Can it be computed from other state or props?

If the value can be calculated using existing state or props, then it usually should **not** be separate state.

This helps avoid duplicate or unnecessary state.

---

## Rule of Thumb

If the answer to all three questions is **no**, then the value is probably state.

---

# 5. How Can You Identify Where State Needs to Live?

State should live in the:

> closest common parent component that needs access to the data

This concept is called:

## "Lifting State Up"

---

## Example

If two child components both need the same data:

1. Store the state in their parent component
2. Pass the data down using props

---

## Goal of Good State Management

Keep state:

- centralized
- organized
- shared only where needed
- easy to maintain

## [Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK){:target="_blank"}

##  What is a "Higher-Order Function"?

A **higher-order function** is a function that:

- takes another function as an argument, OR
- returns another function

Higher-order functions help make code:

- reusable
- flexible
- cleaner

---

## Example

```js
function greet(name) {
  return `Hello ${name}`;
}

function processUser(callback) {
  return callback("Amity");
}

processUser(greet);

- What is Line 2 of the `greaterThan` Function Doing?

## Example Function

```js
function greaterThan(n) {
  return m => m > n;
}

# What Happens in `greaterThan(10)`

- `greaterThan(10)` creates a new function
- the new function remembers `n = 10`
- later it checks if another number is greater than 10

This is called a **closure**.

---

# How `map()` Works

`map()` is a **higher-order function** because it takes another function as an argument.

It creates a **new array** by changing each item in the original array.

---

## Example

```js
const nums = [1, 2, 3];

const doubled = nums.map(num => num * 2);