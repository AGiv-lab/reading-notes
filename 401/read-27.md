# Reading 27: useState() Hook

## WHY — Why Use State?

React components need to remember information between renders, such as user input, counters, and selected items.

The `useState()` Hook allows components to store information and update the UI when that information changes.

## WHAT — Thinking in React

### Five Steps of Thinking in React

1. **Break the UI into components:** Identify reusable pieces, such as Header, SearchBar, and ProductList.
2. **Build a static version:** Create the UI using props before adding interactivity.
3. **Identify minimal state:** Determine which data changes and cannot be calculated from other values.
4. **Decide where state belongs:** Place state in the closest common parent that needs it.
5. **Add inverse data flow:** Pass event handlers to child components so they can request state updates.

## State: A Component's Memory

### 1. Why isn't a local variable sufficient?

Local variables do not persist between renders, and changing them does not trigger React to re-render.

### 2. What is the argument to useState, and what does it return?

The argument is the **initial state value**.

`useState()` returns an array containing:

1. The current state value.
2. A setter function that updates the state and requests a re-render.

**Example:**

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

- `count` stores the current value.
- `setCount()` updates it.
- `0` is the initial value.

### 3. How can Component A access state from Component B?

Components do not directly access each other's local state.

Move shared state to their closest common parent and pass it down through **props**.

**Example:**

```jsx
function Parent() {
  const [name, setName] = useState('Alex');

  return (
    <>
      <ComponentA name={name} />
      <ComponentB setName={setName} />
    </>
  );
}
```

Component A receives the current name. Component B receives a function that can update it.

## HOW — State Updates

1. The component renders using its current state.
2. The user interacts with the UI.
3. An event handler calls the state setter.
4. React renders the component again.
5. React commits any necessary DOM changes.

**Example:** Clicking a counter button changes `count` from `0` to `1`, updating the displayed value.

## Key Concepts

- **State:** Information a component remembers.
- **useState:** React Hook for managing state.
- **Setter:** Function that requests a state update.
- **Props:** Data passed from parent to child.
- **Lifting State Up:** Moving shared state into a common parent.
- **Re-render:** React recalculates the component's UI.

## Key Takeaway

Use `useState()` when a component needs to remember changing information and display updates. Use props to share information between components.

## Resources

- [Thinking in React](https://react.dev/learn/thinking-in-react)
- [State: A Component's Memory](https://react.dev/learn/state-a-components-memory)
- [Passing Props to a Component](https://react.dev/learn/passing-props-to-a-component)
- [Rendering Lists](https://react.dev/learn/rendering-lists)
- [State as a Snapshot](https://react.dev/learn/state-as-a-snapshot)
- [useState Hook Reference](https://react.dev/reference/react/useState)