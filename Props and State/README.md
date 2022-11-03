# [Props and State](https://www.youtube.com/watch?v=IYvD9oBCuJI)

> props (short for “properties”) and state are both plain JavaScript objects. While both hold information that influences the output of render, they are different in one important way: `props get passed to the component (similar to function parameters)` whereas `state is managed within the component (similar to variables declared within a function)`.

#

- Props

> Useful for when we want to display some information inside of a component without hardcoding it, essentially it's a variable to a function.

```js
// We are passing props as parameter for the function component and then using it to take the defined value of name.

function Welcome(props) {
  return <h1>Hello {props.name}</h1>;
}

function App(){
return <Welcome name="Edgar" />;
}
```

- State:

> State is there for when we need to actually re-render and update our application based on something that the user has done.


#

- Example:

**Let's say we have a component with a title and subtitle. We want to change the title according to what the user entered. In this example, we only need props because we are displaying text, and not storing any data that should be updated on every render.**

**Let's say we have a counter. Then props is used to give the starting number, and after that, the counter needs to be updated (the new value that we are going to add another number). So we use State to store the value and change it.**
