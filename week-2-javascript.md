# Week 2: JavaScript

ECMAScript

* JavaScript \(JS\) was beginning popular as a means for dynamic web pages
* A standard was created by ECMA for scripting languages, the standard was based on JS

### Variables and Scopes

We can declare variables using the **var** keyword which gives the variables have function scope. This means that they can be accessed within the function they are declared in \(i.e., lexical scope\).

#### Hoisting

* Weird things happen \(e.g., Not getting an error when accessing variables/calling f before definition\)
* In JavaScript, a variable can be used before it is declared, this is because JavaScript's default behaviour is moving all declarations to the top of the current scope \(to the top of the current script or the current function\)
* All var variables and function declarations are hoisted up to the top of their function scope \(or global scope if not in function\)
  * variable declaration stays in place
* var declarations and definitions are separate

```text
console.log(a) //undefined, not error
var a = 3;

var a; //definition of 'a' is hoisted
console.log(a)
a = 3; //definition executed later
```

For Loops

```text
var i = 8;
function forFunc() {
    for (var i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log(i)
}
forFunc()
console.log(i) // prints out 8; global scope
```

Unexpected Issues - What happens when we don't use var?

Without var, there is no declaration to hoist, so it ends up in global scope

* Now available to everyone in lexical scope
* Hard to manage

"use strict" at the top of the file will help you catch errors and get rid of these unexpected issues

### ES6

* Two new ways to declare variables: let and const, both of which has **block** scope 
  * only the **current block** can access them
  * lexical scope still applies

```text
function f() {

    let a = 3; // block
    if (condition) {
        let b = 4; // block scope
        console.log(a) //3 lexical, block scope
    }  
     
    console.log(a) // 3
    console.log(b) //ERROR! b is undefined
}
```

Const

* Used for variables that will not be re-assigned
* Rule: in this class \(and everywhere else\), default to using const

Is there any benefit to hoisting let and var? Consensus is no...

### Nature of JavaScript

* Functional 
* Object-Oriented

Functions in JS are "first-class objects"

* Stored in variable
* Passed as an argument to a function
* Returned from a function

Functions can be passed around without names, called 'anonymous' functions. We an give it a name for help in stack trace and/or debugging purposes.

Closures

* References to scopes that can be passed around
* Allows function/block scopes to be preserved even after they finish executing
* Function can "carry baggage" with it from where it was created

```text
function foo() {
    let a = 2;
    function inner() {
        console.log(a); // 2
    }
    return inner;
}
const bar = foo(); // foo returns
bar(); // 2
/* Why?
inner carries all the variables that is within its scope
*/
```

### Arrays

```text
const a = [1, 2, "hello"];
```

* The array has a length property attached to it, which implies that it is an object

### Objects

* An object in JS is simple a set of key-value pairs
* Keys are called properties and can be added and changed

**this**

* refers to the containing object of the **call-site** of a function, not where the function is defined
* Context-dependent
  * Values of this is not obvious from reading function definition
  * Unknown until we call it
* Can be changed with bind\(\), call\(\), and apply\(\)

