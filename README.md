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

                => Why use it:
                It makes the code more efficient when you have many child elements or when elements are added dynamically (after the page loads).
                It also reduces the number of event listeners, which improves performance.

                => Example: Imagine you have a list of buttons, and you want to handle clicks on all of them.
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

    => Event Bubbling: moves (or "bubbles") up through
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

    => In Short:
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
11. Lifecycle Methods of React JS Components & Order?
12. Difference between Pure Components vs High Order Components?
13. Difference between State vs Props vs Refs?
14. What are the latest versions of Reactjs and new features?
15. Difference between Class-based vs Function/hooks-based components?
16. What are Fragments in ReactJs?
17. How can you maintain the State of an app in complex applications?
18. Have you thought about implementing 2-way data binding?
19. What does async await get compiled into?
20. How to call 5 APIs in parallel and do something after all 5 responses have come?
21. Divide a website Ui into small components for JS framework.
22. What happens in the background when I enter a website URL in the browser and hit enter?
