# React Lifecycle

## 1. What happens first: `render()` or `componentDidMount()`?

**`render()` happens first**

Order:
1. `constructor()`
2. `render()`
3. `componentDidMount()`

`componentDidMount()` runs after the component has been rendered and mounted to the DOM.

---

## 2. What is the very first thing to happen in the React lifecycle?

**`constructor()`**

It is called first when a class component is created.

Used for:
- Initializing state
- Binding methods
- Setting up the component before rendering

Example:

```javascript
constructor(props) {
  super(props);

  this.state = {
    count: 0
  };
}
```

---

## 3. Put these in order

Correct order:

1. `constructor`
2. `render`
3. `componentDidMount`
4. `React Updates`
5. `componentWillUnmount`

---

## 4. What does `componentDidMount()` do?

Runs once after the component is mounted into the DOM.

Common uses:
- Fetch data from APIs
- Start timers
- Add event listeners
- DOM manipulation
- Set up subscriptions

Example:

```javascript
componentDidMount() {
  fetch('/api/users')
    .then(res => res.json())
    .then(data => this.setState({ users: data }));
}
```

---

# React State vs Props

## 5. What types of things can you pass in props?

You can pass:

### Strings
```jsx
<User name="Sam" />
```

### Numbers
```jsx
<Product price={29.99} />
```

### Booleans
```jsx
<Button disabled={true} />
```

### Arrays
```jsx
<List items={["A", "B", "C"]} />
```

### Objects
```jsx
<User person={{ name: "Sam", age: 22 }} />
```

### Functions
```jsx
<Button onClick={handleClick} />
```

### Components / JSX (`children`)
```jsx
<Card>
  <h1>Hello</h1>
</Card>
```

---

## 6. What is the big difference between props and state?

### Props
- Passed into a component
- Read-only
- Controlled by parent component

**Props = Inputs**

---

### State
- Managed inside a component
- Can change over time
- Updates trigger re-renders

**State = Component Memory**

---

## 7. When do we re-render our application?

React re-renders when:

### When the State changes
```javascript
setCount(count + 1);


### When Props change
Parent passes new data down.

---

## 8. Examples of things we could store in state

### Form Inputs
```javascript
email
password
```

### Counters
```javascript
count
```

### Toggles / UI State
```javascript
isLoggedIn
darkMode
modalOpen
```

### API Data
```javascript
users
posts
products
```

### App State
```javascript
loading
error
selectedTab
```

### Game/App Data
```javascript
score
playerPosition
shoppingCart
```

---

## Props vs State Summary

| Props | State |
|------|------|
| Passed in | Managed inside component |
| Read-only | Can change |
| Controlled by parent | Controlled by component |
| Inputs | Memory/data |

---

## Modern React Note

In modern React, class lifecycle methods like:

- `componentDidMount()`
- `componentWillUnmount()`

are often replaced with Hooks like:

```javascript
useEffect(() => {
  // componentDidMount logic

  return () => {
    // componentWillUnmount cleanup
  };
}, []);
```