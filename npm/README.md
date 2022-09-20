# NPM and [NodeJS](https://www.youtube.com/watch?v=ENrzD9HAZK4)
 1. What is NPM -> npm is the world's lagerst Software Library and also a sofware Package Manager and Installer. It's the main package manager for node.js .
- Dependencies -> Packages that are built using other packages (they are using the package that they are built on to work properly).
2. What is Node.js -> Node.js is open-source, cross-platform JS runtime environment with focus on the networking applications.
- Whats Node.js can do:
   - Node.js can generate dynamic page content.
   - Node.js can create, open, read, write, delete, and close files on the server.
   - Node.js can collect form data.
   - Node.js can add, delete, modify data in our database.

3. How to setup project:
- installing npm packeges -> There are 2 ways of installing packages - locally and globall: 
> Generally  we want to install packages locally in the project floder that we want to use the package for (it will be accessable on that specific project folder). To install pcg. we use the npm cli(command line interface) in our terminal - `npm install <package>`
     Usually we will only globally install packages that are meant to be run on our command line in any directory. To install globally - `npm install -g <package>`
     
- `package.json` file -> This file store info about our projects like: the name, version, author, github repo etc. and it's super useful if other people want to clone our project and need all the specific packages that we used. <br>To set-up our own json file we need to run - `npm init`. After npm is done asking question about our file it will create the json file.
   - `npm init --y` -> it's going to use the default answers (without asking the questions)
   
- `node_modules` folder -> There npm stores all the package files that get installed. Also in that folder we can have other folders that are dependencies of the package that we installed.
- `npm list` -> to display all installed packages and the version they are.
     
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
