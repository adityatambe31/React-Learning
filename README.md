# 📘 ReactJS Interview Preparation Notes

This document is a comprehensive guide to essential ReactJS concepts, complete with examples, to help you ace your interviews. It covers the basics and beyond, including components, JSX, state management, hooks, and more. These notes are derived from a YouTube tutorial and include crucial interview topics.

## 📑 Table of Contents

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
- [Custom Hooks](#custom-hooks)
- [useMemo Hook](#usememo-hook)
- [useRef Hook](#useref-hook)
- [Component Life Cycle](#component-life-cycle)

### 📜 Components

React components are the building blocks of a React application. They can be functional or class-based, each serving different purposes. Functional components are typically used for UI rendering and stateless operations, while class-based components are used for managing state and lifecycle methods.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

```
# 🔤 JSX
JSX stands for JavaScript XML. It allows us to write HTML inside JavaScript, which makes the code easy to understand and debug.

Example: ```jsx const element = <h1>Hello, world!</h1>;```

# 🌐 Fragments
Fragments allow you to group multiple elements without adding extra nodes to the DOM.

```jsx return (
  <>
    <h1>Title</h1>
    <p>Description</p>
  </>
);
```

# 🧮 Expressions in JSX
You can embed any JavaScript expression in JSX by wrapping it in curly braces.
Example: 
```jsx
const name = 'John Doe';
const element = <h1>Hello, {name}</h1>;
```

# 📋 Lists
Rendering lists in React is typically done using the .map() function, which returns an array of JSX elements.

```jsx
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```
# 🔄 Props
Props (short for "properties") are used to pass data from parent to child components.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

```

# ❓ Conditional Rendering
You can conditionally render elements in React using JavaScript operators like if, &&, or the ternary operator ? :.

```jsx
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  }
  return <h1>Please sign up.</h1>;
}

```

# 🔁 Logical and Ternary Operators
Use logical && or ternary operators ? : for inline conditional rendering.

``` jsx
const isLoggedIn = true;
return (
  <div>
    {isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please sign up.</h1>}
  </div>
);

```

# 🎨 Styling in React
Styling can be done using inline styles, CSS stylesheets, or CSS-in-JS libraries.

```jsx

const divStyle = {
  color: 'blue',
  backgroundColor: 'lightblue',
};
return <div style={divStyle}>Styled Component</div>;
```
# 🎛️ Event Handling
Event handling in React is very similar to handling events in DOM elements, but with some syntactical differences.

```jsx
function handleClick() {
  alert('Button clicked!');
}
return <button onClick={handleClick}>Click Me</button>;

```
# 🛠️ State Management and Hooks
React's state is used to manage data that changes over time. Hooks like useState allow you to add state to functional components.

```jsx
const [count, setCount] = useState(0);
return (
  <div>
    <p>You clicked {count} times</p>
    <button onClick={() => setCount(count + 1)}>Click me</button>
  </div>
);

```

# 🔄 useEffect Hook
The useEffect Hook lets you perform side effects in functional components, such as fetching data or directly manipulating the DOM.

```jsx
useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]);
```

# 🔧 Custom Hooks
Custom Hooks allow you to reuse stateful logic across components.

```jsx
function useCustomHook() {
  const [data, setData] = useState(null);
  // logic to fetch data
  return data;
}
```

# 💡 useMemo Hook
useMemo is used to memoize expensive calculations and avoid recalculating unless dependencies change.

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

# 📍 useRef Hook
useRef is used to reference a DOM element directly, bypassing React's state mechanism.

```jsx
const inputRef = useRef(null);
function handleFocus() {
  inputRef.current.focus();
}
return <input ref={inputRef} />;
```

# 🌀 Component Life Cycle
Understanding the React component lifecycle is crucial for managing side effects, state, and component updates.

```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    // Code to run after component mounts
  }
  
  componentWillUnmount() {
    // Code to run before component unmounts
  }
  
  render() {
    return <div>Lifecycle Methods</div>;
  }
}
```

# 📚 Additional Resources



