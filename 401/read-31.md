# Reading 31: Context API

## WHY — Why Use Context?

React applications often have multiple components that need access to the same information, such as a theme or user login status.

Normally, data passes from parent to child through props. Passing props through several components that do not need the data is called **prop drilling**.

React Context helps solve this problem by allowing components to access shared data without passing props through every intermediate component.

## WHAT — Five Principles for Structuring State

1. **Group related state:** Combine state variables that change together.
2. **Avoid contradictions:** Prevent state variables from conflicting with each other.
3. **Avoid redundant state:** Do not store values that can be calculated from existing state or props.
4. **Avoid duplication:** Keep one source of truth for shared information.
5. **Avoid deeply nested state:** Use flatter data structures that are easier to update.

## HOW — Context API Questions

### 1. What problem do Contexts aim to solve?

Context helps solve prop drilling. It allows components to access shared information from an ancestor without passing props through every intermediate component.

### 2. What is one technique to try before useContext?

Try **component composition**, such as passing components through the `children` prop. This can reduce unnecessary prop passing.

### 3. What hook complements useContext for complex applications?

**useReducer** works with useContext to manage complex state.

- `useReducer` manages state updates.
- `useContext` allows components to access shared state and dispatch functions.

## HOW — Simple React Example

```jsx
import { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function Header() {
  const theme = useContext(ThemeContext);

  return <h1>Current theme: {theme}</h1>;
}

export default function App() {
  return (
    <ThemeContext value="dark">
      <Header />
    </ThemeContext>
  );
}
```

**Output:**

```text
Current theme: dark
```

The `Header` component accesses the theme directly through Context instead of receiving it as a prop.

*Note: This example uses React 19 provider syntax.*

## Additional Review

### Sharing State Between Components

When two components need the same state, move the state to their closest common parent. This is called **lifting state up**.

### Preserving and Resetting State

React preserves state based on where a component appears in the UI tree. Changing a component's `key` can reset its state.

## Resources

- [Choosing the State Structure](https://react.dev/learn/choosing-the-state-structure)
- [Passing Data Deeply with Context](https://react.dev/learn/passing-data-deeply-with-context)
- [Sharing State Between Components](https://react.dev/learn/sharing-state-between-components)
- [Preserving and Resetting State](https://react.dev/learn/preserving-and-resetting-state)