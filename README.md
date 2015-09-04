class: middle, center
highlightLanguage: javascript
highlightLines: true
highlightSpans: true

JavaScript Programming
======================

### An introduction to programming with JavaScript.



---
class: middle, center
name: what-is-javascript

# What is JavaScript



---
## What is JavaScript

- Scripting language for the browser
- Developed by Netscape in 1995
- Created by Brendan Eich in **10 days**
- Named JavaScript to convey that it *complemented*, not  *competed* with Java (Sun Microsystems had a partnership with Netscape)
- Designed to be friendly to beginners
- [JavaScript Jabber interview with Brendan Eich](http://devchat.tv/js-jabber/124-jsj-the-origin-of-javascript-with-brendan-eich)

---
#### What is JavaScript
## JavaScript Standardization

- JScript implemented by Microsoft for Internet Explorer in 1996
- Push for standardization
- Specification handled by the standards body "Ecma"
- Specification titled "ECMAScript" to avoid Java trademark issues
- Collaboration between Netscape, Microsoft, Borland, and a few others

---
#### What is JavaScript
## ECMAScript

- Language evolved: ES3, ES3.1
- <strike>ES4</strike> (killed)
- ES5 Harmony
- ES6 / ES 2015
- ES7 / ES 2016

---
#### What is JavaScript
## Server-side JavaScript

- [Node.js](http://nodejs.org)
- Uses Chrome's "V8" JavaScript engine
- Non-blocking event loop
- File and network IO
- [CommonJS Modules 1.1](http://wiki.commonjs.org/wiki/Modules/1.1)
- [npm package repository](npmjs.com)

---
#### What is JavaScript
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
class: middle, center

# JavaScript Language Features




---
## JavaScript Language Features

> _ECMAScript is an object-oriented programming language for performing computations and manipulating computational objects within a host environment._

[ECMAScript Specification Overview](http://www.ecma-international.org/ecma-262/6.0/#sec-overview)

Designed to be embedded in a host environment (web page) to allow developers to
receive input from that environment, manipulate it, and provide client-server
communication.

---
## JavaScript Language Features

- Syntax based on C/Java

- Interpreted
  - There is a compilation stage, but it happens immediately before execution.

- Dynamically Typed
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

- Dynamically typed
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

- Object-based

  - But not traditionally object-oriented
  - Objects are created from functions, object literals, or Object.create, but
  *not* from classes
  - Inheritance is prototype-based, not class-based

---
## JavaScript Language Features

- First-class functions. Functions can be:

  - Assigned to variables
  - Properties of objects
  - Passed to other functions
  - Returned by functions

---
## JavaScript Language Features

- Functions as Constructors

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

- Dynamic objects

  - Properties can be added to objects simply by assigning a value to them

    ```js
    var course = {};
    course.name = "Web Technologies";
    course.instructor = bebarber;
    ```



---
name: syntax
class: middle, center

# JavaScript Syntax



---
## JavaScript Syntax

JavaScript syntax is inspired by C/Java

- Statements: group of words, numbers, or operators that perform a certain task
- Expressions: variable reference, value, or set of values, possibly combined with operations
- Declarations: expressions that define variables (containers of values) or functions
- Operators: symbols that perform an operation on one or more operands
- Whitespace: spaces, tabs, newlines which separate variables, values, operators, and other tokens
- Comments: source code that is not evaluated, used for documentation and clarification

---
## JavaScript Syntax

- Programs are made up of statements
- Statements are made up of expressions
- Expressions come in many flavors
- Whitespace separates tokens and provides organization

[Esprima Parser](http://esprima.org/demo/parse.html)



---
name: javascript-programming
class: middle, center

# Programming with JavaScript



---
name: comments

#### Programming with JavaScript
##  Comments

- C-style line comments

  ```js
  // This entire line is ignored
  var foo = "bar"; // Everything after // is ignored
  ```
- and block comments

  ```js
  /* This is a comment that extends
     to the second line */
  ```
--

Comments are a crucial language feature. Use them.

---
name: declaring-variables

#### Programming with JavaScript
## Variable Declarations

The `var` keyword is used to declare a variable:

```js
var counter;
```

Variables are containers for values. They store values and object references.

Variables can be optionally initialized with a value when they are declared, 
using the [Assignment (=) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators#Assignment_2)

```js
var counter = 0;
var course = {};
console.log(counter); // 0
console.log(course);  // {}
```

---
#### Programming with JavaScript
##  Variables

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

- Variable declarations are "[hoisted]"

[hoisted]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#var_hoisting

---
name: values-and-types

#### Programming with JavaScript
## Values and Types

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
#### Programming with JavaScript
## Strings

A [string literal] is zero or more characters enclosed in double (") or single
(') quotation marks. There is no separate "char" type for individual characters.

```js
var doubleQuoted = "This is a double-quoted string";
var singleQuoted = 'This uses single quotes';
var singleChar = 'a';

typeof(doubleQuoted) // "string"
typeof(singleQuoted) // "string"
typeof(singleChar)   // "string"
```

[string literal]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#String_literals

---
name: string-concatenation

#### Programming with JavaScript
## String Concatenation

The [Addition](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Addition)
(`+`) operator is used for string concatenation.

```js
var hello = "Hello";
console.log( hello + " world" );
// => "Hello world"
```

???

The Addition, or "plus" operator is used to concatenate two strings together. 
It is the only mathematical operator that can be used for strings, unlike
languages like Ruby where you can do "hello" * 3 to get "hellohellohello".

--
```js
var greeting = 'Hello ';
var subject = 'World';

greeting += subject; // same as: `greeting = greeting + subject`

console.log( greeting );
// => "Hello world"
```

???

You can also use the Addition Assignment operator, which is the equivalent of
doing `hello = hello + "Hello"`.

---
#### Programming with JavaScript
##  String Properties and Methods

Strings have methods and properties defined on the 
[`String.prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/prototype#Description) object:

--
- `.length`: A property which reflects the number of characters in the string
--

```js
"hello".length // => 5
```

--
- `.charAt(index)`: Method which returns the character at `index`
--

```js
"hello".charAt(1) // => 'e'
```

--
- `.replace(old, new)`: Method which returns a new string with `old` replaced with with `new`
--

```js
"Java is the best".replace("Java", "JavaScript");
// => "JavaScript is the best"
```

???

Now, a caveat with the 'replace' method: it only replaces the *first* instance
of `old` with `new`. If we need to do multiple replacements, we need to use
regular expressions.

--

[And many more](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#String_instances)

---
name: numbers
#### Programming with JavaScript
## Numbers

Numbers represent numeric values. Note that there is only *one* number type,
represented in [64-bit double-precision floating-point format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format)

```js
var answer = 42;
var pi = 3.14159;

typeof(answer) // => "number"
typeof(pi)     // => "number"
```

---
#### Programming with JavaScript
## Number Properties and Methods

Numbers have a few methods and properties defined on the 
[`Number.prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#Methods_2) object:

- `.toString()`: Returns the value of the number as a string

--
```js
var days = 30;
days.toString(); // => "30"
```

--
- [`.toFixed(digits)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed):
  Returns the number as a string, rounded to `digits` digits and padded if necessary.

--
```js
var pi = 3.141592654;
pi.toFixed(4);   // => "3.1416"
var price = 3;
price.toFixed(2) // => "3.00"
```
---
name: operators
#### Programming with JavaScript
## Operators: Arithmetic

  - Addition
  - Subtraction
  - Multiplication
  - Division
  - Modulus

---
#### Programming with JavaScript
## Operators: Arithmetic Assignment

  - Addition
  - Subtraction
  - Multiplication
  - Division
  - Modulus

---
name: bitwise-operators
#### Programming with JavaScript
## Operators: Bitwise Operators

- Treat their operands as 32-bit binary numbers, converting as necessary
- Returns standard numerical values

Reference: [Bitwise Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)
on [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

---
#### Programming with JavaScript
## Math

The global [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
object has utilities for dealing with numbers.

--
- Math.round(x): Returns the value of a number rounded to the nearest integer.
--

```js
Math.round(3.14)   // => 3
Math.round(1.618)  // => 2
Math.round(-3.14)  // => -3
Math.round(-1.618) // => -2
```

--
- Math.trunc(x): Returns the integral part of the number x, removing any fractional digits.
--

```js
Math.trunc(3.14)   // => 3
Math.trunc(1.618)  // => 1
Math.trunc(-3.14)  // => -3
Math.trunc(-1.618) // => -1
```
---
#### Programming with JavaScript
## Math

The global [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
object has utilities for dealing with numbers.

- Math.ceil(x): Returns the smallest integer greater than or equal to a number.
--

```js
Math.ceil(3.14)   // => 4
Math.ceil(1.618)  // => 2
Math.ceil(-3.14)  // => -3
Math.ceil(-1.618) // => -1
```

--
- Math.floor(x): Returns the largest integer less than or equal to a number.
--

```js
Math.floor(3.14)   // => 3
Math.floor(1.618)  // => 1
Math.floor(-3.14)  // => -4
Math.floor(-1.618) // => -2
```

---
#### Programming with JavaScript
## Math

Additional utilities:

<dl>
<dt>Math.max([x[, y[, …]]])</dt>
<dd>Returns the largest of zero or more numbers.</dd>
<dt>Math.min([x[, y[, …]]])</dt>
<dd>Returns the smallest of zero or more numbers.</dd>
<dt>Math.pow(x, y)</dt>
<dd>Returns base to the exponent power, that is, base<sup>exponent</sup>.</dd>
<dt>Math.random()</dt>
<dd>Returns a pseudo-random number between 0 and 1.</dd>
<dt>Math.abs(x)</dt>
<dd>Returns the absolute value of a number.</dd>
</dl>

---
#### Programming with JavaScript
## Booleans

Booleans represent one of two values: `true` or `false`. The keyword `true`
(lowercase) and `false` (lowercase) are the only two boolean types.

```js
var answer = true;
var differentAnswer = false;

console.log(typeof answer) // => "boolean"
```

---
#### Programming with JavaScript
## Conditionals

* if...else
* ternary operator

---
#### Programming with JavaScript
## Logical Operators

* Logical AND
* Logical OR
* Logical NOT

---
#### Programming with JavaScript
## Truthiness

---

---
#### Programming with JavaScript
## Loops and iteration

* for
* while
* do...while
* break/continue
* for..in

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

Indexed collections
-------------------
* Arrays

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
