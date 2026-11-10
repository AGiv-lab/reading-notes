# Reading 28: Component Lifecycle / useEffect() Hook

## WHY — Why Use useEffect?

React components sometimes need to interact with systems outside React, such as APIs, timers, or event listeners.

The `useEffect()` Hook allows function components to synchronize with these external systems during their lifecycle.

## WHAT — Reading Questions

### 1. What is the main intended use case for useEffect?

`useEffect()` synchronizes a component with an external system.

Examples:
- Connecting to a server
- Setting up event listeners
- Starting and stopping timers

### 2. How does the effect's logic interact with the component?

React runs the effect after committing the component's changes. The dependency array controls when it runs again.

```jsx
useEffect(() => {
  console.log('Component rendered');
});
```

**Dependency examples:**

| Dependency | When it runs |
|---|---|
| No array | After every committed render |
| `[]` | On mount |
| `[count]` | On mount and when `count` changes |

```jsx
useEffect(() => {
  console.log('Count changed:', count);
}, [count]);
```

The effect runs initially and whenever `count` changes.

### 3. What is the importance of the return value?

The effect can return a **cleanup function**.

Cleanup prevents unnecessary timers, subscriptions, or event listeners from continuing.

React runs cleanup before rerunning an effect with changed dependencies and when the component unmounts.

```jsx
useEffect(() => {
  const timer = setInterval(() => {
    console.log('Timer running');
  }, 1000);

  return () => clearInterval(timer);
}, []);
```

The timer starts when the component mounts and is cleared during cleanup.

## HOW — Component Lifecycle

A React component has three main lifecycle stages:

1. **Mount:** The component appears on the screen.
2. **Update:** The component re-renders when props or state change.
3. **Unmount:** The component is removed from the screen.

`useEffect()` helps manage synchronization and cleanup during these stages.

### Example: Socket Event Listener

```jsx
useEffect(() => {
  socket.on('greenlight', handleTheGreenLight);

  return () => {
    socket.off('greenlight', handleTheGreenLight);
  };
}, []);
```

- `socket.on()` registers an event listener.
- `socket.off()` removes the listener during cleanup.
- This prevents duplicate listeners when a component mounts again.

## useState vs. useEffect

| Hook | Purpose |
|---|---|
| `useState()` | Stores and updates component state |
| `useEffect()` | Synchronizes with external systems |

**Example:** `useState()` stores a counter value, while `useEffect()` can update an external system when that value changes.

## Key Takeaway

`useEffect()` manages synchronization with external systems. Dependencies determine when the effect reruns, and cleanup functions release resources when they are no longer needed.

## Resources

- [useEffect Hook Reference](https://react.dev/reference/react/useEffect#reference)
- [Responding to Events](https://react.dev/learn/responding-to-events)
- [Conditional Rendering](https://react.dev/learn/conditional-rendering)
- [Updating Arrays in State](https://react.dev/learn/updating-arrays-in-state)