

## React Hooks 🎣

Think of React Hooks as special tools 🛠️ that help React function properly without writing a lot of extra code. Before, we needed "classes" to do certain things in React, but now, with hooks, it’s much easier!

## 🪝 What are Hooks?

<li>Hooks are like superpowers 💥 that you can add to your functions in React to make them more useful.</li>

<li>They "hook" into React features like state (a place to store values) and lifecycle methods (what happens when things change).
</li>

## State 🗂️

Imagine you have a box 📦 where you can store things (like a toy or a snack). This is like state in React, where we store values that can change over time.

### 🪣 What is State?
<li>State is like a memory box 🧠 where you can put values that might change, like a name, a number, or a button color.</li>

<li>State keeps track of these values and updates the screen whenever something changes!</li>

### 🧸 How to Use State in React?

<li>
  First, we tell React that we need some state using a special tool called useState.
</li>
<li>
  Then, we can update 🖊️ the state whenever we need to, and React will automatically change the display for us.
</li>
<br/>

```jsx
import React, { useState } from 'react';

function SimpleCounter() {
  // 🎲 We have a number (count) and a function to change it (setCount)
  const [count, setCount] = useState(0); 

  return (
    <div>
      <p>🚀 Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>➕ Increase</button>
    </div>
  );
}

```
### In the above example:
<li> count is like a number we store in our memory 🧠.</li>
<li>setCount is how we change the number whenever we press the button.</li>


## useEffect 🔄

Imagine you want to do something every time the room changes—like whenever someone enters, you switch the light on 💡. That's what useEffect does for you!

### 🔔 What is useEffect?

useEffect is like a reaction 😲 to any change. It lets you do something when:
<li>The page first loads.</li>
<li>A value in your app changes.</li>
<li>Something stops or gets removed.</li>


### 🔄 How to Use useEffect?

<li>useEffect runs automatically when things change (like state or props).</li>
<li>You can decide when it should run by adding some conditions.</li>

```jsx
import React, { useState, useEffect } from 'react';

function TimeDisplay() {
  const [time, setTime] = useState(new Date().toLocaleTimeString());

  // ⏰ This runs every time the page is rendered (component mounts).
  useEffect(() => {
    const timer = setInterval(() => {
      setTime(new Date().toLocaleTimeString());
    }, 1000);

    // 🚪 Cleanup: This stops the timer when the component is removed.
    return () => clearInterval(timer);
  }, []);

  return (
    <div>
      <p>⏳ Time: {time}</p>
    </div>
  );
}

```
<li>useEffect in the example keeps the time updated ⏱️ by running every second.</li>
<li>The cleanup 🧹 stops the timer when it's no longer needed.</li>

### Custom Hooks 🛠️

<li>Imagine you have a favorite tool 🔧 that you use over and over in your projects. Instead of making the tool from scratch every time, you make a custom hook to save time!</li>

### 🧑‍🍳 What is a Custom Hook?

<li>A Custom Hook is like a recipe 🍲 that holds some logic (like handling state or effects)     that you can reuse across different components.</li>

### 🛠️ How to Make a Custom Hook?

<li>It's just a function that uses other hooks like useState or useEffect.
  The function name   should start with use, like useCustomThing.</li>

```jsx
import { useState, useEffect } from 'react';

// 👨‍🍳 A custom hook to get the current date & time!
function useCurrentTime() {
  const [time, setTime] = useState(new Date().toLocaleTimeString());

  useEffect(() => {
    const timer = setInterval(() => {
      setTime(new Date().toLocaleTimeString());
    }, 1000);

    return () => clearInterval(timer);
  }, []);

  return time;
}

function TimeDisplay() {
  const time = useCurrentTime(); // 👨‍💻 Using the custom hook!

  return <p>🕒 The current time is {time}</p>;
}

```

In this example, useCurrentTime is a custom hook that does all the time updating magic ✨. Now, we can use it in any component to get the current time!

## Using Hooks in Simple and Complex Projects 🔍

<li>Simple Project: Imagine you have a project that just displays the number of times someone clicks a button (like a counter). Here, we just use state and maybe useEffect to track the clicks. 🖱️</li>

<li>Complex Project: In bigger apps (like a social media app), you can use hooks to manage user data, API calls, and animations. You may have multiple hooks working together: custom hooks for fetching data, useEffect for side effects, and state to manage everything.</li>

## Final Thoughts 🧠

<li>Hooks are like magic tools 🪄 to help you do powerful things in React.</li>
<li>State keeps track of changes, and useEffect helps React know when to run extra code.</li>
<li>Custom hooks let you reuse code, making your life much easier.</li>

### Remember, React hooks are just like making a cool toy 🧸—you just need to understand how to build and use the pieces! 🎉
