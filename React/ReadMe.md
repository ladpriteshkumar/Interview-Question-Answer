> ## What is React ? 
>  React is a JavaScript library for building user interfaces, created and maintained by Meta (Facebook).   
>  It allows developers to create reusable UI components.   

-------------------------------------------------------

> ## Fearures of React 
>  #### The key features of React are:
>  * **Component-based architecture:** A Component is the smallest unit in a React application. Anything that is to be rendered on the browser can be rendered through components. Components help in maintainability and re-usability.
>  * __Virtual DOM:__ React uses virtual DOM concept for DOM manipulation which improves the performance of the application.
>  * __Unidirectional data flow:__  React’s one-way data flow (also called one-way binding) keeps everything modular and fast and easy to debug.
>  * __JSX syntax:__ React used JSX syntax which is similar to XML and HTML syntax that makes it easy for writing markup and binding events in components. 
>  * __SEO performance:__ The SEO performance can be improved using the server-side rendering concept.  Isomorphic applications can be developed by using React which increases the SEO performance.

------------------------------------------------------------

> ## Can you explain the concept of a Virtual DOM in React, and how it contributes to performance?
> The Virtual DOM is a lightweight copy of the actual DOM that React uses to keep track of changes in the UI. When a component's state or props change, React creates a new Virtual DOM tree, compares it to the previous tree, and identifies the specific changes that need to be made to the actual DOM. This allows React to update only the necessary parts of the UI, rather than the entire tree, which contributes to better performance. The Virtual DOM also allows for efficient batch updates and reduces the frequency of expensive DOM operations.

------------------------------------------------------------

> ## What is Reconciliation in react ?
> Reconciliation is React’s process of comparing the new Virtual DOM with the previous Virtual DOM and updating the real DOM with only the minimal necessary changes.

------------------------------------------------------------

> ## how keys affect reconciliation
> Keys give React a stable identity for each element in a list, allowing it to match old and new elements during reconciliation.   
> Keys tell React which items are which, enabling efficient reconciliation, correct DOM updates, and stable component state.

------------------------------------------------------------

> ## Difference Between Virtual DOM and Real DOM
>
>|        | Real DOM              | Virtual DOM                 |
>|---------------|----------------------|-----------------------------|
>| **Definition**   | The real Document Object Model used by browser   | A light weight in-memory representation of the Actual DOM(Real DOM)          |
>| **Performance** | Every update directly manipulates the DOM, Leading to potential slower perfomance. | Optimizes updates by calculating minimal changes needed. |
>| **Rendering Process** | Updates the real DOM directly without any intermediate step. | Updates the virtual DOM first, then reconciles with the real DOM. |
>| **Efficiency** | Can become inefficient with frequent updates, especially in large applications. | More efficient for complex applications, reduces reflow and repaint. |
>
> [Rererence](https://www.geeksforgeeks.org/difference-between-virtual-dom-and-real-dom/)
-----------------------------------------------------------
  
