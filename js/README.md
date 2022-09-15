# JS:
 
1. Object.* [hint](https://github.com/LeCoupa/awesome-cheatsheets/blob/master/languages/javascript.js)
 >The object type repsresents one of JS data types. It's used to store various keyed collections (key-value pairs - properties), methods and more complex entities.
- [Object detailed explanation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
 
```js
const person = {
    name: 'John',
    age: 33
}

console.log(person.name)
```
> In this example we created an object with two properties. They are both key-value pairs, name(or age) beign the key and 'John'(or 33) the value. We need to put comma(,) after each key-value pair, method etc. 
 To get the value of the name(property) we need to call `person.name`.

- **Object methods** -> When the value is function, the property becomes a method. Typically, we use methods to describe the object behaviors:

```js
const person = {
    firstName: 'Gorge',
    lastName: 'Johnson',
    fullName: function(){
        return `${firstName} ${lastName}`;
    }
};
```
> In this example we create a method called `fullName` that combine first and last name.


- **Object constructor** -> The obj. constructor turns the input into an object but it's behavior depends on the input's type:
   - `null` or `undefined` -> It's going to create and return empty string.
   - normal input -> It's going to return an obj. of a type that coresponds to the given value.
   - obj. -> If the value is object already, it will return the value.
   - [Object constructor hint](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/Object)

```js
function person(name, age, heigh){
    this.fullName = name;
    this.age = age;
    this.heigh = heigh;
}

const myFather = new person('David', 45, 182);
```
- **The keyword `this`** -> This keyword refers to an object but it depends on how `this` is been used:
   - Alone, `this` refers to the global object(window).
   - In a function, refers to the global object.
   - In a function, in strict mode, `this` is undefined.
   - In events, refers to the element that recived the event.
   - [Keyword `this` hint](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
   
- **prototype** -> That's the mechanism by which JS object inherit features from one another. The property of an object that points to it's proto. is not called prototype, all browsers use `__proto__`. The standart way to accsess an object's proto. is the `Object.getPrototypeOf()` method
   - Prototype chain - Every object in JS has a built-in property, which it's called `prototype`. The proto. is itself an object, so the proto. will have it's own proto., making what's called a protoype chain.
   - [Prototype hint](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)

#
2. Inheritance (class, ES6)
- **What is a class** -> Classes are a template/'special function' for creating objects. The class syntax has two components - class expressions and class declarations:
   - Class declarations -> To declare a class, we use the `class` keyword with the name of the class:
```js
     class User {
     constructor(email, password){
         this.email = email;
         this.password = password;
     }
 }
```
  - Class expression -> That's another way to define a class. They can be named or unamed and the name given to a class expression is local to the class's body but it can be accessed with the `name` property:
   ```js
   let User = class {
    constructor(email, password){
        this.email = email;
        this.password = password;
    }
};

console.log(User.name);
   ```
   
- `extends` or inheritance -> This keyword is used in class declarations or class expressions to create a class as child of another class. 

   - `Constructor` -> The constructor is a special method for creating and initilizing an object with a class. There can only be one method with the name 'constructor' in a class.
   
   - `super` keyword -> This keyword is used to call the constructor of the super class.
> If there is constructor present in the subclass, it needs to first call `super` before using `this`.
   
   ```js
   class Animal {
    constructor(name) {
      this.name = name;
    }
  
    noise() {
      console.log(`${this.name} makes a noise.`);
    }
  }
  
  class Dog extends Animal {
    constructor(name) {
      super(name); 
    }
  
    speak() {
      console.log(`${this.name} barks.`);
    }
  }
  ```
- [Classes and Inheritance explained!](https://www.youtube.com/watch?v=RBLIm5LMrmc)
 
#
3. await/async
- `async` function -> That's a function declared with the async keyword and the await keyword is premitted within it. Both of those keywords combined enable asynchronous, promise-based behavior to be written, avoiding promise chains.
   > If the function return a value, the promise will be resolved with that value, but if the function throws an exeption, the promise will be rejected.
   ```js
      async function Greeting(){
        return 'Hello'
      }// Promise resolved. Outcome -> 'Hello'
   ```
   - async function expression -> It's like normal async func. but saved in a variable:
   ```js
         const greeting = async () =>{
           return 'Hello'
         }// Promise resolved. Outcome -> 'Hello'
   ```
   
- `await` -> The await operator is used to wait for a `Promise` and it can be used only inside an `async function`. 
   - Code after each await expression can be thought of as existing in a `.then` callback
 > If a promise is passed to an await expression, it waits for the promise to be fulfilled and returns the fulfilled value.
 If the value is not a promise, it converts the value to a resloved promise and waits for it.
```js
    async function fakeRequest(){
      let data = await fakeRequest('/page1')
      return data;
    }
```

#
4. Promises - how to create a promise, how to separete errors.
- What is a `Promise` -> That's an object which represents the eventual completion or failure of an asynchronous operation and it's resulting value. A promise can have one of these states:
   - Pending -> Initial state, neither fulfilled nor rejected.
   - Fulfilled -> It means that the operation was completed successfully.
   - Rejected -> It means that the operation failed.
> A promise is said to be settled if it's either fulfilled or rejected, but not pending. To create one we simply need to write `new Promise` .

```js
   let myPromise = new Promise(function(resolve, reject) {
       resolve(); // when successful
       reject();  // when error
     });

     myPromise
     .then(
       function (res){
         //code that will run if it's successful
       }
     )
     .catch(
       function(err){
         //code if there is error
       }
     );
```
 

- `try` and `catch` -> When using async function, the easiest way to deal with errors is with try and catch blocks around the asynchronous code.
```js
   async function doubleRequest(){
   try{
     let data1 = await fakeRequest('/page1');
     let data2 = await fakeRequest('/page2');
     return data1 && data2;;
   }catch(error){
     return error;
   }
 }
```

- `.then()` -> This method retunrs a promise. It takes up to two arguments: callback function for the success and failuer of the promise.
```js
    const request = fakeRequest('google.com/coffee');
    request.then(() =>{
      //if it works .....
    }).catch(() =>{
      //if we get error .....
    })
```

- `resolve` and `reject` -> These are callback which hold value that is used in cetain situation - when the promise is resolved or rejected.
 ```js
     let promise = new Promise(function(resolve, reject) {
       resolve('Success!');

       reject(new Error('There is error!!'));
     });
 ```
 
- How to handle Promise -> The handler methods: `.then()` & `.catch()`:
 ```js
      let promise = new Promise(function(resolve, reject) {
        resolve('Success!');

        reject(new Error('There is error!!')); // ignored
      });

      promise.then(() =>{
        return resolve;
      }).catch(() =>{
        return reject;
      });
 ```

#
5. bind(), call(), apply() [hint](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)
- `bind()` -> That's a method which creates new function that, when called, has it's `this` keyword set to the provided value, with a given sequence of arguments. 

> The bind() function creates a new bound function. Calling the bound function generally results in the execution of its wrapped function. The bound function will store the parameters passed — which include the value of this and the first few arguments.
```js
   this.x = 5;   
   const number = {
     num: 33,
     getNum() { return this.num; }
   };

   module.getNum(); //  returns 33


   const findNum = number.getNum;
   findNum(); //  returns 5 because the function gets invoked at the global scope


   const boundGetNum = findNum.bind(number);
   boundGetNum(); //  returns 33
```
- `call()` -> The call() method calls the function with a given this value and arguments provided individually. 
 
 ```js
     function rollerCoaster(name, height) {
     this.name = name;
     this.height = height;
   }

   function requirements(name, height) {
     rollerCoaster.call(this, name, height);
     this.category = 'adrenaline boost';
   } 

   console.log(new requirements('Joe', 145).name); //output: 'Joe'
 ```
> The call() allows for a function or method belonging to one object to be assigned and called for a different object. Also we can write a method once and then inherit it in another object, without having to rewrite the method for the new object.
 
- `apply()` -> The apply() method calls the specified function with a given `this` value, and arguments provided as an array. It's almost identical to call(), except that call() accepts an argument list, while apply() accepts a single array of arguments:
   - with call -> function.call(this, 'name', 'height')
   - with apply -> function.apply(this, [name, height])
```js
       const person = {
         info: function (city, country) {
            return `${this.firstName} ${this.lastName} lives in ${city}, ${country}`;
         },
       };

   const person1 = {
     firstName: "Joe",
     lastName: "Barling",
   };

   person.info.apply(person1, ['London', 'United Kingdom']);
```

#
6. DOM - basics, events, window, document
- DOM (or Document Object Model) -> The DOM connects web pages to scripts or programming languages by reprsenting the structure of a document (it contains representation of all the content on the page). Usually it refers to JS, even though modeling HTML and other documents as objects are not part of the core JS language.
   - HTML DOM -> A document containing HTML is described using the `document interface`, which is extended by the HTML specification to include various HTML-specific features.
   
- `The document object` -> Represents the web page and it's used to access elements in the HTML file. 
 
- DOM elements -> How to find an element:
   - `document.getElementById('root')` -> by using the element id.
   - `document.getElementsByTagName('p');` -> by using the element tag name.
   - `document.getElementByClassName('class_name')` -> by using the element class name.
   - `document.querySelector('p')` -> by using querySelector, it's going to take the first match (first paragraph). If we want id('#id') or class('.class_name').
- Other useful commands:
   - `.innerText` -> It changes the text of the element.
   - `.getAttribute('class')` -> It gives the name of the class of the variable we are using it on.
   - `.style` -> It changes the style but inline - `.style.color = 'red'`.
   - `.ClassList` -> It gives the class of the element.
      - `.ClassList.add(class_name)` -> we can add classes without removing the others (like setAttribute does).
      - `ClassList.remove('class_name')` -> removes a class.
      - `ClassList.toggle('class_name')` -> we can toggle a specific class to acitve.
   - `.parentElement` -> it gives the parent element of the element.
   - `.children` -> It gives HTML collection of the children.
   - `.removeChild(child)` -> It's going to remove a child of an element.
   - `document.createElement('img')` -> It creates and `empty` element.
   - `.append` -> we can append text or element.
   - `.appendChild` -> This method allows us to add a node to the end of the list of child nodes of a specified parent element.
   - `Element.insertAdjecentElement('position', element)` -> It's going to  insert an element to a specifiv position:
      - 'beforebegin' -> before the target element.
      - 'afterend' -> after the target element.
      - 'afterbegin' -> inside the target element, before it's first child.
      - 'beforeend' -> inside the target element, after it's last child.
- DOM events -> 
  - `.addEventListener('onclick', function....);` -> we can add what event we are listening for (onclick) and a function that we want to accure after is clicked.
 ```js
    const btn = element.querySelector('.btn');
    const random = () =>{
      alert('click accured');
    }
    btn.addEventListener('onlclick', random);
 ```
- We can add objects after the function to specify different things:
```js
    const btn = element.querySelector('.btn');
    const random = () =>{
      alert('click accured');
    }
    btn.addEventListener('onlclick', random, {once: true});
    //we add an obejct value that allows the function to run once.
```

- `The window object` -> It represents the browser's window and it's supported by all browsers. **All global JS objects, functions and veriables automatically become members of the window object. Global veriables are properties of the window object and global functions are methods of the window object.**

---