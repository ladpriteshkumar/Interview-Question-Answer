> ## [What is DOM (Document Object Model)
> The DOM is a tree-like structure that represents your HTML page.   
> Ref : [geeksforgeeks](https://www.geeksforgeeks.org/javascript/dom-document-object-model/)>

>## Difference Between Virtual DOM and Real DOM
>
>|        | Real DOM              | Virtual DOM                 |
>|---------------|----------------------|-----------------------------|
>| **Definition**   | The real Document Object Model used by browser   | A light weight in-memory representation of the Actual DOM(Real DOM)          |
>| **Performance** | Every update directly manipulates the DOM, Leading to potential slower perfomance. | Optimizes updates by calculating minimal changes needed. |
>| **Rendering Process** | Updates the real DOM directly without any intermediate step. | Updates the virtual DOM first, then reconciles with the real DOM. |
>| **Efficiency** | Can become inefficient with frequent updates, especially in large applications. | More efficient for complex applications, reduces reflow and repaint. |
>| **Use Case**| Used for simple Static web pages where updates are not required | Ideal for dynamic and intractive web pages |
>
> [Rererence](https://www.geeksforgeeks.org/difference-between-virtual-dom-and-real-dom/)
-----------------------------------------------------------

> ## how do you render react component to the DOM ?
You render a React component to the **DOM** using the `ReactDOM.createRoot()` API (React 18+) or the older `ReactDOM.render()` (React 17 and earlier).

---

## **React 18+ (current standard)**  
This is the modern, recommended way.

### **Step 1: Have a root DOM element**
```html
<div id="root"></div>
```

### **Step 2: Render your React component**
```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(<App />);
```

**What’s happening:**  
- `createRoot()` creates a React root.  
- `.render(<App />)` tells React to mount your component into the real DOM.

---

##  Why React needs this step
React doesn’t automatically know *where* to put your UI.  
You choose a DOM node (usually `#root`) and tell React:

> “Render my component tree here.”

React then takes over that DOM node and manages everything inside it.

---
