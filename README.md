# Front Interview Questions

1.  What are new tags in HTML5?
    => Structural and Semantic Tags :
    <header> <Footer> <nav> <aside> <video> <main> <details>
    => Interactive and Multimedia Tags :
    <audio> <video> <track>
     =>Form-Related Tags : 
     <datalist> <output>

2.  Should we Inject Div inside a Span tag? Will Html give an error?
    => No, we shouldn’t put a <div> inside a <span> because <span> is for inline content, and <div> is for block-level content. It won’t give an error but can break the layout or styling.

3.  How to make a website responsive using CSS?
    => Use REM for Font Sizes: Scales well for responsiveness.
    => Media Queries: Set breakpoints for different devices.
    => Responsive CSS Classes: Use pre-defined classes or create your own with media queries (like Bootstrap classes).

4.  5 ways to center align an image inside a div element?
    => Flexbox: Use display: flex; justify-content: center; align-items: center; on the parent div.
    => Text-Align: Set text-align: center; on the parent div (works for inline elements like images).
    => Grid: Use display: grid; place-items: center; on the parent div.
    => Margin Auto: Set display: block; margin: auto; on the image.
    => Positioning: Use position: absolute; with top: 50%; left: 50%; transform: translate(-50%, -50%); on the image.

5.  What to use px vs rem vs em ?
    => px: For fixed, unchanging sizes (e.g., borders, icons).
    => rem: For scalable sizes based on the root font size, great for responsiveness.
    => em: For sizes relative to the parent element's font size, useful for nested elements.

6.  Name all basic data types of Javascript?
    => String: Represents text (e.g., "Hello").
    =>Number: Represents numbers (e.g., 42, 3.14).
    =>BigInt: Represents large integers (e.g., 9007199254740991n).
    =>Boolean: Represents true or false (e.g., true, false).
    =>Undefined: Represents an uninitialized variable (e.g., let x;).
    =>Null: Represents no value or empty value (e.g., null).
    =>Symbol: Represents a unique value (e.g., Symbol('id')).
    =>Object: Represents complex data structures (e.g., { key: 'value' }).

7.  What is Event Delegation & Event bubbling?
    => Event Delegation:
    What it means: Instead of adding individual event listeners to each child element, you add a single event listener to the parent element. The parent listens for events that happen on its child elements.

                - Why use it:
                It makes the code more efficient when you have many child elements or when elements are added dynamically (after the page loads).
                It also reduces the number of event listeners, which improves performance.

                - Example: Imagine you have a list of buttons, and you want to handle clicks on all of them.
                   <!-- HTML -->

                    <div id="parent">
                     <button class="child">Button 1</button>
                     <button class="child">Button 2</button>
                     <button class="child">Button 3</button>

                   </div>

                   <!-- JS -->
                   Instead of adding a click event to each button, you add it to the parent div.

                    document.getElementById('parent').addEventListener('click', function(event) {
                    if (event.target && event.target.matches('.child')) {
                        alert('Button clicked: ' + event.target.textContent);
                    }
                    });

                    What happens:
                    Clicking any button inside the parent div will trigger the event. The parent listens for clicks on any child element (.child), even if new buttons are added later.

    - Event Bubbling: moves (or "bubbles") up through
      What it means: When you click an element, the event doesn’t stop there. It "bubbles up" from the clicked element to its parent, grandparent, and so on. Each parent element can handle the event if it has an event listener.

              => Why use it:
              It allows you to handle events at different levels of the DOM (document structure).
              You can control the flow of events by stopping the bubble at certain points.

              => Example: Imagine you have a button inside a div, and both the button and the div have event listeners.
              =<!-- HTML -->
              <div id="parent">
              <button id="child">Click me</button>
              </div>

                  <!-- javascript -->
                  // Event listener for the div
                  document.getElementById('parent').addEventListener('click', function() {
                  alert('Parent clicked!');
                  });

                  // Event listener for the button
                  document.getElementById('child').addEventListener('click', function() {
                  alert('Button clicked!');
                  });

                  What happens:
                  When you click the button, the button’s alert shows up first: Button clicked!.
                  Then, the event bubbles up to the parent div, and its alert shows up: Parent clicked!.
                  This is event bubbling—the event starts at the child (button) and then bubbles up to the parent (div).

8.  What are closures? Uses of Closures?
    => What are Closures?
    A closure is a function that remembers and uses variables from its surrounding function even after that function has finished running.
    <!-- EXAMPLE -->

        function outer() {
        let message = 'Hello, world!'; // Variable in outer function
        return function inner() {
        console.log(message); // inner function can access message
        };
        }

        const closureFunction = outer(); // outer function runs and returns the inner function
        closureFunction(); // Outputs: Hello, world!

    - In Short:
      Closure = A function that remembers its surrounding variables.
      Why use it? It helps keep data private, create flexible functions, and handle events.

9.  What is the need for JS Frameworks?
    => JavaScript frameworks make coding faster and easier by providing tools and ready-made solutions. They help manage big projects, save time, and ensure your app works smoothly on all browsers.

    1. Faster Development: Reuse built-in tools instead of writing everything from scratch.
    2. Better Code Structure: Keep code clean, organized, and easy to manage.
    3. Simplified Complex Tasks: Frameworks simplify tasks like:
       Data binding
       DOM manipulation
       API integration
    4. Scalability: Handle small and big apps easily.
    5. Built-In Features: Get routing, state management, and more without extra work.
       Example: Instead of manually updating the UI, React does it automatically with its Virtual DOM

10. How do JS frameworks work in the background?
    => **Short Answer:**  
     JS frameworks (like React, Angular, or Vue) work by providing a structured way to build web applications. They use a **virtual DOM** (in React) or **data binding** (in Angular/Vue) to efficiently update the UI when data changes, reducing direct DOM manipulation for better performance.

    **Example:**  
     In React, when state changes, it creates a virtual DOM diff, updates only the changed parts in the real DOM, and re-renders efficiently.

11. Lifecycle Methods of React JS Components & Order?
    => Lifecycle methods help manage component creation, updates, and removal. They provide hooks
    for handling various events and states throughout a component's life cycle.

    1. Mounting Phase
       When a component is created and inserted into the DOM:

       - constructor()
       - static getDerivedStateFromProps()
       - render()
       - componentDidMount()

    2. Updating Phase
       When a component re-renders due to changes in props ~or state:

       - static getDerivedStateFromProps()
       - shouldComponentUpdate()
       - render()
       - getSnapshotBeforeUpdate()
       - componentDidUpdate()

    3. Unmounting Phase
       When a component is removed from the DOM:
       - componentWillUnmount()

12. Difference between Pure Components vs High Order Components?
    => Pure Components: These are React components that automatically check if they need to re-render. They only re-render if their props or state change, which helps improve performance.

    - Higher-Order Components (HOCs): These are functions that take a component and return a new, enhanced version of it. They are used to share common functionality between components, like adding extra features or data.

13. Difference between State vs Props vs Refs?
    => 1) State: Internal data that a component manages and can change (e.g., a counter value).

    - 2. Props: Data passed from a parent component to a child component. It’s read-only and can’t be changed by the child.
         Example: <Child name="John" /> (here, name is a prop).

    - 3.  Refs: A way to directly access and manipulate DOM elements (e.g., focusing an input field).
          Example: const inputRef = useRef();
          import React, { useRef } from 'react';

              function FocusInput() {
                  const inputRef = useRef(); // Create a ref

                  const focusInput = () => {
                      inputRef.current.focus(); // Focus the input field
                  };

                  return (
                      <div>
                          <input ref={inputRef} type="text" placeholder="Type here..." />
                          <button onClick={focusInput}>Focus Input</button>
                      </div>
                  );

    }
    What Happens Here:

    1. inputRef is created using useRef().
    2. The ref={inputRef} attaches the ref to the input field.
    3. When you click the button, inputRef.current.focus() makes the input field active, so you can type without clicking on it.

14. What are the latest versions of Reactjs and new features?
    => As of October 2023, the latest stable version of React is React 18. Here are the key features and updates:

    1. Concurrent Rendering:
       React can now do many tasks at the same time, making your app faster and smoother.
    2. Automatic Batching:
       React groups multiple updates into one, so your app doesn’t waste time re-rendering too often.
    3. New Hooks:
       1. useId: Creates unique IDs for things like labels.
       2. useTransition: Helps React focus on important updates first.
    4. Suspense for Data Fetching:
       Lets your app show a loading spinner while waiting for data to load.

15. Difference between Class-based vs Function/hooks-based components?
    => Class-Based Components:

    1. Use JavaScript classes.
    2. Require this keyword to access props and state.
    3. Use lifecycle methods like componentDidMount, componentDidUpdate, etc.
    4. More code and harder to read.

    - Function/Hooks-Based Components:

    1. Use plain JavaScript functions.
    2. Use hooks like useState and useEffect for state and lifecycle.
    3. Simpler, cleaner, and easier to read.
    4. Modern and recommended way to write React components.

16. What are Fragments in ReactJs?
    => Fragments in React help to group multiple elements without adding extra <div> tags in the HTML.

    - Why Use Fragments?
      1. If we don’t use fragments, React forces us to wrap elements inside a <div>, which can create extra unwanted HTML tags.
      1. Fragments keep the HTML clean and improve performance by reducing unnecessary elements in the DOM.

17. How can you maintain the State of an app in complex applications?
    =>

          - Local Component State
            For simple cases, use useState inside a component.
            Example :
            import React, { useState } from 'react';

                function Counter() {
                    const [count, setCount] = useState(0);

                    return (
                        <div>
                        <p>{count}</p>
                        <button onClick={() => setCount(count + 1)}>Increment</button>
                        </div>
                    );

            }

    - Lifting State Up
      When multiple components need access to the same state, lift state up to a common parent.
      Example :
      function Parent() {
      const [count, setCount] = useState(0);

      return (
      <Child count={count} setCount={setCount} />
      );

      }

      function Child({ count, setCount }) {
      return <button onClick={() => setCount(count + 1)}>Increment</button>;
      }

    - Context API
      For global state, React Context can be used to pass state through the app without prop drilling.
      Example :
      const CountContext = React.createContext();

            function App() {
            const [count, setCount] = useState(0);

            return (
                <CountContext.Provider value={{ count, setCount }}>
                <Counter />
                </CountContext.Provider>
            );
            }

            function Counter() {
                const { count, setCount } = useContext(CountContext);
                return <button onClick={() => setCount(count + 1)}>{count}</button>;
            }

    - State Management Libraries (Redux)
      For large apps, use libraries like Redux to manage state globally.
      Example (Redux):
      import { createStore } from 'redux';

            const store = createStore((state = 0, action) => {
                if (action.type === 'INCREMENT') return state + 1;
                return state;
            });

            function Counter() {
                const count = store.getState();
                return <button onClick={() => store.dispatch({ type: 'INCREMENT' })}>{count}</button>;
            }

18. Have you thought about implementing 2-way data binding?
    =>
    Two-Way Data Binding in React
    In React, two-way data binding means syncing data between the state and UI. When you change the state, the UI updates automatically, and when you change the UI (like typing in an input), the state updates too.

        - How to Implement:
          - State is tied to the input field using the value prop.
          - Input change is handled using the onChange event to update the state.

        Example:

        import React, { useState } from 'react';

            function TwoWayBinding() {
            const [inputValue, setInputValue] = useState('');

            // Update state on input change
            const handleChange = (event) => {
                setInputValue(event.target.value);
            };

            return (
                <div>
                <input
                    type="text"
                    value={inputValue}       // Sync state with input
                    onChange={handleChange}  // Update state on user input
                />
                <p>You typed: {inputValue}</p>
                </div>
            );
            }

        export default TwoWayBinding;

19. What does async await get compiled into?
    =>
    - When you use async/await in JavaScript, it gets converted into Promises and .then() functions for older JavaScript versions.
    -
20. How to call 5 APIs in parallel and do something after all 5 responses have come?
    => To call 5 APIs in parallel and do something after all 5 responses have come, you can use Promise.all(). This method allows you to wait for all promises (API calls) to resolve before proceeding with the next step.
21. Divide a website Ui into small components for JS framework. 22. What happens in the background when I enter a website URL in the browser and hit enter?

# YOUTUBE LINK

    1.https://www.youtube.com/watch?v=CLVevQBbSUU&t=1608s
    2. https://youtu.be/QmfyWw3Cth8?si=wENiikM7lWjDFnhG
