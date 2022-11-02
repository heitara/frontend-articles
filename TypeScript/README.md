# TypeScript

**TypeScript It's JS superset which offers all of JavaScript’s features, and an additional layer on top of these: TypeScript’s type system. The main benefit of TypeScript is that It can highlight unexpected behavior in our code, lowering the chanse of bugs!**

- Assigning variables with particular types:
```js
let helloWorld: string = "Hellow World";
 //let helloWorld = "Hello World";
 
```
- We can use `any` so we can assign the variable with any value:
```js
let random: any = 23;
```
- Using an interface declaration. For example, to create an object with an inferred type which includes name: string and age: number, you can write:
```js
const user = {
  name: "Hayes",
  age: 16,
};
```
- `interface` declaration:
```js
interface User {
  name: string;
  age: number;
}

const user: User = { // We can shape out  new interface by using syntax like : TypeName after a variable declaration
  name: "Hayes",
  id: 0,
};
```
- Since JavaScript supports classes and object-oriented programming, so does TypeScript. You can use an interface declaration with classes:
```js
interface User {
  name: string;
  age: number;
}
 
class UserAccount {
  name: string;
  age: number;
 
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}
 
const user: User = new UserAccount("Murphy", 24);
```

# 

- Composing Types:
1. Unions -> With a union, you can declare that a type could be one of many types. For example, you can describe a boolean type as being either true or false:
```js
type MyBool = true | false;
```
**Unions provide a way to handle different types too. For example, you may have a function that takes an array or a string:**
```js
function getLength(obj: string | string[]) {
  return obj.length;
}
```
**Other things that we can do is to make a function return different values depending on whether it is passed a string or an array:**
```js
function strOrArr(obj: string | string[]) {
  if (typeof obj === "string") {
    return [obj]; // (parameter) obj: string   
  }
  return obj;
}
```
2. Generics -> Generics provide variables to types. A common example is an array. An array without generics could contain anything. An array with generics can describe the values that the array contains.
```js
type StringArray = Array<string>; // array that contains string values
type NumberArray = Array<number>; // array that contains number values
```
