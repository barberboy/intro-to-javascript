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
name: syntax

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

[Esprima Parser](http://esprima.org/demo/parse.html)

---
name: comments

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
name: declaring-variables

##  Programming with JavaScript: Variable Declarations

The `var` keyword is used to declare a variable:

```js
var counter;
```

Variables are containers for values. They store values and object references.

```js
var counter = 0;
var course = {};
console.log(counter); // 0
console.log(course);  // {}
```

Variables can be optionally initialized with a value.

---

##  Programming with JavaScript: Variables

- Variables exist in one of two scopes: global scope or function scope
  * No "block" scope
- Variables do not have a type; **values** have a type

```js
var a;
typeof(a) // "undefined"
a = "a";
typeof(a) // "string"
a = 0;
typeof(a) // "number"
```

- Variables declarations are "[hoisted]"

[hoisted]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting

---
name: values-and-types

##  Programming with JavaScript: Values and Types

JavaScript has 6 primitive data types:

 - string - a sequence of characters, `"Howdy"` or `'Howdy'`
 - number - any numeric value, `42`, or `3.141592`
 - boolean -  `true` and `false`
 - null -  a special keyword denoting a `null` value
 - undefined - a value automatically assigned to variables that don't yet have a value
 - symbol - new in ECMAScript 6

--

And one complex data type:

 - object - containers that have properties, and often methods, constructors, and prototypes

---
name: strings

##  Programming with JavaScript: Strings

A string literal is zero or more characters enclosed in double (") or single (')
quotation marks.

```js
var doubleQuoted = "This is a double-quoted string";
var singleQuoted = 'This uses single quotes.';
```

---

##  Programming with JavaScript: Strings

Strings have methods and properties defined on the 
`[String.prototype]` object:

- `.length`: Returns the number of characters in the string

--
```js
"hello".length // => 5
```

--
- `.charAt(index)`: Returns the character at `index`

--
```js
"hello".charAt(1) // => 'e'
```

--
- `.replace(old, new)`: Replaces `old` with `new` in the string

--
```js
"Java is the best".replace("Java", "JavaScript");
// => "JavaScript is the best"
```

--
[And many more][String Instances]

[String.prototype]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/prototype#Description
[String Instances]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#String_instances
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

## Conditionals

---

## Truthiness

---

Grammar and types
-----------------
* Basic syntax & comments
* Declarations
* Variable scope
* Variable hoisting
* Data structures and types
* Literals

---

Control flow and error handling
-------------------------------
* if...else
* switch
* try/catch/throw
* Error objects
* Promises

---

Loops and iteration
-------------------

* for
* while
* do...while
* break/continue
* for..in
* for..of

---

Functions
---------
* Defining functions
* Calling functions
* Function scope
* Closures
* Arguments & parameters
* Arrow functions

---

Expressions and operators
-------------------------
* Assignment & Comparisons
* Arithmetic operators
* Bitwise & logical operators
* Conditional (ternary) operator

---

Numbers and dates
-----------------
* Number literals
* Number object
* Math object
* Date object

---

Text formatting
---------------
* String literals
* String object
* Template strings
* Internationalization
* Regular Expressions

---

Indexed collections
-------------------
* Arrays
* Array comprehensions
* Typed arrays

---

Keyed collections
-----------------
* Map
* WeakMap
* Set
* WeakSet

---

Working with objects
--------------------
* Objects and properties
* Creating objects
* Defining methods
* Getter and setter

---

Details of the object model
---------------------------
* Prototype-based OOP
* Creating object hierarchies
* Inheritance

---