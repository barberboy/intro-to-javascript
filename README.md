class: middle, center

JavaScript Programming
======================

### An introduction to programming with JavaScript.

---

## What is JavaScript

- Scripting language for the browser
- Developed by Netscape in 1995
- Created by Brendan Eich in **10 days**
- Named JavaScript to convey that it *complemented*, not  *competed* with Java (Sun Microsystems had a partnership with Netscape)
- Designed to be friendly to beginners
- [JavaScript Jabber interview with Brendan Eich](http://devchat.tv/js-jabber/124-jsj-the-origin-of-javascript-with-brendan-eich)

---

## JavaScript Standardization

- JScript implemented by Microsoft for Internet Explorer in 1996
- Push for standardization
- Specification handled by the standards body "Ecma"
- Specification titled "ECMAScript" to avoid Java trademark issues
- Collaboration between Netscape, Microsoft, Borland, and a few others

---

## ECMAScript

- Language evolved: ES3, ES3.1
- <strike>ES4</strike> (killed)
- ES5 Harmony
- ES6 / ES 2015
- ES7 / ES 2016

---

## Server-side JavaScript

- [Node.js](http://nodejs.org)
- Uses Chrome's "V8" JavaScript engine
- Non-blocking event loop
- File and network IO
- [CommonJS Modules 1.1](http://wiki.commonjs.org/wiki/Modules/1.1)
- [npm package repository](npmjs.com)

---
## Writing JavaScript

- Source code saved in a `.js` file (like "`application.js`")
- Code is evaluated and executed:
  - In the browser with the `script` tag and `src` attribute:

    ```html
<script src="application.js"></script>
    ```
  - On the server with Node.js:
  
    ```sh
node application.js
    ```

---

## JavaScript Programming Language

> _ECMAScript is an object-oriented programming language for performing computations and manipulating computational objects within a host environment._

[ECMAScript Specification Overview](http://www.ecma-international.org/ecma-262/6.0/#sec-overview)

Designed to be embedded in a host environment (web page) to allow developers to
receive input from that environment, manipulate it, and provide client-server
communication.

---

## JavaScript Language Features

Syntax based on C/Java

Interpreted
- There is a compilation stage, but it happens immediately before execution.

Dynamically Typed
- All variable references are declared with 'var' keyword
- No `int`, `char`, `double` variable types
 
```c
// C
int index = 0;
char flag = 's';
```

```js
// JavaScript
var index = 0;
var flag = 's';
```
---
## JavaScript Language Features

Dynamically typed
- Variables do not have a type
- BUT
- <u>Values</u> _are_ typed
  
```js
var index = 0  // number type
var flag = 's' // string type
typeof(index)  // -> "number"
typeof(flag)   // -> "string"
flag = 0 
typeof(flag)   // -> "number"
```
---

## JavaScript Language Features

Object-based

- But not traditionally object-oriented
- Objects are created from functions, object literals, or Object.create, but
*not* from classes
- Inheritance is prototype-based, not class-based

---

## JavaScript Language Features

First-class functions. Functions can be:

* Assigned to variables
* Properties of objects
* Passed to other functions
* Returned by functions

---

## JavaScript Language Features

Functions as Constructors

- Functions are used to create new objects:

```js
function Teacher(name) {
    this.name = name;
}
var bebarber = new Teacher("Benjamin Barber");
console.log(bebarber.name); // -> "Benjamin Barber"
```

---

## JavaScript Language Features

Dynamic objects

  - Properties can be added to objects simply by assigning a value to them

```js
var course = {};
course.name = "Web Technologies";
course.instructor = bebarber;
```

---

## Programming with JavaScript: Syntax

JavaScript syntax is inspired by C/Java

- Statements: group of words, numbers, or operators that perform a certain task
- Expressions: variable reference, value, or set of values, possibly combined with operations
- Declarations: expressions that define variables (containers of values) or functions
- Operators: symbols that perform an operation on one or more operands
- Whitespace: spaces, tabs, newlines which separate variables, values, operators, and other tokens
- Comments: source code that is not evaluated, used for documentation and clarification

---

##  Programming with JavaScript: Syntax

- Programs are made up of statements
- Statements are made up of expressions
- Expressions come in many flavors 
- Whitespace separates tokens and provides organization

---

##  Programming with JavaScript: Comments

- C-style line and block comments

```js
// This entire line is ignored

var foo = "bar"; // Everything after // is ignored

/* This is a multi-line
   comment.
*/
```
--

Comments are a crucial language feature. Use them.

---

##  Programming with JavaScript: Values and Types

JavaScript has 6 primitive data types:

 - boolean -  true and false.
 - number - any numeric value, 42, or 3.141592
 - string - a sequence of characters, "Howdy"
 - null -  a special keyword denoting a null value
 - undefined - a value automatically assigned to variables don't yet have a value
 - symbol - new in ECMAScript 6

And one complex data type:

 - object - containers that have properties, and often methods, constructors, and prototypes

---

##  Programming with JavaScript: Booleans

Booleans represent one of two values: `true` or `false`

```js
true
false
```
```js
console.log(typeof true) // -> "boolean"
console.log(typeof false) // -> "boolean"
```
--

(`typeof` operator returns a variable's type)

---

##  Programming with JavaScript: Number

Numbers represent numeric values. Note that there is only *one* number type,
represented in [64-bit double-precision floating-point format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format)

```js
42
3.14159

console.log(typeof 42) // -> "number"
console.log(typeof 3.14159) // -> "number"
```

---
