class: middle, center

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
- [npm package repository](https://npmjs.com)

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
    
    ```
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
  
    ```
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

    ```
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

    ```
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

  ```
  // This entire line is ignored
  var foo = "bar"; // Everything after // is ignored
  ```
- and block comments

  ```
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

```
var counter;
```

Variables are containers for values. They store values and object references.

Variables can be optionally initialized with a value when they are declared, 
using the [Assignment (=) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators#Assignment_2)

```
var counter = 0;
var course = {};
console.log(counter); // 0
console.log(course);  // {}
```

---
#### Programming with JavaScript
##  Variables

- Variables exist in one of two scopes: [global scope or function scope](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#Description)
  * No "block" scope
- Variables do not have a type; **values** have a type

```
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

And one complex data type:

 - object - containers that have properties, and often methods, constructors, and prototypes



---
name: strings
class: middle, center

# Programming with JavaScript
# Strings




---
#### Programming with JavaScript
## Strings

A [string literal] is zero or more characters enclosed in double (") or single
(') quotation marks. There is no separate "char" type for individual characters.

```
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

```
var hello = "Hello";
console.log( hello + " world" );
// => "Hello world"
```

???

The Addition, or "plus" operator is used to concatenate two strings together. 
It is the only mathematical operator that can be used for strings, unlike
languages like Ruby where you can do "hello" * 3 to get "hellohellohello".

--
```
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

- `.length`: A property which reflects the number of characters in the string
```
"hello".length // => 5
```

- `.charAt(index)`: Method which returns the character at `index`
```
"hello".charAt(1) // => 'e'
```

- `.replace(old, new)`: Method which returns a new string with `old` replaced with with `new`
```
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
class: middle, center

# Programming with JavaScript
# Numbers



---
#### Programming with JavaScript
## Numbers

Numbers represent numeric values. Note that there is only *one* number type,
represented in [64-bit double-precision floating-point format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format)

```
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
```
var days = 30;
days.toString(); // => "30"
```
- [`.toFixed(digits)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed):
  Returns the number as a string, rounded to `digits` digits and padded if necessary.
```
var pi = 3.141592654;
pi.toFixed(4);   // => "3.1416"
var price = 3;
price.toFixed(2) // => "3.00"
```
---
name: operators
#### Programming with JavaScript
## Operators: Arithmetic

- `+` Addition operator
  ```
  3 + 4 // => 7
  ```
- `-` Subtraction operator
  ```
  3 - 4 // => -1
  ```
---
#### Programming with JavaScript
## Operators: Arithmetic

- `*` Multiplication operator
  ```
  3 * 4 // => 12
  ```
- `/` Division operator
  ```
  3 / 4 // => 0.75
  ```
- `%` Remainder operator
  ```
  4 % 3 // => 1
  ```
---
#### Programming with JavaScript
## Operators: Arithmetic Assignment

- `+=` Addition assignment: adds the value of the right operand to a variable and 
  assigns the result to the variable
  ```
  var x = 10;
  x += 5;    // Equivalent to: x = x + 5
  ```

- `-=` Subtraction assignment
- `*=` Multiplication assignment
- `/=` Division assignment 
- `%=` Modulus assignment 

[Assignment operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment_Operators#Addition_assignment_2)
on MDN

---

#### Programming with JavaScript
## Operators: Increment

- `++` Increment operator: increase a reference’s value by one and return the new value

???
The "Increment" or "plus plus" operator adds one to the value of a variable
or property. It comes in two different forms:

--
  - Postfix: Return the original value **before** incrementing
    ```
    var a = 3;
    var b = a++;     // b: 3, a: 4
    ```
???
Both forms return a value.
 - The postfix form:
 
    The postfix form returns the value prior to
    incrementing it. In this case, the value **3** is assigned to the variable `b`,
    **then** the variable `a` is incremented.
--
  - Prefix: Return the new (incremented) value
    ```
    var a = 3;
    var b = ++a;     // b: 4, a: 4
    ```
???
 - Prefix form

   With the prefix form, the incremented value is returned. In this case, the
   variable `a` is incremented to `4`, then `b` is assigned the value 4.

---

#### Programming with JavaScript
## Operators: Decrement

- `--` Decrement operator: decrease a reference’s value by one and return the new value
  - Postfix: Return the original value **before** decrementing
    ```
    var a = 3;
    var b = a--;     // b: 3, a: 2
    ```
  - Prefix: Return the new (decremented) value
    ```
    var a = 3;
    var b = --a;     // b: 2, a: 2
    ```
---
name: bitwise-operators
#### Programming with JavaScript
## Operators: Bitwise Operators

- Treats operands as 32-bit binary numbers, converting as necessary
- Returns standard numerical values

Reference: [Bitwise Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)
on [Mozilla Developer Network (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)

---
#### Programming with JavaScript
## Math

The global [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
object has utilities for dealing with numbers.

- `Math.round(x)` : Returns the value of a number rounded to the nearest integer.

```
Math.round(3.14)   // =>  3
Math.round(1.618)  // =>  2
Math.round(-3.14)  // => -3
Math.round(-1.618) // => -2
```

- `Math.trunc(x)` : Returns the integral part of the number x, removing any fractional digits.

```
Math.trunc(3.14)   // =>  3
Math.trunc(1.618)  // =>  1
Math.trunc(-3.14)  // => -3
Math.trunc(-1.618) // => -1
```
---
#### Programming with JavaScript
## Math

The global [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
object has utilities for dealing with numbers.

- `Math.ceil(x)` : Returns the smallest integer greater than or equal to a number.

```
Math.ceil(3.14)   // =>  4
Math.ceil(1.618)  // =>  2
Math.ceil(-3.14)  // => -3
Math.ceil(-1.618) // => -1
```

- `Math.floor(x)` : Returns the largest integer less than or equal to a number.

```
Math.floor(3.14)   // =>  3
Math.floor(1.618)  // =>  1
Math.floor(-3.14)  // => -4
Math.floor(-1.618) // => -2
```

---
#### Programming with JavaScript
## Math

Additional utilities:

- `Math.max([x[, y[, …]]])` : Returns the largest of zero or more numbers
- `Math.min([x[, y[, …]]])` : Returns the smallest of zero or more numbers
- `Math.pow(x, y)` : Returns base to the exponent power, that is, base<sup>exponent</sup>
- `Math.random()` : Returns a pseudo-random number between 0 and 1
- `Math.abs(x)` : Returns the absolute value of a number

Reference: [`Math` global object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

---
name: booleans
class: middle, center

# Programming with JavaScript
# Booleans



---
#### Programming with JavaScript
## Booleans

Booleans represent one of two values: `true` or `false`. The keyword `true`
(lowercase) and `false` (lowercase) are the only two boolean types.

```
var answer = true;
var differentAnswer = false;

console.log(typeof answer) // => "boolean"
```

---
#### Programming with JavaScript
## Comparison operators

The most common use of Booleans are as the result of equality or comparison operators.

```
var aGrade = 93;
var yourGrade = 97;
*var hasA = yourGrade >= aGrade;

console.log(hasA);  // => true
```

---
#### Programming with JavaScript
## Equality operators

- `==` Equality
- `===` Strict/identity equality
- `!=` Inequality
- `!==` Strict/identity inequality

[Equality operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Equality_operators)

---
#### Programming with JavaScript
## Equality operator

```js
x == y
```

The equality operator **converts** the operands if they are not of the same type, then applies strict comparison. If both operands are objects, then JavaScript compares internal references which are equal when operands refer to the same object in memory.

```js
console.log(1 == 1);      // => true
console.log(1 == '1');    // => true
console.log(true == '1'); // => true
console.log(0 == 0);      // => true
console.log(0 == '0');    // => true
console.log(0 == '');     // => true
console.log(false == '0');// => true
var x = {};
var y = x;
console.log(x == y);       // => true
```

---
#### Programming with JavaScript
## Inequality operator

```js
x != y
```

The inequality operator **converts** operands if they are not of the same type, then returns true if the operands are **not** equal.

```js
console.log(1 != 1);      // => false
console.log(1 != '1');    // => false
console.log(true != '1'); // => false
console.log(1 != 0);      // => true
console.log('apples' != 'oranges'); // => true
var x = {};
var y = {};
console.log(x != y);      // => true
```

---
#### Programming with JavaScript
## Identity / strict equality operator

```js
x === y
```

The identity operator returns true if the operands are strictly equal (see above) with no type conversion.

```js
console.log(1 === 1);      // => true
console.log(1 === '1');    // => false
console.log(true === '1'); // => false
console.log(0 === 0);      // => true
console.log(0 === '0');    // => false
console.log(0 === '');     // => false
console.log(false === '0');// => false
var x = {};
var y = x;
console.log(x === y);       // => true
```

---
#### Programming with JavaScript
## Identity / strict inequality operator

```js
x !== y
```

The non-identity operator returns true if the operands are not equal and/or not of the same type.

```js
console.log(1 !== '1') // true
console.log(1 !== 2)   // true
```

---
#### Programming with JavaScript
## Relational operators

- `>` Greater than
  ```
  3 > 4 // => false
  4 > 4 // => false
  5 > 4 // => true
  ```
- `>=` Greater than or equal
  ```
  3 >= 4 // => false
  4 >= 4 // => true
  5 >= 4 // => true
  ```
  
---
#### Programming with JavaScript
## Relational operators

- `<` Less than operator
  ```
  3 < 4 // => true
  4 < 4 // => false
  5 < 4 // => false
  ```
- `<=` Less than or equal
  ```
  3 <= 4 // => true
  4 <= 4 // => true
  5 <= 4 // => false
  ```

[Relational operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators#Relational_operators)

---
#### Programming with JavaScript
## If statement

```js
if (condition)
   statement1
else               // optional `else`
   statement2
```

Executes `statement1` if a `condition` is true. If `condition` is false, statement2 is executed.

[if...else statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)

---
#### Programming with JavaScript
## Conditional (ternary) operator

```js
condition ? expression1 : expression2
```

Return `expression1` if `condition` is true, otherwise return `expression2`

[Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

---
#### Programming with JavaScript
## If versus Conditional

```js
var n1 = 100;
var n2 = 98;
var max;

if(n1 >= n2) {
    max = n1;
}
else {
    max = n2;
}
console.log(max);
```

---
#### Programming with JavaScript
## If versus Conditional

```js
var n1 = 100;
var n2 = 98;
var max = (n1 >= n2) ? n1 : n2;

console.log(max);
// => 100
```

---
#### Programming with JavaScript
## Logical operators

- `&&` &nbsp; Logical AND
- `||` &nbsp; Logical OR
- `!` &nbsp; &nbsp; Logical NOT

[Logical operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators)

---
#### Programming with JavaScript
## Logical AND

Returns `expr1` if it can be converted to false; otherwise, returns `expr2`.

When used with Boolean values, `&&` returns `true` if both operands are `true`; otherwise, returns `false`.

```js
expr1 && expr2
```

```js
var grade = 95;
var letter;
*if( grade >= 93 && grade < 100) {
    letter = 'A';
}
console.log(letter);
// => "A"
```

---
#### Programming with JavaScript
## Logical OR

Returns `expr1` if it can be converted to `true`; otherwise, returns `expr2`.

When used with Boolean values, `||` returns `true` if either operand is `true`; if both are `false`, returns `false`.

```js
expr1 || expr2
```

```js
var letter = 'A';

*if(letter === 'A' || letter === 'B' || letter === 'C') {
    console.log('Pass');
}
else {
    console.log('Fail');
}
// => "Pass"
```
---
#### Programming with JavaScript
## Logical NOT

Returns false if its single operand can be converted to true; otherwise, returns true.

```js
!expr1
```

```js
var day = false;
*if( !day ) {
    console.log("It is night.")
}
// => "It is night"

```

---
#### Programming with JavaScript
## Truthiness

JavaScript coerces primitives and objects to a Boolean when a Boolean is expected.

Truthy : a value is “truthy” if it is not “falsy.”

---
#### Programming with JavaScript
## Falsy

The following 6 values are considered `false` in a boolean context:

- `false` 
- `0`
- `''` (empty string)
- `null`
- `undefined`
- `NaN`

---
#### Programming with JavaScript
## Truthy

The following values (among many others) are considered `true` in a boolean context:

- `true`
- `"hi"`
- `12`
- `-1`
- [] (empty array)
- {} (empty object)



---
name: loops
class: middle, center

# Programming with JavaScript
# Loops and iteration



---
#### Programming with JavaScript
## Loops and iteration

* while
* do...while
* for
* break/continue
* for..in

---
#### Programming with JavaScript
## `while` loops

Syntax:

```
while (condition)
   statement
```

The while statement creates a loop that executes a specified statement as long 
as the test condition evaluates to true. The condition is evaluated before
executing the statement.

[`while` loop reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)

---
#### Programming with JavaScript
## `while` loops

Example:

```
var x = 0;

while (x <= 10) {
   console.log( x );
   x++;
}
```

---
#### Programming with JavaScript
## `do…while` loops

Syntax:

```
do
  statement 
while (condition)
   
```

The `do…while` statement creates a loop that executes `statement`  until the
`condition` evaluates to false. Since the condition is evaluated after
executing the statement, the specified statement will execute at least once.

[`do…while` loop reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)

---
#### Programming with JavaScript
## `do…while` loops

Example:

```
var x = 0;
do {
   x++;
   console.log( x );
} while (x <= 10)

```

---
#### Programming with JavaScript
## `for` loops

Syntax:

```
for ([initialization]; [condition]; [final-expression])
   statement
```

[`for` reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)

---
#### Programming with JavaScript
## `for` loops

Example:

```
for (var i = 1; i <= 10; i++) {
   console.log( i );
}
```

---
#### Programming with JavaScript
## `for` loops: Arrays

A common use case for `for` loops is looping through array values:

```
var scores = [89, 98, 92, 69, 87, 53];
for (var i = 0; i < scores.length; i++) {
   console.log( scores[i] );
}
```

---
#### Programming with JavaScript
## `for` loops: Arrays

A quick performance optimization is to cache the length of the array:

```
var scores = [89, 98, 92, 69, 87, 53];
for (var i = 0, len = scores.length; i < len; i++) {
   console.log( scores[i] );
}
```
---
name: arrays
class: middle, center

# Programming with JavaScript
# Arrays


---
#### Programming with JavaScript
## Arrays

An array is an ordered set of numerically-indexed values.

Arrays can be created using the global `Array` function (not recommended) or by
using the [Array literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#Array_literals): `[]`

```
var empty = [];
var scores = [88, 75, 84, 100, 77, 105, 86];
var books = ["To Kill a Mockingbird", "Prince Caspian", "The Hitchhiker’s Guide to the Galaxy"]
```

Array values can accessed (or assigned) by a numeric index

```
console.log( books[0] );  // => "To Kill a Mockingbird"
books[0] = "Fellowship of the Ring";
console.log( books[0] );  // => "Fellowship of the Ring"
```

[Introduction to Arrays on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)

---
#### Programming with JavaScript
## Array methods: push

`push()` adds one or more elements to the end of an array and returns the resulting length of the array.

```
var myArray = ["1", "2"]
myArray.push("3"); // myArray is now ["1", "2", "3"]
```

---
#### Programming with JavaScript
## Array methods: concat

`concat()` joins two arrays and returns a new array

```
var myArray = ["1", "2", "3"]
myArray = myArray.concat(["a", "b", "c"]);
// myArray is now ["1", "2", "3", "a", "b", "c"]
```
---
#### Programming with JavaScript
## Array methods: join

`join(deliminator = ',')` joins all elements of an array into a string.

```
var myArray = ["Wind", "Rain", "Fire"];
var list = myArray.join(" - "); // list is "Wind - Rain - Fire"
```

---
#### Programming with JavaScript
## Array methods: push

`push()` adds one or more elements to the end of an array and returns the resulting length of the array.

```
var myArray = ["1", "2"];
myArray.push("3"); // myArray is now ["1", "2", "3"]
```

---
#### Programming with JavaScript
## Array methods: pop

`pop()` removes the last element from an array and returns that element.

```
var myArray = ["1", "2", "3"];
var last = myArray.pop(); 
// myArray is now ["1", "2"], last = "3"
```

---
#### Programming with JavaScript
## Array methods: shift

`shift()` removes the first element from an array and returns that element.

```
var myArray = ["1", "2", "3"];
var first = myArray.shift(); 
// myArray is now ["2", "3"], first is "1"
```

---
#### Programming with JavaScript
## Array methods: unshift

`unshift()` adds one or more elements to the front of an array and returns the 
new length of the array.

```
var myArray = ["1", "2", "3"];
myArray.unshift("4", "5"); 
// myArray becomes ["4", "5", "1", "2", "3"]
```
---
#### Programming with JavaScript
## Array methods: slice

`slice(start_index, upto_index)` extracts a section of an array and returns a 
new array.

```
var myArray = ["a", "b", "c", "d", "e"];
myArray = myArray.slice(1, 4); 
// starts at index 1 and extracts all elements until index 3,
// returning [ "b", "c", "d"]
```

---
#### Programming with JavaScript
## Array methods: splice

`splice(index, count_to_remove, addElement1, addElement2, ...)` removes elements
from an array and (optionally) replaces them.

```
var myArray = ["1", "2", "3", "4", "5"];
myArray.splice(1, 3, "a", "b", "c", "d"); 
// myArray is now ["1", "a", "b", "c", "d", "5"]
// This code started at index one (or where the "2" was), 
// removed 3 elements there, and then inserted all consecutive
// elements in its place.
```

---
#### Programming with JavaScript
## Array methods: reverse

`reverse()` transposes the elements of an array: the first array element becomes
the last and the last becomes the first.

```
var myArray = ["1", "2", "3"];
myArray.reverse(); 
// transposes the array so that myArray = [ "3", "2", "1" ]
```

---
#### Programming with JavaScript
## Array methods: sort

`sort([sortFunction])` sorts the elements of an array.

```
var myArray = ["Wind", "Rain", "Fire"];
myArray.sort(); 
// sorts the array so that myArray = [ "Fire", "Rain", "Wind" ]
```

---
#### Programming with JavaScript
## Array methods: sort

`sort()` can also take a callback function to determine how array elements are 
compared. The function compares two values and returns one of three values:

- if a is **less than** b by the sorting system, return `-1` (or any negative 
  number)
- if a is **greater than** b by the sorting system, return `1` (or any positive
  number)
- if a and b are considered **equivalent**, return `0`.

For instance, the following will sort by the last letter of a string:

```
var sortFn = function(a, b){
  if (a[a.length - 1] < b[b.length - 1]) return -1;
  if (a[a.length - 1] > b[b.length - 1]) return 1;
  if (a[a.length - 1] == b[b.length - 1]) return 0;
}
myArray.sort(sortFn); 
// sorts the array so that myArray = ["Wind","Fire","Rain"]
```

---
#### Programming with JavaScript
## Array methods: indexOf

`indexOf(searchElement[, fromIndex])` searches the array for `searchElement` and
returns the index of the first match.

```
var a = ['a', 'b', 'a', 'b', 'a'];
console.log(a.indexOf('b')); // logs 1
// Now try again, starting from after the last match
console.log(a.indexOf('b', 2)); // logs 3
console.log(a.indexOf('z')); // logs -1, because 'z' was not found
```

---
#### Programming with JavaScript
## Array methods: lastIndexOf

`lastIndexOf(searchElement[, fromIndex])` works like `indexOf()`, but starts at 
the end and searches backwards.

```
var a = ['a', 'b', 'c', 'd', 'a', 'b'];
console.log(a.lastIndexOf('b')); // logs 5
// Now try again, starting from before the last match
console.log(a.lastIndexOf('b', 4)); // logs 1
console.log(a.lastIndexOf('z')); // logs -1
```

---
#### Programming with JavaScript
## Array methods: forEach

`forEach(callback[, thisObject])` executes `callback` on every array item.

```
var a = ['a', 'b', 'c'];
a.forEach(function(element) { console.log(element);} ); 
// logs each item in turn
```

---
#### Programming with JavaScript
## Array methods: map

`map(callback[, thisObject])` returns a new array of the return value from 
executing `callback` on every array item.

```
var a1 = ['a', 'b', 'c'];
var a2 = a1.map(function(item) { return item.toUpperCase(); });
console.log(a2); // logs A,B,C
```

---
#### Programming with JavaScript
## Array methods: filter

`filter(callback[, thisObject])` returns a new array containing the items for 
which `callback` returned `true`.

```
var a1 = ['a', 10, 'b', 20, 'c', 30];
var a2 = a1.filter(function(item) {
  return typeof item == 'number';
});
console.log(a2); // logs 10,20,30
```

---
#### Programming with JavaScript
## Array methods: every

`every(callback[, thisObject])` returns `true` if `callback` returns `true` for 
every item in the array.

```
function isNumber(value){
  return typeof value == 'number';
}
var a1 = [1, 2, 3];
console.log(a1.every(isNumber)); // logs true
var a2 = [1, '2', 3];
console.log(a2.every(isNumber)); // logs false
```

---
#### Programming with JavaScript
## Array methods: some

`some(callback[, thisObject])` returns `true` if `callback` returns `true` for 
at least one item in the array.

```
function isNumber(value){
  return typeof value == 'number';
}
var a1 = [1, 2, 3];
console.log(a1.some(isNumber)); // logs true
var a2 = [1, '2', 3];
console.log(a2.some(isNumber)); // logs true
var a3 = ['1', '2', '3'];
console.log(a3.some(isNumber)); // logs false
```
---
#### Programming with JavaScript
## Array methods: reduce

`reduce(callback[, initialValue])` applies `callback(firstValue, secondValue)` 
to reduce the list of items down to a single value.

```
var a = [10, 20, 30];
var total = a.reduce(function(first, second) {
  return first + second; 
}, 0);
console.log(total) // Prints 60
```

`reduceRight(callback[, initalvalue])` works like `reduce()`, but starts with 
the last element.

reduce and reduceRight are the least obvious of the iterative array methods. 
They should be used for algorithms that combine two values recursively in order 
to reduce a sequence down to a single value.

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
