# React Components

**Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.**

**Always start component names with capital letter, because React treats components starting with lowercase letters as DOM tags!**

- Functional Components:
   - The simplest way to define a component is to write a JavaScript function:
```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
> This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.

- Class Components:
  - The same example as the one above but with class component:
```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
# 

- Rendering a component
  - When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object. We call this object “props”.
```js
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="John" />; // It's going to render 'Hello, John'
```
- Composing Components
  - Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.
```js
//In this example we create App component that renders Welcome 3 times

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="John" />
      <Welcome name="Maya" />
      <Welcome name="Edgar" />
    </div>
  );
}
```
