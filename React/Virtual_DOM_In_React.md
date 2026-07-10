
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
