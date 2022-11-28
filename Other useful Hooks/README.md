**Other useful hooks**

#

1. [`useRef`](https://www.youtube.com/watch?v=t2ypzz6gJm0)
```js
const renderCount = useRef(0)
```
- In this example (and every other), renderCount(just a name) is an object with only one property which is called `current`. The value of current is stored in the brackets after useRef.<br> The main resaon we are using useRef is because the `current` value is never going to cause our component to re-render. That's because is completely separated from the component render cycle.   
```ts
const App = () =>{
import React, { useEffect, useState, useRef } from "react";

function App() {
  const inputElement = useRef();

  const focusInput = () => {
    inputElement.current.focus();
  };

  return (
    <>
      <input type="text" ref={inputElement} />
      <button onClick={focusInput}>Focus Input</button>
    </>
  );
}
}
```
- Other example where with useRef we focus into our input element by clicking the button.

#

2. [`useMemo`](https://www.youtube.com/watch?v=THL1OPn72vo)

- It's used to optimize the computation cost of our React function components by memorizing values. React memo is used to wrap components to prevent re-rendering.<br>The useMemo Hook only runs when one of its dependencies update.
>If we have a function compute 1 + 1, it will return 2. But if it uses memoization, the next time we run 1’s through the function, it won’t add them up, it will just remember the answer is 2 without executing the adding function.<br><br>The dependencies act similar to arguments in a function. The dependency’s list are the elements useMemo watches: if there are no changes, the function result will stay the same. Otherwise, it will re-run the function. If they don’t change, it doesn’t matter if our entire component re-renders, the function won’t re-run but instead return the stored result.
```ts
function Welcome() {
  const [msg, setMsg] = useState("hello");
  const reverseMsg = useMemo(() => {
    return msg.split("").reverse().join("");
  },[msg]); //msg is dependency

  return (
    <div>
      <h1>{msg}</h1>
      <h1>{reverseMsg}</h1>
      <h1>{reverseMsg}</h1>
      <button onClick={() => setMsg("Hello")}>Change Msg</button>
    </div>
  );
}
```
- In the example above, we wrapped the function with useMemo() hook and it returns a memoized value or cached value, which is stored inside the reverseMsg variable. Now we can use reverseMsg in multiple places but the function will only run once and the next time it will return the value immediately from the cache.

#

3. [`useCallback`](https://www.youtube.com/watch?v=_AyFP5s69N4)

- When a component re-renders, every function inside of the component is recreated and therefore these functions’ references change between renders. `useCallback(callback, dependencies)` will return a memoized instance of the callback that only changes if one of the dependencies has changed. This means that instead of recreating the function object on every re-render, we can use the same function object between renders.

```ts
const memoized = useCallback(() => {
   // the callback function to be memoized
 },
  // dependencies array
[]);
```
> The useMemo and useCallback Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function.

- We need to pass two things to useCallback:
   - A function definition that you want to cache between re-renders.
   - A list of dependencies including every value within your component that’s used inside your function.

```ts
import { useCallback } from 'react';

function ProductPage({ productId, referrer, theme }) {
  const handleSubmit = useCallback((orderDetails) => {
    post('/product/' + productId + '/buy', {
      referrer,
      orderDetails,
    });
  }, [productId, referrer]);
  // ...
```
> On the initial render, the returned function you’ll get from useCallback will be the function you passed.
On the following renders, React will compare the dependencies with the dependencies you passed during the previous render. If none of the dependencies have changed, useCallback will return the same function as before. In other words, useCallback stores a function between re-renders until its dependencies change.


[`useContext`](https://www.youtube.com/watch?v=5LrDIWkK_Bc)

- React’s useContext hook makes it easy to pass data throughout your app without manually passing props down the tree.

```js
import ClassContextComponent from './classContextComponent';
import React from "react";
import {Display} from '../displayComponent'

// Here we create a Context
const NumberContext = React.createContext();
// It returns an object with 2 values:
// { Provider, Consumer }

// We can export useContext with destructuring 
export { CurrencyContext };


function App() {
  // Use the Provider to make a value available to all children and grandchildren
  return (
    <NumberContext.Provider value={42}>
      <div>
        <Display />
      </div>
    </NumberContext.Provider>
  );
}

// ----------------- ./DisplayComponent --------------------
// That's our Display component in separate file which takes tha value from our provider.

export default function Display() {
  // Then we use .Consumer to grab the value from context in our separate file
  return (
    <NumberContext.Consumer>
      {value => <div>The answer is {value}.</div>}
    </NumberContext.Consumer>
  );
}


// ----------------- ./DisplayComponent_PracticalWay --------------------
//We can also do it this way which is not including .Consumer but it's more practical:
export default function Display() { 
    const value = useContext(NumberContext);
  return (
      <div>
          <p>The answer is {value}.</p>
      </div>
  );
}
```

> All of the components and their childern wraped inside our context provider have access to this variable `value` and it's value. useContext can pass props essentially all the way down into any of the childern, without having to manually pass them. 

- Often, we’ll want the context to change over time. To update context, you need to combine it with state. Declare a state variable in the parent component, and pass the current state down as the context value to the provider:

```js
function MyPage() {
  const [theme, setTheme] = useState('dark');
  return (
    <ThemeContext.Provider value={theme}>
      <Form />
      <Button onClick={() => {
        setTheme('light');
      }}>
        Switch to light theme
      </Button>
    </ThemeContext.Provider>
  );
}
```












