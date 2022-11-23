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






