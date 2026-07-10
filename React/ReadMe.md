> ## What is React ? 
>  React is a JavaScript library for building user interfaces, created and maintained by Meta (Facebook).   
>  It allows developers to create reusable UI components.   

-------------------------------------------------------
> ## Why React ?

> ## [Difference between React and Angular](Difference_between_React_and_Angular.md)

> ## [What is DOM (Document Object Model)]((Virtual_DOM_In_React.md))
> The DOM is a tree-like structure that represents your HTML page.   

> ## [Difference Between Virtual DOM and Real DOM](Virtual_DOM_In_React.md)

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




> ## [Explain Component Lifecycle in React](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/React/Component_Lifecycle_In_React.md)
> 
---------------------------------------------------------------

> ## What is component in React ?
> A React component is a reusable, self-contained piece of UI that manages its own structure, logic, and behavior. It receives data through props, can maintain internal state, and returns JSX to describe what should appear on the screen.

----------------------------------------------------------------

> ## what is super() ? (class component only)
> - super() calls the parent class constructor.
> - super(props) makes this.props available.
> - You must call super() before using this in a constructor.
> - It’s required only in class components, not functional components.

-------------------------------------------------------------------

> ## [How Events are handled in React ?](Events.md)
