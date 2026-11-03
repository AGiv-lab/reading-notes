# Reading 26: Component Based UI

## WHY — Why Use React?

React helps developers build interactive user interfaces using reusable components. Components make applications easier to organize, maintain, and update.

## WHAT — React Quick Start

**1. What are the building blocks of a React app?**

Components. They are reusable pieces of UI written as JavaScript functions that return JSX.

**2. What is the difference between an HTML element and a React component?**

- HTML elements are built-in tags such as `<div>` and `<button>`.
- React components are custom functions, written with capitalized names such as `<Header />`.

**3. What is JSX and why do we use it?**

JSX is a JavaScript syntax extension that lets us write HTML-like markup inside JavaScript.

It keeps UI structure and rendering logic together.

**4. How do we embed JavaScript expressions in JSX?**

Use curly braces `{}` to insert JavaScript expressions.

```jsx
const name = "Alex";
return <h1>Hello, {name}!</h1>;
```

**5. Does React or JSX have special features for iteration or conditional logic?**

No. React uses standard JavaScript.

- `.map()` renders lists.
- `if` statements and ternary operators handle conditions.

```jsx
items.map(item => <li key={item.id}>{item.name}</li>)
```

**6. How does React respond to user input?**

React uses event handlers such as `onClick` and `onChange`.

```jsx
<button onClick={handleClick}>Click Me</button>
```

**7. What word indicates a component manages data with a Hook? How can components share data?**

Hooks commonly start with `use`, such as `useState`.

Components can share data by lifting state to a common parent and passing values through props.

## HOW — Render and Commit

**1. What are the three steps of refreshing a React UI?**

1. Trigger — A render is requested.
2. Render — React calls components to determine what to display.
3. Commit — React applies necessary DOM changes.

**2. How do we trigger updates after the initial render?**

Update component state using a state setter, such as `setCount()`.

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
  Count: {count}
</button>
```

**3. Does React recreate DOM nodes on every re-render?**

No. React compares the rendered output and updates only the DOM parts that need changing.

**4. What happens after React updates the DOM?**

The browser paints the updated screen so the user can see the changes.

## Key Concepts

- **Component:** Reusable UI building block.
- **JSX:** HTML-like syntax inside JavaScript.
- **Props:** Data passed between components.
- **State:** Data a component remembers between renders.
- **Hook:** React function such as `useState`.
- **Render:** React calculates the UI.
- **Commit:** React applies changes to the DOM.

## Key Takeaway

React builds interfaces from reusable components. JSX describes the UI, props pass data, state manages changes, and React updates the DOM when necessary.

## Resources

- [React Quick Start](https://react.dev/learn)
- [Render and Commit](https://react.dev/learn/render-and-commit)
- [Your First Component](https://react.dev/learn/your-first-component)
- [Importing and Exporting Components](https://react.dev/learn/importing-and-exporting-components)
- [Writing Markup with JSX](https://react.dev/learn/writing-markup-with-jsx)
- [Sass Cheatsheet](https://devhints.io/sass)
- [React Cheatsheet](https://devhints.io/react)