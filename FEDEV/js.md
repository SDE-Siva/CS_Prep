# JavaScript

### Basic Questions

1. **What is JavaScript?**  
   JavaScript is a high-level, interpreted programming language primarily used to create interactive and dynamic content on web pages. It is a core technology of the web, along with HTML and CSS.

2. **What are the data types supported by JavaScript?**  
   JavaScript supports several data types:

   - **Primitive Types:** Undefined, Null, Boolean, Number, BigInt, String, and Symbol.
   - **Reference Types:** Objects, Arrays, and Functions.

3. **What is the difference between `==` and `===`?**

   - `==` (loose equality) compares values for equality after converting them to a common type.
   - `===` (strict equality) compares both value and type without any type conversion.

4. **What are functions in JavaScript?**  
   Functions are reusable blocks of code that perform a specific task. They can be defined using function declarations, function expressions, or arrow functions:

   ```javascript
   function add(a, b) {
     return a + b;
   }
   ```

5. **What is an IIFE (Immediately Invoked Function Expression)?**  
   An IIFE is a function that is executed immediately after its creation. It is often used to create a new scope and avoid polluting the global namespace:
   ```javascript
   (function () {
     console.log("IIFE executed!");
   })();
   ```

### Advanced Concepts

6. **What is hoisting in JavaScript?**  
   Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during compilation. This means you can use functions and variables before they are declared:

   ```javascript
   console.log(x); // undefined
   var x = 5;
   ```

7. **Explain closures in JavaScript.**  
   A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope. It allows you to create private variables:

   ```javascript
   function outerFunction() {
     let outerVariable = "I am outside!";
     return function innerFunction() {
       console.log(outerVariable);
     };
   }
   const innerFunc = outerFunction();
   innerFunc(); // "I am outside!"
   ```

8. **What is the purpose of `this` in JavaScript?**  
   `this` refers to the context in which a function is executed. Its value can vary based on how a function is called:
   - In a method, it refers to the object it belongs to.
   - In a regular function, it refers to the global object (or `undefined` in strict mode).
   - In an arrow function, it lexically binds `this` from the enclosing context.

### Asynchronous JavaScript

9. **What are callbacks in JavaScript?**  
   A callback is a function passed as an argument to another function, which is executed after a certain event or condition is met. It’s commonly used for handling asynchronous operations:

   ```javascript
   function fetchData(callback) {
     // Simulate fetching data
     setTimeout(() => {
       callback("Data received!");
     }, 1000);
   }
   fetchData((data) => console.log(data)); // "Data received!"
   ```

10. **What are Promises in JavaScript?**  
    A Promise is an object representing the eventual completion or failure of an asynchronous operation. It can be in one of three states: pending, fulfilled, or rejected. Promises provide a cleaner way to handle asynchronous code:

    ```javascript
    const myPromise = new Promise((resolve, reject) => {
      // Simulate async operation
      setTimeout(() => {
        resolve("Operation succeeded!");
      }, 1000);
    });
    myPromise.then((result) => console.log(result)); // "Operation succeeded!"
    ```

11. **What are async/await in JavaScript?**  
    `async/await` is a syntax for working with Promises that makes asynchronous code easier to read and write. An `async` function always returns a Promise, and you can use `await` to pause execution until the Promise is resolved:
    ```javascript
    async function fetchData() {
      const result = await myPromise; // Wait for the Promise to resolve
      console.log(result);
    }
    fetchData(); // "Operation succeeded!"
    ```

### Object-Oriented JavaScript

12. **What is prototypal inheritance?**  
    Prototypal inheritance is a feature in JavaScript where objects can inherit properties and methods from other objects. It allows for shared behavior among objects:

    ```javascript
    function Person(name) {
      this.name = name;
    }
    Person.prototype.greet = function () {
      console.log(`Hello, my name is ${this.name}`);
    };
    const john = new Person("John");
    john.greet(); // "Hello, my name is John"
    ```

13. **What are ES6 classes?**  
    ES6 introduced class syntax for creating objects and inheritance. Classes are syntactical sugar over JavaScript’s existing prototypal inheritance:
    ```javascript
    class Animal {
      constructor(name) {
        this.name = name;
      }
      speak() {
        console.log(`${this.name} makes a noise.`);
      }
    }
    class Dog extends Animal {
      speak() {
        console.log(`${this.name} barks.`);
      }
    }
    const dog = new Dog("Rex");
    dog.speak(); // "Rex barks."
    ```

### Miscellaneous

14. **What is the difference between `null` and `undefined`?**

    - `undefined` means a variable has been declared but has not yet been assigned a value.
    - `null` is an assignment value that represents the intentional absence of any object value.

15. **Explain the concept of the event loop in JavaScript.**  
    The event loop is a mechanism that allows JavaScript to perform non-blocking I/O operations by using a single-threaded model. It manages the execution of code, collecting and processing events, and executing queued sub-tasks:

    - The call stack executes synchronous code.
    - The event loop checks the message queue for pending tasks and executes them after the call stack is empty.

16. **What are the different ways to declare variables in JavaScript?**  
    JavaScript provides three keywords to declare variables:
    - `var`: Function-scoped or globally scoped. Can be re-declared and updated.
    - `let`: Block-scoped. Can be updated but not re-declared in the same scope.
    - `const`: Block-scoped. Cannot be updated or re-declared. Used for constants.

### Coding Questions

17. **Write a function to reverse a string.**

    ```javascript
    function reverseString(str) {
      return str.split("").reverse().join("");
    }
    console.log(reverseString("hello")); // "olleh"
    ```

18. **Implement a function that checks if a number is prime.**

    ```javascript
    function isPrime(num) {
      if (num <= 1) return false;
      for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false;
      }
      return true;
    }
    console.log(isPrime(5)); // true
    ```

19. **Create a function that removes duplicates from an array.**
    ```javascript
    function removeDuplicates(arr) {
      return [...new Set(arr)];
    }
    console.log(removeDuplicates([1, 2, 2, 3, 4, 4])); // [1, 2, 3, 4]
    ```

### Behavioral Questions

20. **Describe a challenging project you worked on with JavaScript.**  
    (Use the STAR method to structure your response.)
    - **Situation:** Explain the context of the project and the challenge.
    - **Task:** Describe your role and responsibilities.
    - **Action:** Detail the specific actions you took to address the challenge.
    - **Result:** Share the outcome and what you learned.

### Basic JavaScript Questions

1. **What are JavaScript functions as first-class citizens?**  
   Functions in JavaScript are treated as first-class citizens, meaning they can be assigned to variables, passed as arguments to other functions, returned from functions, and stored in data structures.

2. **What is the difference between a function declaration and a function expression?**

   - **Function Declaration:** Defined with the `function` keyword and hoisted to the top of their scope.
     ```javascript
     function greet() {
       console.log("Hello!");
     }
     ```
   - **Function Expression:** Created when you define a function within an expression and are not hoisted.
     ```javascript
     const greet = function () {
       console.log("Hello!");
     };
     ```

3. **What is the scope in JavaScript?**  
   Scope refers to the current context of execution in which values and expressions are visible or accessible. JavaScript has two main types of scope:

   - **Global Scope:** Variables defined outside of any function.
   - **Local Scope:** Variables defined within a function.

4. **What is the difference between `let`, `const`, and `var`?**

   - `var`: Function-scoped or globally scoped, can be redeclared and updated.
   - `let`: Block-scoped, can be updated but not redeclared in the same scope.
   - `const`: Block-scoped, must be initialized at declaration, cannot be updated or redeclared.

5. **What is the spread operator?**  
   The spread operator (`...`) allows an iterable (like an array) to be expanded in places where zero or more arguments or elements are expected. It is commonly used for merging arrays or objects.
   ```javascript
   const arr1 = [1, 2];
   const arr2 = [3, 4];
   const combined = [...arr1, ...arr2]; // [1, 2, 3, 4]
   ```

### Intermediate JavaScript Questions

6. **What is the difference between an object and an array?**

   - An **object** is a collection of key-value pairs, where keys are strings (or Symbols) and values can be any type.
   - An **array** is a special type of object that is an ordered list of values, accessible via numeric indices.

7. **Explain how `this` behaves in different contexts.**

   - In a regular function, `this` refers to the global object (or `undefined` in strict mode).
   - In an object method, `this` refers to the object the method is called on.
   - In a constructor function, `this` refers to the newly created object.
   - In an arrow function, `this` is lexically bound, meaning it inherits `this` from the enclosing scope.

8. **What is event delegation in JavaScript?**  
   Event delegation is a technique where you attach a single event listener to a parent element to manage events for multiple child elements. This improves performance and simplifies code:

   ```javascript
   document
     .getElementById("parent")
     .addEventListener("click", function (event) {
       if (event.target.matches("button")) {
         console.log("Button clicked!");
       }
     });
   ```

9. **What are template literals?**  
   Template literals are string literals that allow embedded expressions and multi-line strings. They use backticks (`` ` ``) instead of quotes:

   ```javascript
   const name = "John";
   const greeting = `Hello, ${name}!`; // "Hello, John!"
   ```

10. **What is the purpose of the `bind`, `call`, and `apply` methods?**  
    These methods are used to control the `this` context of a function:
    - `bind()`: Creates a new function that, when called, has its `this` keyword set to the provided value.
    - `call()`: Calls a function with a specified `this` value and arguments provided individually.
    - `apply()`: Calls a function with a specified `this` value and arguments provided as an array.

### Advanced JavaScript Questions

11. **What is the difference between synchronous and asynchronous programming?**

    - **Synchronous programming:** Code execution happens line by line, and each operation must complete before the next one starts.
    - **Asynchronous programming:** Allows code to run in the background, enabling operations to happen simultaneously. This is essential for tasks like network requests.

12. **What are JavaScript modules?**  
    JavaScript modules are reusable pieces of code that can export and import functionality between different files. This helps in organizing code and avoiding name collisions:

    ```javascript
    // module.js
    export const myFunction = () => {
      console.log("Hello from module!");
    };

    // main.js
    import { myFunction } from "./module.js";
    myFunction(); // "Hello from module!"
    ```

13. **What is the `instanceof` operator?**  
    The `instanceof` operator tests whether an object is an instance of a specific constructor or class. It checks the prototype chain:

    ```javascript
    function Person() {}
    const john = new Person();
    console.log(john instanceof Person); // true
    ```

14. **Explain the concept of garbage collection in JavaScript.**  
    Garbage collection is an automatic memory management feature that removes objects that are no longer in use or accessible from the program. JavaScript uses a mark-and-sweep algorithm to identify and clean up unused objects.

15. **What is functional programming in JavaScript?**  
    Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. Key concepts include first-class functions, higher-order functions, and pure functions.

### Additional Coding Questions

16. **Write a function that flattens a nested array.**

    ```javascript
    function flattenArray(arr) {
      return arr.flat();
    }
    console.log(flattenArray([1, [2, [3, 4]], 5])); // [1, 2, 3, 4, 5]
    ```

17. **Create a debounce function.**  
    A debounce function limits the rate at which a function can fire. It's often used in scenarios like handling scroll events:

    ```javascript
    function debounce(func, delay) {
      let timeout;
      return function (...args) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, args), delay);
      };
    }
    ```

18. **Implement a function to find the longest word in a sentence.**

    ```javascript
    function findLongestWord(sentence) {
      const words = sentence.split(" ");
      return words.reduce((longest, current) => {
        return current.length > longest.length ? current : longest;
      }, "");
    }
    console.log(
      findLongestWord("The quick brown fox jumped over the lazy dog.")
    ); // "jumped"
    ```

19. **Write a function that merges two sorted arrays.**

    ```javascript
    function mergeSortedArrays(arr1, arr2) {
      let merged = [];
      let i = 0,
        j = 0;

      while (i < arr1.length && j < arr2.length) {
        if (arr1[i] < arr2[j]) {
          merged.push(arr1[i]);
          i++;
        } else {
          merged.push(arr2[j]);
          j++;
        }
      }
      return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
    }
    console.log(mergeSortedArrays([1, 3, 5], [2, 4, 6])); // [1, 2, 3, 4, 5, 6]
    ```

20. **Create a function that checks if a string is a palindrome.**
    ```javascript
    function isPalindrome(str) {
      const cleanedStr = str.replace(/[^A-Za-z0-9]/g, "").toLowerCase();
      return cleanedStr === cleanedStr.split("").reverse().join("");
    }
    console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
    ```

### Behavioral Questions

21. **Can you describe a time when you optimized JavaScript code?**  
    (Use the STAR method to structure your response.)

    - **Situation:** Explain the context of the project and the code that needed optimization.
    - **Task:** Describe your role and what you needed to achieve.
    - **Action:** Detail the steps you took to optimize the code (e.g., using caching, reducing complexity).
    - **Result:** Share the outcomes of your optimization and any metrics you have (e.g., performance improvements).

22. **How do you stay updated with the latest JavaScript features and best practices?**  
    (Discuss resources like blogs, courses, GitHub repositories, and community forums.)

---

# Web Development :

### Basic Concepts

1. **What is the Document Object Model (DOM)?**  
   The DOM is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as a tree of nodes, where each node corresponds to part of the document.

2. **How do you select elements in the DOM?**  
   You can select elements using various methods, such as:

   - `document.getElementById()`: Selects an element by its ID.
   - `document.getElementsByClassName()`: Selects elements by their class name.
   - `document.getElementsByTagName()`: Selects elements by their tag name.
   - `document.querySelector()`: Selects the first element that matches a CSS selector.
   - `document.querySelectorAll()`: Selects all elements that match a CSS selector.

3. **What are event listeners in JavaScript?**  
   Event listeners are functions that are executed when a specified event occurs on a particular element. You can add an event listener using the `addEventListener` method:

   ```javascript
   document.getElementById("myButton").addEventListener("click", function () {
     alert("Button clicked!");
   });
   ```

4. **What is event propagation?**  
   Event propagation refers to the way events travel through the DOM. There are two phases:

   - **Capturing phase:** The event starts from the root and travels down to the target element.
   - **Bubbling phase:** The event bubbles up from the target element back to the root.
     You can control this behavior by setting the `useCapture` parameter in `addEventListener`.

5. **What is AJAX?**  
   AJAX (Asynchronous JavaScript and XML) is a technique for creating asynchronous web applications. It allows you to send and receive data from a server asynchronously without refreshing the page. You can use the `XMLHttpRequest` object or the newer `fetch` API:
   ```javascript
   fetch("https://api.example.com/data")
     .then((response) => response.json())
     .then((data) => console.log(data));
   ```

### Intermediate Concepts

6. **What are Promises in JavaScript?**  
   Promises are objects that represent the eventual completion (or failure) of an asynchronous operation and its resulting value. They can be in one of three states: pending, fulfilled, or rejected. Promises help manage asynchronous operations more effectively:

   ```javascript
   const myPromise = new Promise((resolve, reject) => {
     setTimeout(() => {
       resolve("Data received!");
     }, 1000);
   });
   myPromise.then((result) => console.log(result)); // "Data received!"
   ```

7. **What is the `fetch` API?**  
   The `fetch` API is a modern interface for making HTTP requests in JavaScript. It returns a Promise that resolves to the Response object representing the response to the request:

   ```javascript
   fetch("https://api.example.com/data")
     .then((response) => response.json())
     .then((data) => console.log(data))
     .catch((error) => console.error("Error:", error));
   ```

8. **What are callbacks in JavaScript?**  
   Callbacks are functions that are passed as arguments to other functions and are executed after some operation has been completed. They are commonly used in asynchronous programming to handle results:

   ```javascript
   function fetchData(callback) {
     setTimeout(() => {
       callback("Data received!");
     }, 1000);
   }
   fetchData((data) => console.log(data)); // "Data received!"
   ```

9. **What is the purpose of the `this` keyword?**  
   The `this` keyword refers to the context in which a function is executed. Its value depends on how the function is called:

   - In a method, it refers to the object the method is called on.
   - In a regular function, it refers to the global object (or `undefined` in strict mode).
   - In an arrow function, `this` is lexically bound from the enclosing scope.

10. **What is the difference between local storage and session storage?**  
    Both are part of the Web Storage API used to store data in the browser:
    - **Local Storage:** Data persists even after the browser is closed and reopened. It has no expiration time.
    - **Session Storage:** Data is stored for the duration of the page session and is cleared when the page session ends (i.e., when the tab is closed).

### Advanced Concepts

11. **What are JavaScript modules?**  
    JavaScript modules allow you to split your code into separate files, promoting better organization and reuse. Modules can export functions, objects, or variables using `export` and can be imported using `import`:

    ```javascript
    // module.js
    export const myFunction = () => {
      console.log("Hello from module!");
    };

    // main.js
    import { myFunction } from "./module.js";
    myFunction(); // "Hello from module!"
    ```

12. **What is the difference between `call`, `apply`, and `bind`?**  
    These methods control the value of `this` in functions:

    - `call()`: Invokes the function with a specified `this` value and arguments provided individually.
    - `apply()`: Invokes the function with a specified `this` value and arguments provided as an array.
    - `bind()`: Returns a new function with a bound `this` value, which can be called later.

    ```javascript
    function greet(greeting) {
      console.log(`${greeting}, ${this.name}`);
    }
    const obj = { name: "Alice" };
    greet.call(obj, "Hello"); // "Hello, Alice"
    ```

13. **What is the event loop?**  
    The event loop is a mechanism that allows JavaScript to perform non-blocking I/O operations. It enables asynchronous behavior by managing the execution of code, collecting and processing events, and executing queued sub-tasks:

    - The call stack executes synchronous code.
    - The event loop checks the message queue for pending tasks and executes them after the call stack is empty.

14. **What is a closure?**  
    A closure is a function that retains access to its lexical scope, even when executed outside that scope. It allows you to create private variables:

    ```javascript
    function outerFunction() {
      let outerVariable = "I am outside!";
      return function innerFunction() {
        console.log(outerVariable);
      };
    }
    const innerFunc = outerFunction();
    innerFunc(); // "I am outside!"
    ```

15. **What are higher-order functions?**  
    Higher-order functions are functions that take other functions as arguments or return functions as their results. They are commonly used in functional programming:
    ```javascript
    function higherOrderFunction(callback) {
      return function () {
        console.log("Executing callback...");
        callback();
      };
    }
    const myCallback = () => console.log("Callback executed!");
    const result = higherOrderFunction(myCallback);
    result(); // "Executing callback..." "Callback executed!"
    ```

### Common Coding Challenges

16. **Write a function to debounce another function.**  
    Debouncing ensures that a function is not called too frequently, which is useful for events like scrolling or resizing:

    ```javascript
    function debounce(func, delay) {
      let timeout;
      return function (...args) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, args), delay);
      };
    }
    ```

17. **Create a function that throttles another function.**  
    Throttling ensures that a function is called at most once in a specified period:

    ```javascript
    function throttle(func, limit) {
      let lastFunc;
      let lastRan;
      return function (...args) {
        if (!lastRan) {
          func.apply(this, args);
          lastRan = Date.now();
        } else {
          clearTimeout(lastFunc);
          lastFunc = setTimeout(() => {
            if (Date.now() - lastRan >= limit) {
              func.apply(this, args);
              lastRan = Date.now();
            }
          }, limit - (Date.now() - lastRan));
        }
      };
    }
    ```

18. **Write a function to flatten a nested array.**

    ```javascript
    function flattenArray(arr) {
      return arr.reduce((flat, current) => {
        return flat.concat(
          Array.isArray(current) ? flattenArray(current) : current
        );
      }, []);
    }
    console.log(flattenArray([1, [2, [3, 4]], 5])); // [1, 2, 3, 4, 5]
    ```

19. **Implement a function to check if an object is empty.**

    ```javascript
    function isEmpty(obj) {
      return Object.keys(obj).length === 0;
    }
    console.log(isEmpty({})); // true
    console.log(isEmpty({ name: "John" })); // false
    ```

20. **Create a function to merge two objects.**
    ```javascript
    function mergeObjects(obj1, obj2) {
      return { ...obj1, ...obj2 };
    }
    console.log(mergeObjects({ a: 1 }, { b: 2 })); // { a: 1, b: 2 }
    ```

### Performance and Optimization

21. \*\*How can you improve the performance of a

web application?\*\*

- Minimize HTTP requests. - Use asynchronous loading for scripts. - Optimize images and assets. - Use a content delivery network (CDN). - Minify and bundle CSS and JavaScript files.

22. **What is lazy loading?**  
    Lazy loading is a design pattern that defers the loading of non-critical resources (like images or scripts) until they are needed. This helps improve initial load time and overall performance.

23. **How can you prevent memory leaks in JavaScript?**
    - Avoid global variables.
    - Clean up event listeners when they are no longer needed.
    - Use weak references where applicable.
    - Monitor performance and memory usage during development.

---
