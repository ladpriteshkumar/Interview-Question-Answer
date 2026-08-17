> ## [What is React ?](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/React/What_is_React.md)

> ## What is component in React ?
> A React component is a reusable, self-contained piece of UI that manages its own structure, logic, and behavior. It receives data through props, can maintain internal state, and returns JSX to describe what should appear on the screen.

> ## [Difference between React and Angular](Difference_between_React_and_Angular.md)

> ## [What is DOM (Document Object Model)](Virtual_DOM_In_React.md)
> The DOM is a tree-like structure that represents your HTML page.   

> ## [Difference Between Virtual DOM and Real DOM](Virtual_DOM_In_React.md)

> ## [What is React Fiber and how does it differ from the old reconciliation algorithm?](https://drive.google.com/file/d/1WEWzNMIAI7YKH1KbikJVza6nOhfOqqhk/view)
> ## [Reconciliation vs React Fiber](https://drive.google.com/file/d/1YIv47ZDsAo9GulNTbiNOvHIqiz4OWcmE/view)
> ## [React Fiber](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/React/ReactFiber.md)
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

## 24. How is a node of a DOM tree updated in an application built in React? ##
When the state or props of a component change in React, a new virtual DOM tree is created, which is compared to the previous tree using a diffing algorithm. React identifies the minimal set of changes required to update the actual DOM and uses reconciliation to update only the corresponding nodes that have changed. This process minimizes the number of actual DOM operations that need to be performed.

## 25. What is a diffing algorithm in React?
A diffing algorithm in React is a process that compares the current virtual DOM tree with the previous one and identifies the minimal set of changes required to update the actual DOM. This is done by checking the type, props, and children of each node in the tree and updating only those specific parts of the DOM that need to be changed, rather than updating the entire tree.


> ## [Explain Component Lifecycle in React](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/React/Component_Lifecycle_In_React.md)
> 
---------------------------------------------------------------



----------------------------------------------------------------

> ## What is JSX and how does it work?
> JSX is a syntax extension ( that looks like HTML.) for JavaScript that lets you write HTML‑like markup directly inside your code, and it works by compiling that markup into plain JavaScript function calls (usually `React.createElement`)

> ## what is super() ? (class component only)
> - super() calls the parent class constructor.
> - super(props) makes this.props available.
> - You must call super() before using this in a constructor.
> - It’s required only in class components, not functional components.

-------------------------------------------------------------------

> ## [How Events are handled in React ?](Events.md)

>## What is the difference between controlled and uncontrolled components?
>A controlled component stores form input value in React state - React is the source of truth. An uncontrolled component stores value in the DOM itself, accessed via a `ref`. Controlled components are easier to validate and synchronize; uncontrolled components are simpler for file inputs or when integrating with non-React code.


---



---

