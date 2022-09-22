# NPM and NodeJS
 1. What is NPM -> npm is the world's lagerst Software Library and also a sofware Package Manager and Installer. It's the main package manager for node.js .
- [About packages](https://docs.npmjs.com/about-packages-and-modules) -> A package is a file or directory that is described by a `package.json` file and that package must contain a package.json file in order to be published to the npm registry. 
    - These packages can be scoped or unscoped -> A scope allows us to create a package with the same name as a package created by another user or organization without confilct. Scoped packages are preceded by their scope name(the scope name is everything between the `@` and the slash).
        - Unscoped packages are always public and private packages are always scoped!
- Dependencies -> Packages that are built using other packages (they are using the package that they are built on to work properly).

#
2. What is [node.js](https://www.youtube.com/watch?v=ENrzD9HAZK4) -> Node.js is open-source, cross-platform JS runtime environment with focus on the networking applications (or the way developers write JS ot the server).
- Whats Node.js can do:
   - Node.js can generate dynamic page content.
   - Node.js can create, open, read, write, delete, and close files on the server.
   - Node.js can collect form data.
   - Node.js can add, delete, modify data in our database.
   
- Node.js tools:
  - `Mocha.js` -> That's a JS framework that enables node.js developers to test both in the console and in the browser. It also work for TDD(Test-Driven Development) and BDD(Behaviour Driven Development). Mocha.js modularity is a big advantage because it allows the user to use other libraries.
  - `Chai` -> As an assential tool, chai is mostly used beacause of it's rich plugins(like chai-as-promised, chai-subset, chai-things etc.). Chai is also a TDD and BDD assertion framework.
  - `Sinon.js` -> It's a standalone framework for JS and works with any testing framework. Sinon.js supports stubs, spies and moch and also has cross-platform support.
  - `Express.js` -> It enables the users to build software with JS on the server side. Whole website can be built by using - Node.js to build server-side part of the app and Express.js to publish the app on your website.
  - `Passport` -> It's an authentication middleware. It gives a choise of over 300 different ways of authenticating your app including username and password model.
  - Socket.io -> That's a framework that enables a bi-directional communication in real time, based on events. It includes real-time analytics with counters and charts.
  - BlueBird.js -> BlueBird is promise library that helps to control asynchronous code.

#
3. How to setup project:
- installing npm packeges -> There are 2 ways of installing packages - locally and globall: 
> Generally  we want to install packages locally in the project floder that we want to use the package for (it will be accessable on that specific project folder). To install pcg. we use the npm cli(command line interface) in our terminal - `npm install <package>`
     Usually we will only globally install packages that are meant to be run on our command line in any directory. To install globally - `npm install -g <package>`
     
- `package.json` file -> This file store info about our projects like: the name, version, author, github repo etc. and it's super useful if other people want to clone our project and need all the specific packages that we used. <br>To set-up our own json file we need to run - `npm init`. After npm is done asking question about our file it will create the json file.
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
