# Reading 29: Advanced State with Reducers

## WHY — Why Use Reducers?

React's `useReducer()` Hook helps manage complex state updates by organizing the update logic in one function.

Reducers are useful when multiple actions affect the same state, making the code easier to understand and maintain.

## WHAT — Reading Questions

### 1. What is the motivation for adding a reducer?

When a component has many state updates, the logic can become difficult to manage.

A reducer moves state update logic into a separate function, keeping event handlers simpler.

### 2. What are actions in the context of a reducer?

Actions are JavaScript objects describing what happened.

**Example:**

```javascript
{ type: 'increment' }
```

An action tells the reducer what kind of update to perform.

### 3. How are actions different from setting state directly?

- `useState()` updates state using a setter function.
- `useReducer()` sends an action through `dispatch()`.
- The reducer examines the action and calculates the next state.

**Example:**

```javascript
// useState
setCount(count + 1);

// useReducer
dispatch({ type: 'increment' });
```

### 4. What common list operation is useReducer named for, and why?

It is named after JavaScript's `reduce()` array method.

Both use a function to calculate a new accumulated result from previous values and new input.

A React reducer calculates the next state from the current state and an action.

### 5. When should you switch from useState to useReducer?

Consider `useReducer()` when:

- State updates become complicated.
- Several actions modify the same state.
- Event handlers contain repetitive update logic.
- You want to organize state transitions in one place.

For simple counters or input fields, `useState()` is often sufficient.

## HOW — Reducer Example

```jsx
import { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>
        Add
      </button>
      <button onClick={() => dispatch({ type: 'decrement' })}>
        Subtract
      </button>
    </>
  );
}
```

### How It Works

1. The user clicks a button.
2. `dispatch()` sends an action.
3. The reducer receives the current state and action.
4. The reducer returns the next state.
5. React re-renders with the updated state.

## useState vs. useReducer

| useState | useReducer |
|---|---|
| Simple state updates | More complex state logic |
| Uses setter functions | Uses dispatch and actions |
| Logic often stays in handlers | Logic is centralized in a reducer |
| Less setup | More structure |

## Key Concepts

- **Reducer:** Function that calculates the next state.
- **Action:** Object describing what happened.
- **Dispatch:** Function that sends an action to the reducer.
- **State:** Information React remembers between renders.
- **Pure Function:** Produces the same output for the same inputs without side effects.

## Key Takeaway

`useReducer()` helps organize complicated state updates. Actions describe what happened, and the reducer determines how state should change.

## Resources

- [Extracting State Logic into a Reducer](https://react.dev/learn/extracting-state-logic-into-a-reducer)
- [useReducer Hook](https://react.dev/reference/react/useReducer)
- [Keeping Components Pure](https://react.dev/learn/keeping-components-pure)
- [Queueing a Series of State Updates](https://react.dev/learn/queueing-a-series-of-state-updates)