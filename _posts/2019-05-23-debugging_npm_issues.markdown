---
layout: post
title:      "Debugging NPM issues"
date:       2019-05-23 04:14:25 +0000
permalink:  debugging_npm_issues
---


While I was building my final project, a React app for setting reminders about your pets important events, I kept running into environment issues that slowed me down.  This is what I did to fix them.

The errors happend while trying to run `npm start`, and were some version of 
  ```
compiler.hooks.done.tap('done', async stats => {
                                  ^^^^^
SyntaxError: missing ) after argument list
    at createScript (vm.js:56:10)
    at Object.runInThisContext (vm.js:97:10)
    at Module._compile (module.js:542:28)
    at Object.Module._extensions..js (module.js:579:10)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)
    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/Users/adabarto/Documents/flatiron/my-pets/client/node_modules/react-scripts/scripts/start.js:45:5)
```
 or 
` Cannot find module './access-error.js'`
 
The first thing to check is that you only have one package-lock.json file, and that it's inside your project directory.  If you find more than one, It's probably your best bet to delete all of them, cd into your project directory and run `npm install`.

Next, check your Node and npm versions. Make sure they're up to date. 

 `nvm ls` to see which versions of Node you have installed, and which one you're currently using.
 `npm -v` to see which version of npm you're using


`nvm use <version number>` will let you define which version of Node to use.

`npm install -g npm@latest` will upgrade you to the latest version of npm.

If those don't work, try uninstalling then reinstalling Node from scratch.

