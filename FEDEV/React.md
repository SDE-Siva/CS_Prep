# ReactJS interview questions:

### Basic Concepts

1. **What is React?**  
   React is an open-source JavaScript library used for building user interfaces, particularly for single-page applications. It allows developers to create reusable UI components and manage the state of their applications efficiently.

2. **What are components in React?**  
   Components are the building blocks of a React application. They can be functional or class-based and encapsulate the logic, structure, and styling of a part of the user interface. Components can be reused throughout the application.

3. **What is JSX?**  
   JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code within JavaScript. It makes it easier to create React elements and components:
   ```jsx
   const element = <h1>Hello, world!</h1>;
   ```

### State and Props

4. **What are props in React?**  
   Props (short for properties) are read-only attributes passed from a parent component to a child component. They allow data to be passed down through the component hierarchy.

5. **What is state in React?**  
   State is an object that holds the dynamic data of a component. It can change over time, usually in response to user actions or events. State is local to the component and can be modified using the `setState` method or the `useState` hook in functional components.

### Lifecycle Methods

6. **What are lifecycle methods in React?**  
   Lifecycle methods are hooks that allow you to run code at specific points in a component's life cycle (e.g., mounting, updating, unmounting). Common lifecycle methods in class components include `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

7. **What is the purpose of the `useEffect` hook?**  
   The `useEffect` hook is used in functional components to handle side effects, such as data fetching, subscriptions, or manual DOM manipulations. It runs after the component renders and can be configured to run only when certain dependencies change.

### Handling Events

8. **How do you handle events in React?**  
   Events in React are handled using camelCase syntax. You pass an event handler function as a prop:

   ```jsx
   function handleClick() {
     console.log("Button clicked");
   }

   return <button onClick={handleClick}>Click me</button>;
   ```

9. **What is the difference between controlled and uncontrolled components?**
   - **Controlled Components:** Form elements whose value is controlled by React through state. The state is the single source of truth.
   - **Uncontrolled Components:** Form elements that maintain their own state. React does not control their values directly.

### Conditional Rendering

10. **How do you conditionally render components in React?**  
    You can use JavaScript expressions, such as conditional statements or the ternary operator, to render components based on a condition:

    ```jsx
    {
      isLoggedIn ? <UserGreeting /> : <GuestGreeting />;
    }
    ```

11. **What are higher-order components (HOCs)?**  
    HOCs are functions that take a component as an argument and return a new component, enhancing the original component with additional behavior or data. They are a pattern for reusing component logic.

### React Router

12. **What is React Router?**  
    React Router is a library for routing in React applications. It allows you to create single-page applications with multiple views and navigation between them without refreshing the page.

13. **How do you create a route in React Router?**  
    You use the `Route` component to define a route:

    ```jsx
    import { BrowserRouter as Router, Route } from "react-router-dom";

    function App() {
      return (
        <Router>
          <Route path="/" component={Home} />
          <Route path="/about" component={About} />
        </Router>
      );
    }
    ```

### Hooks

14. **What are React hooks?**  
    Hooks are functions that allow you to use state and lifecycle features in functional components. The most commonly used hooks are `useState`, `useEffect`, and `useContext`.

15. **What is the `useContext` hook?**  
    The `useContext` hook allows you to access context values directly within functional components without wrapping them in a `Consumer` component. It is used to share data across the component tree without passing props down manually.

### Performance Optimization

16. **How do you optimize performance in a React application?**  
    Performance can be optimized by:

    - Using `React.memo` to prevent unnecessary re-renders of functional components.
    - Using the `shouldComponentUpdate` lifecycle method or `PureComponent` for class components.
    - Splitting code with React.lazy and Suspense for lazy loading components.

17. **What is the purpose of the `key` prop in React?**  
    The `key` prop is a unique identifier for elements in a list. It helps React identify which items have changed, been added, or removed, optimizing the rendering process.

### Testing

18. **How do you test React components?**  
    React components can be tested using libraries like Jest and React Testing Library. You can test component rendering, behavior, and user interactions by simulating events and asserting expected outcomes.

19. **What is the purpose of `React.StrictMode`?**  
    `React.StrictMode` is a wrapper component that helps identify potential problems in an application during development. It activates additional checks and warnings for its descendants.

### Problem-Solving Questions

20. **How would you handle form validation in React?**  
    You can handle form validation by using state to manage input values and error messages. You can check input validity on change or on form submission and provide feedback to the user.

21. **Write a simple counter component using React.**

    ```jsx
    import React, { useState } from "react";

    function Counter() {
      const [count, setCount] = useState(0);

      return (
        <div>
          <p>Count: {count}</p>
          <button onClick={() => setCount(count + 1)}>Increment</button>
          <button onClick={() => setCount(count - 1)}>Decrement</button>
        </div>
      );
    }
    ```

### Behavioral Questions

22. **Tell me about a challenging problem you faced in a React project and how you solved it.**  
    (Use the STAR method to structure your response.)
    - **Situation:** Briefly describe the context of the project.
    - **Task:** Explain your responsibility in the project.
    - **Action:** Describe the specific steps you took to address the challenge.
    - **Result:** Share the outcome of your actions and any learnings.

## Advanced Concepts

1. **What is the virtual DOM?**  
   The virtual DOM is a lightweight copy of the real DOM. React creates a virtual representation of the UI and compares it to the real DOM. When changes occur, React calculates the difference (or "diffing") and updates only the parts of the DOM that changed, improving performance.

2. **What is reconciliation in React?**  
   Reconciliation is the process by which React updates the DOM with the minimum number of changes needed. When a component's state changes, React re-renders the component and compares the new virtual DOM with the previous one to identify changes.

3. **Explain the significance of keys in lists.**  
   Keys help React identify which items have changed, are added, or are removed. They should be unique among siblings to ensure that React can optimize re-renders efficiently.

4. **What are Fragments in React?**  
   Fragments are used to group multiple elements without adding extra nodes to the DOM. You can use `<Fragment>` or the shorthand `<>` syntax to create fragments.

5. **What is the difference between a functional component and a class component?**
   - **Functional Component:** A stateless component that is a plain JavaScript function. It can use hooks for managing state and lifecycle.
   - **Class Component:** A component defined using ES6 class syntax, which can hold state and lifecycle methods. However, the trend is moving towards functional components with hooks.

### Hooks and State Management

6. **What is the `useReducer` hook?**  
   The `useReducer` hook is a React hook used for managing complex state logic. It works similarly to `useState` but provides a way to handle state transitions based on actions, similar to Redux:

   ```jsx
   const [state, dispatch] = useReducer(reducer, initialState);
   ```

7. **What are custom hooks in React?**  
   Custom hooks are user-defined functions that allow you to encapsulate reusable stateful logic. They start with the `use` prefix and can call built-in hooks inside them.

8. **What is the Context API?**  
   The Context API is a feature that allows you to share data globally across components without passing props through every level of the component tree. It is useful for managing global state or themes.

### Performance Optimization

9. **How do you optimize a React application for performance?**

   - Use code splitting with `React.lazy` and `Suspense` for lazy loading components.
   - Memoize components using `React.memo` to prevent unnecessary re-renders.
   - Optimize state management to minimize updates and component re-renders.
   - Avoid inline functions and objects in render methods.

10. **What is the purpose of the `React.memo` function?**  
    `React.memo` is a higher-order component that memoizes a functional component, preventing it from re-rendering if its props haven't changed.

### Routing

11. **What is the difference between `BrowserRouter` and `HashRouter`?**

    - **BrowserRouter:** Uses the HTML5 history API to manage routes without the hash in the URL. It requires server-side configuration to handle routes.
    - **HashRouter:** Uses the hash portion of the URL for routing. It doesn't require server-side configuration, but URLs may be less clean.

12. **How do you pass parameters in a route using React Router?**  
    You can pass parameters using the `:paramName` syntax in the route path and access them with `useParams`:
    ```jsx
    <Route path="/user/:id" component={User} />;
    // Inside the User component
    const { id } = useParams();
    ```

### Form Handling

13. **How do you handle form submissions in React?**  
    You can handle form submissions by creating a submit handler function and attaching it to the form's `onSubmit` event:

    ```jsx
    const handleSubmit = (event) => {
      event.preventDefault();
      // Handle form data
    };

    return <form onSubmit={handleSubmit}>...</form>;
    ```

14. **What is controlled vs. uncontrolled components in forms?**
    - **Controlled Components:** The input value is controlled by React state, providing a single source of truth.
    - **Uncontrolled Components:** The input value is managed by the DOM itself. React only accesses the input value when needed.

### Testing

15. **What are some common testing strategies for React applications?**  
    Common strategies include:

    - Unit Testing: Testing individual components with Jest or Mocha.
    - Integration Testing: Testing interactions between components and APIs.
    - End-to-End Testing: Testing the entire application flow with tools like Cypress or Selenium.

16. **What is Jest, and how does it relate to React?**  
    Jest is a JavaScript testing framework commonly used for testing React applications. It supports snapshot testing, mocking, and asynchronous testing.

### State Management

17. **What is Redux, and how does it work with React?**  
    Redux is a state management library that provides a centralized store for the application state. It uses actions to describe state changes and reducers to specify how the state should change based on those actions. React-Redux is the official binding library that integrates Redux with React components.

18. **Explain the concept of middleware in Redux.**  
    Middleware in Redux is a way to extend the store's capabilities, allowing you to handle asynchronous actions (like API calls) or logging. Common middleware includes Redux Thunk and Redux Saga.

### Miscellaneous

19. **What are error boundaries in React?**  
    Error boundaries are components that catch JavaScript errors in their child component tree and provide a fallback UI instead of crashing the application. They can be implemented using the `componentDidCatch` lifecycle method or `getDerivedStateFromError`.

20. **How do you handle authentication in a React application?**  
    Authentication can be handled using context and state management to track the user's logged-in state. You can use libraries like Firebase or Auth0 for authentication services.

### Behavioral Questions

21. **Describe a project where you used React and the challenges you faced.**  
    (Use the STAR method to structure your response.)

    - **Situation:** Briefly describe the context of the project.
    - **Task:** Explain your responsibility in the project.
    - **Action:** Describe the specific steps you took to address the challenge.
    - **Result:** Share the outcome of your actions and any learnings.

22. **How do you keep up with the latest React updates and best practices?**  
    Discuss how you follow blogs, documentation, community forums, and attend meetups or webinars to stay current with React developments.

### Coding Questions

23. **Implement a simple todo list application using React.**  
    Outline the structure, components (e.g., `TodoList`, `TodoItem`, `AddTodo`), and manage state with hooks.

24. **Create a component that fetches data from an API.**

    ```jsx
    import React, { useEffect, useState } from "react";

    function DataFetchingComponent() {
      const [data, setData] = useState([]);
      const [loading, setLoading] = useState(true);

      useEffect(() => {
        fetch("https://api.example.com/data")
          .then((response) => response.json())
          .then((data) => {
            setData(data);
            setLoading(false);
          });
      }, []);

      if (loading) return <div>Loading...</div>;
      return (
        <ul>
          {data.map((item) => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      );
    }
    ```

### Basic Questions About Hooks

1. **What are React hooks?**  
   React hooks are functions that allow you to use state and lifecycle features in functional components. They enable you to manage component state, side effects, and context without using class components.

2. **What is the `useState` hook?**  
   The `useState` hook is a built-in React hook that allows you to add state to functional components. It returns an array containing the current state value and a function to update that state:

   ```jsx
   const [count, setCount] = useState(0);
   ```

3. **What is the `useEffect` hook?**  
   The `useEffect` hook allows you to perform side effects in functional components, such as data fetching, subscriptions, or manual DOM manipulations. It runs after the component renders and can be configured to run based on dependencies:
   ```jsx
   useEffect(() => {
     // Side effect code here
   }, [dependencies]); // Runs when dependencies change
   ```

### Advanced Hook Concepts

4. **What is the `useContext` hook?**  
   The `useContext` hook is used to access values from a React context directly in functional components. It simplifies consuming context without needing to wrap components in a `Consumer`:

   ```jsx
   const value = useContext(MyContext);
   ```

5. **What is the `useReducer` hook, and when would you use it?**  
   The `useReducer` hook is a built-in hook that manages complex state logic in functional components. It is particularly useful when you have multiple state variables that depend on each other or when the state transition logic is complex:

   ```jsx
   const [state, dispatch] = useReducer(reducer, initialState);
   ```

6. **What are custom hooks?**  
   Custom hooks are functions that allow you to extract and reuse stateful logic across multiple components. They start with the `use` prefix and can call other hooks:
   ```jsx
   function useFetch(url) {
     const [data, setData] = useState(null);
     useEffect(() => {
       fetch(url)
         .then((response) => response.json())
         .then(setData);
     }, [url]);
     return data;
   }
   ```

### Performance and Optimization

7. **How do you optimize performance with hooks?**  
   Performance can be optimized using:

   - `React.memo` to prevent re-renders of memoized components.
   - `useCallback` to memoize functions and prevent unnecessary re-creations.
   - `useMemo` to memoize expensive calculations and return cached values unless dependencies change.

8. **What is the `useCallback` hook?**  
   The `useCallback` hook returns a memoized version of a callback function that only changes if one of its dependencies has changed. It helps to optimize performance by preventing unnecessary re-renders:

   ```jsx
   const memoizedCallback = useCallback(() => {
     // Function logic here
   }, [dependencies]);
   ```

9. **What is the `useMemo` hook?**  
   The `useMemo` hook is used to memoize the result of a computation and recompute it only when dependencies change. It can be helpful for optimizing performance in complex calculations:
   ```jsx
   const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
   ```

### Common Use Cases

10. **How do you handle cleanup with `useEffect`?**  
    You can return a cleanup function from the `useEffect` hook to clean up resources like subscriptions or timers when the component unmounts or before the effect re-runs:

    ```jsx
    useEffect(() => {
      const timer = setTimeout(() => {
        // Side effect code
      }, 1000);
      return () => clearTimeout(timer); // Cleanup function
    }, []);
    ```

11. **Can you use hooks in class components?**  
    No, hooks can only be used in functional components. Class components cannot use hooks directly. If you need similar functionality, you can refactor the class component into a functional component.

12. **What is the rules of hooks?**  
    There are two main rules for using hooks:
    - **Only call hooks at the top level:** Do not call hooks inside loops, conditions, or nested functions to ensure that hooks are called in the same order on every render.
    - **Only call hooks from React functions:** Hooks can only be called from functional components or custom hooks.

### Error Handling and Best Practices

13. **How do you handle errors in `useEffect`?**  
    You can handle errors in `useEffect` by using a try-catch block within an asynchronous function or by using `.catch()` on promises:

    ```jsx
    useEffect(() => {
      const fetchData = async () => {
        try {
          const response = await fetch(url);
          const data = await response.json();
          // Handle data
        } catch (error) {
          // Handle error
        }
      };
      fetchData();
    }, [url]);
    ```

14. **What are some common pitfalls when using hooks?**  
    Common pitfalls include:
    - Not following the rules of hooks (calling hooks conditionally or inside loops).
    - Forgetting to specify dependencies in `useEffect`, which can lead to stale values or infinite loops.
    - Overusing state and hooks when simpler solutions exist.

### Coding Questions Related to Hooks

15. **Create a simple counter using hooks.**

    ```jsx
    import React, { useState } from "react";

    function Counter() {
      const [count, setCount] = useState(0);
      return (
        <div>
          <p>Count: {count}</p>
          <button onClick={() => setCount(count + 1)}>Increment</button>
          <button onClick={() => setCount(count - 1)}>Decrement</button>
        </div>
      );
    }
    ```

16. **Implement a custom hook to fetch data from an API.**

    ```jsx
    import { useState, useEffect } from "react";

    function useFetch(url) {
      const [data, setData] = useState(null);
      const [loading, setLoading] = useState(true);
      const [error, setError] = useState(null);

      useEffect(() => {
        const fetchData = async () => {
          try {
            const response = await fetch(url);
            if (!response.ok) throw new Error("Network response was not ok");
            const result = await response.json();
            setData(result);
          } catch (error) {
            setError(error);
          } finally {
            setLoading(false);
          }
        };
        fetchData();
      }, [url]);

      return { data, loading, error };
    }
    ```

### Behavioral Questions

17. **Describe a situation where you used hooks to solve a problem.**  
    (Use the STAR method to structure your response.)
    - **Situation:** Explain the context of the project and the problem.
    - **Task:** Describe your role and responsibilities.
    - **Action:** Detail the specific actions you took using hooks to solve the problem.
    - **Result:** Share the outcome and what you learned.

---
