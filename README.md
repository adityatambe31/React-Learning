# ReactJS Interview Preparation Notes

This document contains ReactJS concepts and examples to help you prepare for interviews. It covers the basics of components, JSX, state management, hooks, and more. These notes are derived from a YouTube tutorial and include important interview topics.

## Table of Contents

- [Components](#components)
- [JSX](#jsx)
- [Fragments](#fragments)
- [Expressions in JSX](#expressions-in-jsx)
- [Lists](#lists)
- [Props](#props)
- [Conditional Rendering](#conditional-rendering)
- [Logical and Ternary Operators](#logical-and-ternary-operators)
- [Styling in React](#styling-in-react)
- [Event Handling](#event-handling)
- [State Management and Hooks](#state-management-and-hooks)
- [useEffect Hook](#useeffect-hook)
- [Prop Drilling](#prop-drilling)
- [useContext Hook](#usecontext-hook)
- [useRef Hook](#useref-hook)

---

## Components

Components are independent, reusable bits of code that serve the same purpose as JavaScript functions but work in isolation and return HTML.

**Syntax:**
```javascript
function Component() {
    return (
        <div>Component</div>
    );
}

export default Component;

```
Example: 

```javascript
function VideoDescription() {
    return (
        <div>
            <h2>Video Title</h2>
            <p>Description of the video</p>
        </div>
    );
}
```
# JSX
JSX allows us to write HTML tags in React, making it easier to write and add HTML in React.

```javascript
function App() {
    return <h1>Hi Adi</h1>;
}

```

# Fragments
Fragments let you group a list of children without adding extra nodes to the DOM.

```javascript
function App() {
    return (
        <>
            <h1>Hi Adi</h1>
            <p>This is a paragraph</p>
        </>
    );
}
```

# Expressions in JSX
Expressions in JSX can be written inside curly braces. The expression can be a React variable, property, or any other JavaScript expression.

Example:

```javascript
const myName = "Aditya Tambe";
const multiply = (a, b) => a * b;
const specialClass = "Simple-class";

return (
    <>
        <h1>{myName}</h1>
        <h1>2 * 2 = {multiply(2, 2)}</h1>
        <p>Friends: {["Adi", "Vitaly"]}</p>
        <p className={specialClass}>This is a specialClass variable</p>
    </>
);
```

# Lists
Lists can be rendered using loops. The map() method is generally preferred.

Example:

```javascript
const userInfo = [
    { name: "Adi", email: "tambeaditya22@gmail.com" },
    { name: "Arya", email: "arya777@gmail.com" },
    { name: "Ali", email: "alibaba@gmail.com" },
];

return (
    <>
        {userInfo.map((user) => (
            <ul key={Math.random() * 10}>
                <li>{user.name}</li>
                <li>{user.email}</li>
            </ul>
        ))}
    </>
);
```
# Props
Props are arguments passed into React components via HTML attributes.

Example:

```javascript
const User = (props) => {
    return (
        <section>
            <img src={props.img} alt={props.name} />
            <h1>Name: {props.name}</h1>
            <h1>Hobbies: {props.hobbies}</h1>
            <h1>Age: {props.age}</h1>
        </section>
    );
};

function App() {
    return (
        <>
            <User
                name="Aditya"
                img="https://example.com/image.jpg"
                age={21}
                hobbies={["coding", "traveling"]}
            />
        </>
    );
}

export default App;

```

# Props Destructuring
You can destructure props for cleaner code.

Example:

``` javascript
const User = ({ img, name, age, hobbies }) => {
    return (
        <section>
            <img src={img} alt={name} />
            <h1>Name: {name}</h1>
            <h1>Hobbies: {hobbies}</h1>
            <h1>Age: {age}</h1>
        </section>
    );
};

```
# Conditional Rendering
Conditional rendering in React can be done using if-else statements or conditional (ternary) operators.

Example:

```javascript
const ValidPassword = () => <h1>Valid Password</h1>;
const InvalidPassword = () => <h1>Invalid Password</h1>;

const Password = ({ isValid }) => {
    return isValid ? <ValidPassword /> : <InvalidPassword />;
};

function App() {
    return (
        <>
            <Password isValid={true} />
        </>
    );
}

export default App;

```

# Logical and Ternary Operators
Logical operators like && can be used for conditional rendering.

Example:

``` javascript
const Cart = () => {
    const items = ["TWS", "Smartphones", "RAM", "Cabinets"];

    return (
        <>
            <h1>Cart 🛒</h1>
            {items.length > 0 && <h2>You have {items.length} items in your cart</h2>}
            <ul>
                {items.map((item) => (
                    <li key={Math.random()}>{item}</li>
                ))}
            </ul>
        </>
    );
};

```

# Styling in React

You can style React components using inline styles or external CSS.

Example:

```javascript
function App() {
    return (
        <section>
            <h1 style={{ color: "white", backgroundColor: "teal", padding: "2rem" }}>
                Inline Styling
            </h1>
        </section>
    );
}
export default App;

```

# Event Handling
Events in React are handled similarly to native HTML but use camelCase syntax.

Example:

```javascript
const Button = () => {
    const handleClick = () => {
        console.log("clicked");
        alert("You clicked me!");
    };

    return <button onClick={handleClick}>Click Me!</button>;
};

function App() {
    return (
        <>
            <Button />
        </>
    );
}

export default App;

```

# Copy Event Listener
Another Example:

```javascript
const Copy = () => {
    const copyHandler = () => {
        alert("Stop copying 😢");
    };
    return (
        <>
            <p onCopy={copyHandler}>
                lorem ipsum...
            </p>
        </>
    );
};

function App() {
    return (
        <>
            <Copy />
        </>
    );
}

export default App;


```
# Hover Event Listener
Another example: 

```javascript
const Move = () => {
    const moveHandler = () => {
        console.log("You hovered over me!!");
        alert("Stop hovering 😢");
    };
    return (
        <>
            <p onMouseMove={moveHandler}>
                lorem ipsum...
            </p>
        </>
    );
};

function App() {
    return (
        <>
            <Move />
        </>
    );
}

export default App;

```
# State Management and Hooks
State in React is an object that holds data or information about the component. It can change over time, causing the component to re-render.

useState Hook
The useState() hook allows you to track state in a functional component.

Example:

```javascript

import { useState } from "react";

const Counter = () => {
    const [count, setCount] = useState(0);

    const increment = () => setCount(count + 1);
    const decrement = () => setCount(count - 1);

    return (
        <>
            <h1>{count}</h1>
            <button onClick={increment}>+</button>
            <button onClick={decrement}>-</button>
        </>
    );
};

function App() {
    return (
        <>
            <Counter />
        </>
    );
}

export default App;
```
# useEffect Hook
The useEffect() hook allows you to perform side effects in your components, such as fetching data or directly manipulating the DOM.

Example without useEffect:

```javascript
import { useState } from "react";

function App() {
    const [value, setValue] = useState(0);

    return (
        <>
            <h1>{value}</h1>
            <button onClick={() => setValue(value + 1)}>Click Me</button>
        </>
    );
}
export default App;
```
Example with useEffect:

```javascript
import { useEffect, useState } from "react";

function App() {
    const [value, setValue] = useState(0);

    useEffect(() => {
        console.log("hello");
        document.title = `Increment ${value}`;
    }, [value]);

    return (
        <>
            <h1>{value}</h1>
            <button onClick={() => setValue(value + 1)}>Click Me</button>
        </>
    );
}

export default App

```
# Prop Drilling
Prop drilling refers to passing props down multiple levels of components, often leading to complex and less maintainable code. It can be a challenge in large applications.

Example:

```javascipt
const ComponentC = ({ user }) => <div>User: {user}</div>;

const ComponentB = ({ user }) => <ComponentC user={user} />;

const ComponentA = ({ user }) => <ComponentB user={user} />;

function App() {
    const user = "Aditya";
    return (
        <>
            <ComponentA user={user} />
        </>
    );
}

export default App;
```

# useContext Hook
The useContext() hook provides a way to pass data through the component tree without having to pass props manually at every level.

Example:

```javascript
import React, { useContext } from "react";

const UserContext = React.createContext();

const ComponentC = () => {
    const user = useContext(UserContext);
    return <div>User: {user}</div>;
};

const ComponentB = () => <ComponentC />;

const ComponentA = () => <ComponentB />;

function App() {
    const user = "Aditya";
    return (
        <UserContext.Provider value={user}>
            <ComponentA />
        </UserContext.Provider>
    );
}

export default App;
```

# useRef Hook
The useRef() hook is useful for accessing and manipulating DOM elements directly. It can also be used to store mutable values that persist across renders without triggering a re-render.

Example:
```javascript
import React, { useRef } from "react";

const InputFocus = () => {
    const inputRef = useRef(null);

    const handleFocus = () => {
        inputRef.current.focus();
    };

    return (
        <>
            <input ref={inputRef} type="text" />
            <button onClick={handleFocus}>Focus Input</button>
        </>
    );
};

function App() {
    return (
        <>
            <InputFocus />
        </>
    );
}

export default App;
```
