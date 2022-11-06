# Hooks

**Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes**

1. State Hook(returns stateful value and a function to update it)
- We call it inside a function component to add some local state to it. React will preserve this state between re-renders. useState returns a pair: the current state value and a function that lets you update it. The only argument to the useState() Hook is the initial state. Unlike with classes, the state doesn’t have to be an object. We can keep a number or a string if that’s all we need.
```js
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
``` 
> The array destructuring syntax lets us give different names to the state variables we declared by calling useState. These names aren’t a part of the useState API. Instead, React assumes that if you call useState many times, you do it in the same order during every render. 

- Using Multiple State Variables
   - Declaring state variables as a pair of [something, setSomething] is also handy because it lets us give different names to different state variables if we want to use more than one:
```js
  function ExampleWithManyStates() {
     const [age, setAge] = useState(37);
     const [fruit, setFruit] = useState('apple');
     const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  }
  
  // we can update them individually:
  function handleOrangeClick() {
    setFruit('banana');
  }
```
#

2. Effect Hook

**The Effect Hook lets you perform side effects in function components**

> Data fetching, setting up a subscription, and manually changing the DOM in React components are all examples of side effects.<br>There are two common kinds of side effects in React components: those that don’t require cleanup, and those that do.
- Effects Without Cleanup:
  - Let's say we want to run some additional code after React has updated the DOM. Network requests, manual DOM mutations, and logging are common examples of effects that don’t require a cleanup. We say that because we can run them and immediately forget about them.
  - `What does useEffect do?`<br>By using this Hook, you tell React that your component needs to do something after render. React will remember the function you passed (we’ll refer to it as our “effect”), and call it later after performing the DOM updates.
  - `Why is useEffect called inside a component?`<br>Placing useEffect inside the component lets us access the count state variable (or any props) right from the effect. We don’t need a special API to read it — it’s already in the function scope.
  - `Does useEffect run after every render?` - Yes! By default, it runs both after the first render and after every update.

```js
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

- Effects with Cleanup
  - Let's say we might want to set up a subscription to some external data source. In that case, it is important to clean up so that we don’t introduce a memory leak!
  - You might be thinking that we’d need a separate effect to perform the cleanup. But code for adding and removing a subscription is so tightly related that useEffect is designed to keep it together. If your effect returns a function, React will run it when it is time to clean up:

```js
import React, { useState, useEffect } from 'react';

function FriendStatus(props) {
  const [isOnline, setIsOnline] = useState(null);

  useEffect(() => {
    function handleStatusChange(status) {
      setIsOnline(status.isOnline);
    }
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
    // We don’t have to return a named function from the effect. It's called cleanup here to clarify its purpose.
    return function cleanup() {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });

  if (isOnline === null) {
    return 'Loading...';
  }
  return isOnline ? 'Online' : 'Offline';
}
```
> The cleanup function is after a return so it's ran first and because of that it can "clean" whatever we did last time before the side effect!
- `Why did we return a function from our effect?`<br>This is the optional cleanup mechanism for effects. Every effect may return a function that cleans up after it. This lets us keep the logic for adding and removing subscriptions close to each other. They’re part of the same effect!
- `When exactly does React clean up an effect?`<br>React performs the cleanup when the component unmounts. However, as we learned earlier, effects run for every render and not just once. This is why React also cleans up effects from the previous render before running the effects next time.

- Sometimes we don't want to use Effect after every render. That's where dependencies come. They are waiting for a specific thing to happened/change and then the useEffect is fired:

```js
  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }[count]);
```
> In the example above, only when the value of count is changed, useEffect will fire. If we dont pass any value in the dependencies, it's going to me only on mount!

