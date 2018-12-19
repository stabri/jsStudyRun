## Basics variables
- JavaScript provides seven different data types which are undefined, null, boolean, string, symbol, number, and object.
- When JavaScript variables are declared, they have an initial value of undefined, mathematical operation on them => NaN, concatenation => undefined
- Number is a data type in JavaScript which represents numeric data.
- String values in JavaScript may be written with single or double quotes, as long as you start and end with the same type of quote. Unlike some other programming languages, single and double quotes work the same in JavaScript.
- In JavaScript, String values are immutable, which means that they cannot be altered once created.  Note that this does not mean that myStr cannot be changed, just that the individual characters of a string literal cannot be changed.
-

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
- === is the counterpart to the equality operator (==). However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.
-


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
## Code snipets

- Array : var sandwich = ["peanut butter", "jelly", "bread"]
- arr[0][1] - second element from first array in array of arrays
- function testFun(param1, param2) {
  console.log(param1, param2);
}

```sh
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
