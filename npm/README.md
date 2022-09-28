# NPM and NodeJS
 1. What is NPM( or Node Package Manager) -> npm is the world's lagerst Software Library and also a sofware Package Manager and Installer. It's the main package manager for node.js .
- [About packages](https://docs.npmjs.com/about-packages-and-modules) -> A package is a file or directory that is described by a `package.json` file and that package must contain a package.json file in order to be published to the npm registry. 
    - These packages can be scoped or unscoped -> A scope allows us to create a package with the same name as a package created by another user or organization without confilct. Scoped packages are preceded by their scope name(the scope name is everything between the `@` and the slash).
        - Unscoped packages are always public and private packages are always scoped!
        - Overview -> package is code somebody else has written and most of the time it's easily integrated to ur projects!
- Dependencies -> Packages that are built using other packages (they are using the package that they are built on to work properly).

- To use a certain package we need to require it first in our file. NPM has tons of packages that we can install and use in our projects. First we search what we need in the [npm website](https://www.npmjs.com/) and there we can find how we can integrade it in our project!
#
2. What is [node.js](https://www.youtube.com/watch?v=ENrzD9HAZK4) -> Node.js is open-source, cross-platform JS runtime environment with focus on the networking applications (or the way developers write JS ot the server).
- The global object is not called `window` like in JS, it's called global!

- Whats Node.js can do:
   - Node.js can generate dynamic page content.
   - Node.js can create, open, read, write, delete, and close files on the server.
   - Node.js can collect form data.
   - Node.js can add, delete, modify data in our database.
#

**The main file -> `index.js`**
- When we require a whole directory, node is going to look for that `index.js` file and whatever that file exports it's what the directory is going to export!<br>In that index.js file we need to require the other `.js` files and export them there.
```js
// first.js:
module.exports = {
  objectOne: objectOne,
};
// second.js:
module.exports = {
  objectTwo: objectTwo,
};
// index.js:
const first = require("./first");
const second = require("./second");

const combined = [first, second];
module.exports ={
    combined: combined
}
```

#
- `process` -> It's an object that provides information about, and cotrol over the current Node.js process(it contains methods, properties etc.)
    - `process.cwd()` -> process the current working directory.
    - `process.argv` -> It returns array that contains command line arguments. These arguments are passed when node.js process was launched (The first two things that are going to show up are: executable path and path of the file that we are running).
    
#
**To require module**
- `What is require` -> It's buildin function that is used to include modules that exist in separate files. The basic functionality is that it reads a JS file, executes the file, and then proceeds to return the exports object.

```js
const fs = require("fs");
//we require fs

fs.mkdir("new_Project");
//we create a directory with fs

fs.writeFile(index.html);
//we create a file with fs

```

**To require a file**
- For example we have two files: math,js and app.js, in math.js we have different formulas that we want to have access to in our app.js file. First we need to use `module.exports` to export the different formulas in the math.js file (which can be done using few methods, my presonal favourite - object export):
```js
const square = x * x;

const multiply = (x, y) => {
  return x * y;
};
const add = (x, y) => {
  return x + y;
};

module.exports = {
  square: square,
  multiply: multiply,
  add: add,
};

```
To use the formulas from the math.js file, now we need to require it in our app.js file using './math' to make it clear we are referring the path in the same directory:
```js
const math = require("./math");

math.square(2);
//4
math.multiply(4, 5);
//20
math.add(3, 7);
//10
```

- Node.js tools:
  - `Express.js` -> It enables the users to build software with JS on the server side. Whole website can be built by using - Node.js to build server-side part of the app and Express.js to publish the app on your website.
  - `Mocha.js` -> That's a JS framework that enables node.js developers to test both in the console and in the browser. It also work for TDD(Test-Driven Development) and BDD(Behaviour Driven Development). Mocha.js modularity is a big advantage because it allows the user to use other libraries.
  - `Chai` -> As an assential tool, chai is mostly used beacause of it's rich plugins(like chai-as-promised, chai-subset, chai-things etc.). Chai is also a TDD and BDD assertion framework.
  - `Sinon.js` -> It's a standalone framework for JS and works with any testing framework. Sinon.js supports stubs, spies and moch and also has cross-platform support.
  - `Passport` -> It's an authentication middleware. It gives a choise of over 300 different ways of authenticating your app including username and password model.
  - `Socket.io` -> That's a framework that enables a bi-directional communication in real time, based on events. It includes real-time analytics with counters and charts.
  - `BlueBird.js` -> BlueBird is promise library that helps to control asynchronous code.

#
3. How to setup project:
- installing npm packeges -> There are 2 ways of installing packages - locally and globall: 
> Generally  we want to install packages locally in the project floder that we want to use the package for (it will be accessable on that specific project folder). To install pcg. we use the npm cli(command line interface) in our terminal - `npm install <package>`
     Usually we will only globally install packages that are meant to be run on our command line in any directory. To install globally - `npm install -g <package>`
     
- `package.json` file -> This file store info(mostly metadata) about our projects like: the name, version, author, github repo etc. and it's super useful if other people want to clone our project and need all the specific packages that we used. <br>To set-up our own json file we need to run - `npm init`. After npm is done asking question about our file it will create the json file.
   - `npm init --y` -> it's going to use the default answers (without asking the questions)
   - `npm list` -> to display all installed packages and the version they are.
   
- `node_modules` folder -> There npm stores all the package files that get installed. Also in that folder we can have other folders that are dependencies of the package that we installed.
   - [`module`](https://docs.npmjs.com/about-packages-and-modules) -> A module is any file or directory in the `node_modules` directory that can be loaded by the Node.js `require()` function.
   - To be loaded by the Node.js require() function, a module must be either a folder with package,json file containing a `main` field or a JS file!

     
#
4. How to add scripts [hint](https://docs.npmjs.com/cli/v6/using-npm/scripts)
- `npm scripts` -> They are the entries in the scripts field of the `package.json file`. The scripts field holds an object where you can specify various commands and scripts that we want to expose. NPM scripts are used to automate tasks in our web project.
   - `npm run <script_name>`
- Adding a script -> We write our own scripts in the package.json file.
 ```js
   {
    "name": "example",
    "scripts": {
      "test": "echo 'hello world'"
    }
  }
  
  npm run test //in the terminal
 ```
---
