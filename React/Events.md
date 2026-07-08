
## How Events are handled in React ?
## What is a Synthetic Event in React ?

If you’ve heard the term **“synthetic React”**, what people actually mean is **React’s Synthetic Event System** — not a separate version of React. It’s a core part of how React handles browser events efficiently and consistently.

Let me break it down clearly so you can lock this concept in.

---

# ⭐ **What is a Synthetic Event in React?**
A **Synthetic Event** is React’s own wrapper around the browser’s native event object.

> It provides a **consistent, cross‑browser event interface** and powers React’s **event delegation** system.

So when you write:

```jsx
<button onClick={handleClick}>Click</button>
```

The `event` you receive in `handleClick` is **not** the browser’s native event — it’s a **SyntheticEvent** created by React.

---

# 🧠 Why React Uses Synthetic Events

### 1. **Cross‑browser consistency**
Different browsers implement events differently.  
React normalizes them so your code behaves the same everywhere.

### 2. **Performance via event delegation**
React attaches **one event listener** at the root (like `document`) and uses delegation to handle events for all components.

This means:
- fewer event listeners  
- faster updates  
- better memory usage  

### 3. **Unified API**
Every event in React has the same interface:
- `event.target`
- `event.currentTarget`
- `event.preventDefault()`
- `event.stopPropagation()`

No browser quirks.

---

# 🔍 Example of Synthetic Event

```jsx
function handleClick(e) {
  console.log(e); // SyntheticEvent
}
```

Even though it looks like a normal event, React controls it internally.

---

# 🧩 Synthetic Events vs Native Events

| Feature | Synthetic Event | Native Event |
|--------|------------------|--------------|
| Cross‑browser consistency | ✔ | ✘ |
| Event delegation | ✔ | ✘ |
| Performance optimized | ✔ | ✘ |
| Provided by browser | ✘ | ✔ |

---

# 🔥 Important Note
Older versions of React used **event pooling**, meaning the event object was reused.  
Modern React (17+) **no longer pools events**, so you can safely use events asynchronously.

---

# 🎯 In One Sentence
> **“Synthetic React” refers to React’s Synthetic Event system — a unified, cross‑browser, performance‑optimized wrapper around native DOM events.**

---
