## Notes Class 10

### 1. What is a cache?

A **cache** is temporary storage used to save data so it can be retrieved faster instead of requesting it again from an API or database.

---

### 2. What is a cache hit? What is a cache miss?

- **Cache Hit** = Data is found in the cache and can be used immediately.
- **Cache Miss** = Data is not found in the cache and must be fetched from an API or database.

---

### 3. What does `debugger` do in your code?

The `debugger` keyword pauses code execution and opens debugging tools so you can inspect variables and program flow.

```javascript
debugger;
```

---

### 4. What is a breakpoint?

A **breakpoint** is a place where code execution pauses so you can inspect values and troubleshoot problems.

---

### 5. List 5 different debugging tools

1. `console.log()`
2. Browser DevTools
3. `debugger`
4. Breakpoints
5. Network Tab

---

### 6. Adding Data to the Cache

Before making an API request, check whether the data already exists in memory.

```javascript
if (inMemoryDB[ingredient] !== undefined) {
  // Cache Hit
  return inMemoryDB[ingredient];
} else {
  // Cache Miss
  // Get data from API
  inMemoryDB[ingredient] = recipeArr;
}
```

**How it works:**
- Check the cache first.
- If data exists → use it.
- If not → fetch data and save it in the cache.

---

### 7. Tracking How Old Cached Data Is

Add a timestamp when data is stored.

```javascript
function Recipe(obj) {
  // other properties
  this.dateAdded = Date.now();
}
```

**Purpose:**
- Records when data was cached.
- Helps determine whether cached data is still fresh.

---

### 8. Checking Cache Expiration

Compare the current time to the saved timestamp.

```javascript
if (cache[key] && (Date.now() - cache[key].dateAdded < 50000)) {
  console.log('Cache hit');
} else {
  // Cache expired
  // Get fresh data from API
}
```

**How it works:**
- If data is less than 50,000 ms old → use cache.
- If data is older → discard it and request fresh data.

*Browser → API → Server → Database*

*Database → Server → API → Browser*

*Caching saves a copy somewhere in the middle so you don't have to repeat the whole trip every time.*