# Vanila JS
## Basics
- JavaScript provides seven different data types which are undefined, null, boolean, string, symbol, number, and object.
- When JavaScript variables are declared, they have an initial value of undefined, mathematical operation on them => NaN, concatenation => undefined
- Number is a data type in JavaScript which represents numeric data.
- String values in JavaScript may be written with single or double quotes, as long as you start and end with the same type of quote. Unlike some other programming languages, single and double quotes work the same in JavaScript.
- In JavaScript, String values are immutable, which means that they cannot be altered once created.  Note that this does not mean that myStr cannot be changed, just that the individual characters of a string literal cannot be changed.
- Switch statement - case values are tested with strict equality (===)

## Object

- Objects are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties. [code example](#Objects);
- There are two ways to access the properties of an object: dot notation (.property) and bracket notation (["property"]), similar to an array. You can add new properties to existing JavaScript objects the same way you would modify them.
-We can also delete properties from objects like this:
```javascript
delete ourDog.bark;
```
- .hasOwnProperty(propname) method of objects to determine if that object has the given property name. .hasOwnProperty() returns true or false if the property is found or not.
## Operators
- % The remainder operator is sometimes incorrectly referred to as the "modulus" operator. It is very similar to modulus, but does not work properly with negative numbers.
- escape char in String :
```sh
\'	single quote    
\"	double quote
\\	backslash
\n	newline
\r	carriage return
\t	tab
\b	backspace
\f	form feed
```

- length of a String value by writing .length
- ==  The equality operator compares two values and returns true if they're equivalent or false if they are not.
- === is the counterpart to the equality operator (==). However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion. [code examples](#comparison)
- parseInt() function parses a string and returns an integer. Here's an example


## Arrays
-  .push() takes one or more parameters and "pushes" them onto the end of the array.
-  .unshift() takes one or more parameters and "pushes" them at the beginning of the array.
-  .pop() removes the last element from an array and returns that element
-  .shift() removes the first element from an array and returns that element

### Variables
- In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have Global scope. This means, they can be seen everywhere in your JavaScript code.
- Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.
- Variables which are declared within a function, as well as the function parameters have local scope. That means, they are only visible within that function.
- It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.
-
## Code snippets

- Array : var sandwich = ["peanut butter", "jelly", "bread"]
- arr[0][1] - second element from first array in array of arrays
- function testFun(param1, param2) {
  console.log(param1, param2);
}

#### Comparison
```javascript
1 == 1 // true
1 == 2 // false
1 == '1' // true
"3" == 3 // true
3 === 3 // true
3 === '3' // false
1 != 2 // true
1 != "1" // false
1 != '1' // false
1 != true // false
0 != false // false
3 !== 3 // false
3 !== '3' // true
4 !== 3 // true
```
#### Objects
```javascript
var anotherObject = {
  make: "Ford",
  5: "five",
  "artist": "Daft Punk",
  "release_year": 1997,
  "formats": [
    "CD",
    "Cassette",
    "LP"
  ]
}
```
# ES6

## Features
- Arrow functions
- Classes
- Modules
- Promises
- Generators
- let and const

## Basics :
- One of the biggest problems with declaring variables with the var keyword is that you can overwrite variable declarations without an error. Let doesn't allowed for overwrite and protect from unexpected state changing [example](#overwrite)
-  __"use strict"__ This enables Strict Mode, which catches common coding mistakes and "unsafe" actions. [exmaple](#strict)
- When you declare a variable with the var keyword, it is declared globally, or locally if declared inside a function.  
- When you declare a variable with the __let__ keyword inside a block, statement, or expression, its scope is limited to that block, statement, or expression, [example](#codeBlock).
This behavior will cause problems if you were to create a function and store it for later use inside a for loop that uses the i variable. This is because the stored function will always refer to the value of the updated global i variable
- __const__ has all the awesome features that let has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned. [example](#const)
- However, it is important to understand that objects (including arrays and functions) assigned to a variable using const are still __mutable__. Using the const declaration only prevents reassignment of the variable identifier.
- __Object.freeze__ to prevent data mutation. Once the object is frozen, you can no longer add, update, or delete properties from it. Any attempt at changing the object will be rejected without an error. [example](#frozen)
- __arrow function syntax:__ In JavaScript, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions. [example](#inline) You can pass more than one argument into arrow functions as well.
- Arrow functions work really well with higher order functions, such as map(), filter(), and reduce(), that take other functions as arguments for processing collections of data. [example](#higherOrder)
- ES6 introduces __default parameters__ for functions [example](#defaultParameter)
- ES6 introduces the __rest operator__ for function parameters. With the rest operator, you can create functions that take a variable number of arguments. These arguments are stored in an array that can be accessed later from inside the function.[example](#restOperator)
- ES6 introduces the __spread operator__, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected [example](#spreadOperator) However, the spread operator only works in-place, like in an argument to a function or in an array literal.
## Code snippets
###### overwrite
```javascript
let camper = 'James';
let camper = 'David'; // throws an error
```
###### strict
```javascript
"use strict";
x = 3.14; // throws an error because x is not declared
```

###### codeBlock
```javascript
var numArray = [];
for (var i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray); // returns [0, 1, 2]
console.log(i); // returns 3
//==========================================================
var numArray = [];
var i;
for (i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);// returns [0, 1, 2]
console.log(i);// returns 3
//==========================================================
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if(i === 2){
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());// returns 3
//==========================================================
'use strict';
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());// returns 2
console.log(i);// returns "i is not defined"
```
###### const
```javascript
"use strict"
const FAV_PET = "Cats";
FAV_PET = "Dogs"; // returns error
// but mutable
const ARRAY = [1, 2, 3];
ARRAY[1] = 4
console.log(ARRAY) // => [1,4,3]
```

###### frozen
```javascript
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad"; //will be ignored. Mutation not allowed
obj.newProp = "Test"; // will be ignored. Mutation not allowed
console.log(obj);
// { name: "FreeCodeCamp", review:"Awesome"}
```
###### inline
```javascript
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```
###### higherOrder
```javascript
FBPosts.filter((post) => post.thumbnail !== null && post.shares > 100 && post.likes > 500)
```
###### defaultParameter
```javascript
function greeting(name = "Anonymous") {
  return "Hello " + name;
}
console.log(greeting("John")); // Hello John
console.log(greeting()); // Hello Anonymous
```
###### restOperator
```javascript
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2)); // You have passed 3 arguments
console.log(howMany("string", null, [1, 2, 3], { })); // You have passed 4 arguments.
```
###### spreadOperator
```javascript
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr); // returns 89
//...arr returns an unpacked array. In other words, it spreads the array.
```
