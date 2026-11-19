# Reading 32: Context API — Behaviors

## WHY — Why Combine useReducer and useContext?

As React applications grow, managing state across multiple components becomes more complicated. Passing state and functions through several components can lead to **prop drilling**, making the code harder to maintain.

Combining `useReducer` and `useContext` helps organize state management and allows components to share information without passing props through every level.

## WHAT — How Do useReducer and useContext Work Together?

`useReducer` manages state and the logic for updating it. It uses a reducer function that receives the current state and an action, then returns the updated state. This keeps state changes organized in one place instead of spreading the update logic across multiple components.

`useContext` allows components to access shared state and the `dispatch` function without receiving them through props. When combined, `useReducer` controls how state changes, while Context makes the state and dispatch function available to components below a provider. This simplifies state management in larger React applications.

## HOW — Simple Example

```jsx
import { createContext, useContext, useReducer } from 'react';

const CountContext = createContext(null);

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    default:
      return state;
  }
}

function Counter() {
  const { state, dispatch } = useContext(CountContext);

  return (
    <button onClick={() => dispatch({ type: 'increment' })}>
      Count: {state.count}
    </button>
  );
}

export default function App() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <CountContext value={{ state, dispatch }}>
      <Counter />
    </CountContext>
  );
}
```

### How It Works

1. `useReducer` manages the counter state.
2. `createContext` creates a way to share information.
3. `CountContext` provides the state and dispatch function.
4. `useContext` allows `Counter` to access them.
5. Clicking the button dispatches an action that updates the count.

**Key Takeaway:** `useReducer` manages how state changes, while `useContext` makes that state and its dispatch function accessible to components without prop drilling.

*Note: This example uses React 19 provider syntax.*

## Resource

[Scaling Up with Reducer and Context](https://react.dev/learn/scaling-up-with-reducer-and-context)