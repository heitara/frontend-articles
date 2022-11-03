# [Conditional Rendering](https://www.youtube.com/watch?v=4oCVDkb_EIs)

**Conditional rendering in React works the same way conditions work in JavaScript. Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.**

#

- Inline If with logical `&&` Operator:
```js
function App(props){
  const msg = props.msg;
  
  return(
    <div>
     {msg.length > 0 && 
       <p>New message: {msg} </p>
     }
    </div>
 );
}
```
**It works because in JavaScript, true && expression always evaluates to expression, and false && expression always evaluates to false.<br>Therefore, if the condition is true, the element right after && will appear in the output. If it is false, React will ignore and skip it.**

#

- Inline If-Else with Conditional Operator
   - Another method for conditionally rendering elements inline is to use the JavaScript conditional operator condition ? true : false.
```js
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
    </div>
  );
}
```

**In the example above we use `?` for if it's true and `:` for else(if it's not). So the end result is if isLoggedIn is ture we pass 'currently', else we pass 'not' . **
