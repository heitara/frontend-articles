# [JSX](https://www.youtube.com/watch?v=9GtB5G2xGTY)

**It's a syntax extension to JavaScript which produces React "elements". Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both.**

- Embedding expressions in JSX:
```js
const name = 'John D.';
const element = <h1>Hello, {name}</h1>;
// In this example we declare a variable called name and then use it inside JSX by wrapping it in curly braces
```
#

- JSX represents objects trough Babel(which is JS compiler):
```js
const element = <h1 class=greet''> Hello stranger! </h1>

//Then Bable compiles JSX:

const element = {
  type: 'h1',
  props: { 
    className: 'greet',
    children: 'Hello stranger!'
  }
};
```
**These objects are called “React elements”. You can think of them as descriptions of what you want to see on the screen. React reads these objects and uses them to construct the DOM and keep it up to date.**

#

- JSX is an expression too. This means that we can use JSX inside of if statements and for loops, assign it to variables, accept it as argument, and return it from function:
```js
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```
**Since JSX is closer to JavaScript than to HTML, React DOM uses camelCase property naming convention instead of HTML attribute names. For example, class becomes className in JSX, and tabindex becomes tabIndex.**
