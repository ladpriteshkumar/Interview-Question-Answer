React.memo and useMemo sound similar, but they solve **completely different problems**. If you mix them up, you’ll end up with confusing bugs or unnecessary re-renders. Let’s break them down clearly so you never confuse them again.

---

# 🎯 **The Core Difference**
**React.memo → Prevents component re-renders**  
**useMemo → Prevents expensive calculations from re-running**

They operate at different levels:
- **React.memo works at the component level**
- **useMemo works inside a component**

---

# 🧩 **1. React.memo — Component Re-render Optimization**

### ✔ What it does  
Wraps a component and tells React:  
> “Only re-render this component if its props change.”

### ✔ Use it when  
- A child component re-renders too often  
- Props rarely change  
- You want to avoid unnecessary renders

### Example
```jsx
const Child = React.memo(function Child({ value }) {
  console.log("Child rendered");
  return <div>{value}</div>;
});
```

If the parent re-renders but `value` stays the same, `Child` **won’t re-render**.

### 🔥 React.memo prevents:
- Wasted renders  
- Slow UI updates  
- Re-render chains  

---

# 🧩 **2. useMemo — Value/Computation Memoization**

### ✔ What it does  
Memoizes (caches) the **result of a calculation** so it doesn’t run on every render.

### ✔ Use it when  
- You have expensive calculations  
- You compute derived data  
- You want stable references (e.g., dependency arrays)

### Example
```jsx
const sortedList = useMemo(() => {
  return heavySortFunction(list);
}, [list]);
```

If `list` doesn’t change, React **reuses the previous result**.

### 🔥 useMemo prevents:
- Slow calculations  
- Re-running heavy logic  
- Unnecessary re-computation  

---

# 🧠 **React.memo vs useMemo — Side-by-Side**

| Feature | React.memo | useMemo |
|--------|------------|---------|
| Prevents re-renders | ✔ Yes | ✘ No |
| Prevents recalculation | ✘ No | ✔ Yes |
| Used on | Components | Values/Functions |
| Syntax | `React.memo(Component)` | `useMemo(() => fn, [deps])` |
| Purpose | Skip rendering | Skip computation |
| Level | Component-level | Inside component |

---

# 🔥 **Common Misunderstandings**
### ❌ “useMemo prevents re-renders”  
No — it only prevents recalculations.

### ❌ “React.memo makes components faster automatically”  
Only if props rarely change.

### ❌ “You should use both everywhere”  
Overusing them **hurts** performance. Use them only when needed.

---

# 🚀 When to Use Which?

### Use **React.memo** when:
- A child component re-renders too often  
- Props rarely change  
- You want to stop unnecessary renders  

### Use **useMemo** when:
- You have expensive logic  
- You compute derived values  
- You need stable references for `useEffect`, `useCallback`, or props  

---

# 🎯 In One Sentence
> **React.memo stops components from re-rendering; useMemo stops expensive calculations from re-running.**

---

If you want, I can also explain:
- React.memo vs useCallback  
- When memoization becomes harmful  
- Real-world examples where memoization boosts performance  

Just tell me what direction you want to go next.
