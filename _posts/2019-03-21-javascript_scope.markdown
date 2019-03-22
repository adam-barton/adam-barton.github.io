---
layout: post
title:      "JavaScript Scope"
date:       2019-03-21 22:14:45 -0400
permalink:  javascript_scope
---


I'm writing this beginner's guide to JavaScript scopes to help solidify my understanding. 


The basic types of scope are:  
* **Global scope** - Variables and functions declared in the global scope are available everywhere. 
Global variables declared without `const` `let` or `var`, are always in the global scope.
*  **Function scope** - Variables and functions declared inside functions are only available within that function.
* **Block scope** - Variables or functions declared with `const` or `let` inside a block are only available inside that block. 
`var` does not support block scoping. 

When a function is declared inside another function, the inner function has access to both function's variables and data. The outer function does not have access to the inner function's scope. In other words, scopes cascade from the inside out, but not the outside in.



Examples:

```
const myName = "Adam" //is in the global scope

const sayHiTo = (name) => {
    const z = "This function scoped variable is available to 'sayHiTo()' and 'sayMyName()'"
   const sayMyName = () => {
        const x = "this function scoped variable is only available inside of 'sayMyName()'"
        y = "this is a global variable"
        console.log(z)
        return myName
    } 
    return `Hi ${name}, i'm ${sayMyName()}.`
}
```


`sayHiTo()` is a function defined in the global scope, so it has access to other variables and functions in the global scope. 

`sayMyName()` is a function defined within `sayHiTo()`, so it has access to `sayMyName()`, `sayHiTo()` and the global scopes

`const x` is inside the `sayMyName()` scope, so it is only available inside that function.
 
 
Block Scope example: 

```
const blockScope = () => {

    if (true) {
        const a = "some thing"
        let b = "another thing"
        var c = "one more thing"  
    }
    console.log(a)
    console.log(b)
    console.log(c)
}
```


Inside the `if (true)` block, `a` `b` and `c` variables are declared and assigned values. Because `const` and `let` support block scope, those variable reassignments are only available in that block.  Trying to log them to the console will throw an error. `var` doesn't support block scope so that variable will be available outside of the block. 

