# frontend-articles
A repository that contains resources and useful articles for frontend developers

> The materials here are heavily inspired from `https://roadmap.sh/frontend`.

## Repository structure

[HTTP Protocol](./articles/http/README.md)


## Topics:
1. [Markdown](#markdown)
1. [Git (Github)](#user-content-git--github)
1. [Terminal](#terminal)
1. [JS](#js)
1. [NPM (NodeJS)](user-content-npm--nodejs)


## Markdown

**Markdown is a `lightweight markup language` that you can use to add formatting elements to plaintext text documents.**

**How does Markup work?**

> When you write in Markdown, the text is stored in a plaintext file that has an .md or .markdown extension. Markdown applications use something called a Markdown processor (also commonly referred to as a “parser” or an “implementation”) to take the Markdown-formatted text and output it to HTML format. At that point the document can be viewed in a web browser or combined with a style sheet and printed.

![Markdown visual representation](https://mdg.imgix.net/assets/images/markdown-flowchart.png?auto=format&fit=clip&q=40&w=1080)

[**Markdown cheat sheet**](https://www.markdownguide.org/cheat-sheet/)

---
## Git(Github)

**What's git?**

> Git is Version Control System(VCS) for traking changes in computer files. With git many people can work on the same project without having to be on the same network. 
> Usualy when we use it there is local repository that we make changes on and then we push it to a remote repository.

**Concept of Git**

- Keeps track of code history.
- Takes 'snapshots' of our files.
- We can take a 'snapshot' by making a 'commit'.
- We can visit our snapshots at any time.
#
**Imortant commands:**

1. ##### `git rebase <nameOfBranch>`
![Git rebase example](https://wac-cdn.atlassian.com/dam/jcr:4e576671-1b7f-43db-afb5-cf8db8df8e4a/01%20What%20is%20git%20rebase.svg?cdnVersion=486)
> Rebasing is the process of moving or combining a sequence of commits to a new base commit (basically rewriting history). It's useful alternative to merging because it gives a cleaner repo history which can help us troubleshoot bugs faster.
- **Don't rebase in public branches! The rebase would replace the old commits with new ones and it would look like that part of your project history abruptly vanished.**
- `git log -3` //to see most recent commits (to be exact, last 3 on this example).
- [Git Rebase clean explanation!](https://www.youtube.com/watch?v=_UZEXUrj-Ds)

#
2. ##### `git merge <nameOfBranch>`
> In the most frequent use cases, git merge is used to combine two branches. When creating a merge commit Git will attempt to auto magically merge the separate histories for us. If Git encounters a piece of data that is changed in both histories it will be unable to automatically combine them. That's why we should be prepared for merge:
- Confirm the receiving branch -> Execute git status to ensure that HEAD is pointing to the correct merge-receiving branch. If needed, execute git checkout to switch to the receiving branch. 
- Fetch latest remote commits -> Make sure the receiving branch and the merging branch are up-to-date with the latest remote changes. Execute git fetch to pull the latest remote commits. Once the fetch is completed ensure the main branch has the latest updates by executing git pull.
- Execute `git merge <.>` where <.> is the name of the branch that will be merged into the receiving branch.
![Git merge example](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=486)

[Git merge vs git rebase](https://www.youtube.com/watch?v=dO9BtPDIHJ8)

#
3. ##### `git pull`
> Git pull is used to fetch and download content from a remote repo and immediately update the local repo to match that content. The biggest risk that can occur when running git pull is getting changes in a remote file that we have been working in which may cause conflics to arise in certain cases.
- `git pull <remote>` //fetch the specified remote’s copy of the current branch and immediately merge it into the local copy -> it's equal to: git fetch <remote> + git merge <current branch>
 
[Git fetch and git pull](https://www.youtube.com/watch?v=QRydepk8TB0)
 
#
**Other useful commands:**
 
- `git init` //initialize local git repository.
- `git add <file>` //add file(s) in the staging area.
- `git status` // shows what we have in the staging area and also what's ready for commit.
- `git commit`  //commit changes -> it's going to take everything that's in the staging area and put it in our local repository.
  - `git commit -m 'Changed index.html'` //it's going to commit a file with message.
- `git clone` //it's going to copy a remote repository into our current folder.
- `git rm --cached <file>` //it's going to remove a file.
- `git branch <name>` //create a branch
  - `git checkout <name>` // to switch to other branch.
- `git fetch <remote>` //fetch all of the branches from the repository -> downloads commits, files, and refs from a remote repository into our local repo (making sure that updates have occured) 
  
  
  
---
## Terminal 
  1. **Basic commands:**
   
  - `mkdir` [OPTION]... DIRECTORY... -> The command stands for "Make directory" and allows users to create directories. We can create more than one directory at a time.
    - `mkdir test` // It's going to create a folder with the name test.
    
- `cd` -> Changes directories!
    - `cd Movie` //It's going to change to Movie folder.
    - `cd ..` //Change to previous directory(parent directory).
    - `cd .` //Change to current directory.
    - `cd ~` //Change to the HOME direcory of the user that's currently logged in.
    - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
    
- `echo` [option] [string] -> The command is going to display string or variable provided by the user.
    - `echo -e` //Enables interpretation of escape charecters like: \a, \b, \c etc.
    - `echo -n` //It's going to display the content with line numbers.
   
- `cat` [option] [directory] -> The command can:
   - Display content of a file(s) -> `cat test_file.txt` or for multiple files `cat test_file1.txt test_file2.txt`
   - Redirect contents -> `cat file1.txt > file2.txt`
   - Append content from one file to another -> `cat file1.txt >> file2.txt`
   - Append text -> `cat >> file.txt`
   - Create new file -> `cat > new_file.txt`
   - [How to use `cat`](https://www.youtube.com/watch?v=nK4028I3N5U&list=LL&index=3&t=452s)
   
- `ls` [option] [directory] -> The command is used to view the content of a directory. If we want to see the content of other directories, type ls and then the directory’s path.
   - `ls -R` -> It's going to list all the files in the sub-directories.
   - `ls -a` -> It's going to show the hidden files
   - `ls -al` -> It's going to list the files and directories with detailed information like: permissions, size, owner, etc.
   - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
 
- `grep` or Global Regular Expression Print -> The command it's going to search through a file or files for a regular expression(regex) and then print out the lines where that regex was found.
   - `grep 'orage' grocery_list.txt` //It's going to search for orange in the .txt file -> oranges-yes, Orange Juice-no
   - `grep -i 'orange' grocery_list.txt` // -i it's going to ignore upper or lower-cased latters -> oranges-yes, Orange Juice-yes
   - `grep -w 'orange'.... ` // It's going to return only the lines where our regex is a single word -> oranges-no, orange juice-yes
   - `grep -c .... ` // -c It's going to return how many times our regex was found (stands for count)
  
#
2. **vim**
 
- Create:
> To use and create vim file (in VScode) we need: Vim extension and [enabled key-repeating](https://github.com/VSCodeVim/Vim).

##### Edit file:
- Switching modes:
   - `i` for insert mode.
   - `esc` for command mode.

- Navigation in command mode:
  - `k` for going up.
  - `j` for goimg down.
  - `h` for going left.
  - `l` for going right.
 
- Editing in a line:
  - `Shift + i` -> Switch to insert mode and move to the start of the line.
  - `a` -> Switch to insert mode and move to the right.
  - `Shift + a` -> Switch to insert mode and move to the end of the line.
  - `i` -> Switch to insert mode and move to the left.
 
- Making changes while in command mode:
  - `x` -> Delete the character that we are currently on.
  - `r` -> Replace the character that we are currently on.
 
#
3. **ssh**

> SSH (or Secure Shell) is network protocol that allows one computer to secuerly connect to another computer by encrypting data. It's commonly implemented using the clinet-server model:
- One computer is called SSH Clinet and another machine acts as SSH Sever.
- Then SSH can be set-up by using a pair of keys:
   - Public key that is stored on the SSH Server and a private key that is stored on the SSH Clinet.
- Then the SSH Client will make contact with the SSH Server and provide the ID of the key pair to prove it's identity.
- The SSH servers creates a challenge that is encrypted by the public key and sent to the SSH Client.
- At last the SSH Client decrypts the callenge with the private key and sends back the original form to the SSH Server.
- Once the nagotiation is complete, the connection is established.

 
---
## JS:
 
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
> In this example we created an object with one property. That's a key-value pair, name beign the key and 'John' the value. We need to put comma(,) after each key-value pair, method etc. 
 To get the value of the name(property) we need to call `person.name`.

- **Object methods** -> When the value is function, the property becomes a mathod. Typically, we use methods to describe the object behaviors:

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
   - normal input -> It's going to return an obj. of a type that coresponds to the given value
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
   '''js
         const greeting = async () =>{
           return 'Hello'
         }// Promise resolved. Outcome -> 'Hello'
   '''
   
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
- What is a `Promise` -> That's an object which represents the eventual completion or failur of an asynchronous operation and it's resulting value. A promise can have one of these states:
   - Pending -> Initial state, neither fulfilled nor rejected.
   - Fulfilled -> It means that the operation was completed successfully.
   - Rejected -> It means that the operation failed.
> A promise is said to be settled if it's either fulfilled or rejected, but not pending.
 
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
         fullName: function (city, country) {
            return `${this.firstName} ${this.lastName} lives in ${city}, ${country}`;
         },
       };

   const person1 = {
     firstName: "Joe",
     lastName: "Barling",
   };

   person.fullName.apply(person1, ['London', 'United Kingdom']);
```

#
6. DOM - basics, events, window, document
- DOM (or Document Object Model) -> The DOM connects web pages to scripts or programming languages by reprsenting the structure of a document (it contains representation of all the content on the page). Usually it refers to JS, even though modeling HTML and other documents as objects are not part of the core JS language.
   - HTML DOM -> A document containing HTML is described using the `document interface`, which is extended by the HTML specification to include various HTML-specific features.
   
- DOM elements -> How to find an element:
   - `document.getElementById('root')` -> by using the element id.
   - `document.getElementsByTagName('p');` -> by using the element tag name.
   - `document.getElementByClassName('class_name')` -> by using the element class name.
   - `document.querySelector('p')` -> by using querySelector, it's going to take the first match (first paragraph). If we want id('#id') or class('.class_name').

---
## NPM & NodeJS
  1. how to setup project
  1. how to add scripts
---


  
