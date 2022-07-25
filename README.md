# Javascript-Theory-Qustions

## Q 1. List out important features of JavaScript ES6?
- a. Template Strings
- b. Spread Operator
- c. Sets
- d. Default Parameter
- e. repeat()
- f. Arrow Function (=>):
- g. Arrow function with this
- h. Destructing Assignment
- i. Iterator
- j. Genrators
- k. Symbols

## Q 2. What is Spread Operator
Spread operator allows iterables( arrays / objects / strings ) to be expanded into single arguments/elements.
```js
function sum(x, y, z) {
  return x + y + z;
}
let numbers = [30, 10, 30];
// Using Spread Operator
console.log(sum(...numbers)); // 70
```
It use as: 
- a. copy an array
```js
let fruits = ["Apple", "Orange", "Banana"];
let newFruitArray = [...fruits];
console.log(newFruitArray); 
//Output 
['Apple','Orange','Banana']
```
- b. Concat an arry
```js
let arr1 = ["A", "B", "C"];
let arr2 = ["X", "Y", "Z"];
let result = [...arr1, ...arr2];
console.log(result); 
// Output
['A', 'B', 'C', 'X', 'Y', 'Z']
```
- c. Spreading elements together with an individual element
```js
let fruits = ["Apple", "Orange", "Banana"];
let newFruits = ["Cherry", ...fruits];
console.log(newFruits); 
// Output
['Cherry', 'Apple','Orange','Banana']
```
- d. Spreading elements on function calls
```js
let fruits = ["Apple", "Orange", "Banana"];
const getFruits = (f1, f2, f3) => {
  console.log(`Fruits: ${f1}, ${f2} and ${f3}`);
};
getFruits(...fruits); 
// Output
Fruits: Apple, Orange and Banana
```
- e. Spread syntax for object literals
```js
var obj1 = { id: 101, name: 'Rajiv Sandal' }
var obj2 = { age: 35, country: 'INDIA'}
const employee = { ...obj1, ...obj2 }
console.log(employee); // { "id": 101, "name": "Rajiv Sandal", "age": 35, "country": "INDIA" }
```

## Q.3 What is Sets?
Sets are a new object type with ES6 (ES2015) that allow to create collections of unique values. The values in a set can be either simple primitives like strings or integers, but more complex object types like object literals or arrays can also be part of a set.
```js
let numbers = new Set([10, 20, 20, 30, 40, 50]);
console.log(numbers); // Set(5) {10, 20, 30, 40, 50}
console.log(typeof numbers); // Object
```
## Q.4 What are global variables?
Global variables are declared outside of a function or declared with a window object for accessibility throughout the program (unless shadowed by locals). If you declare a variable without using var, even if it's inside a function, it will still be seen as global.

The var statement declares a function-scoped or globally-scoped variable, optionally initializing it to a value.
```js
var x = 10;

if (x === 10) {
  var x = 20;

  console.log(x);
  // expected output: 20
}

console.log(x);
// expected output: 20
```

## Q.5  What are the arro function?
An arrow function is a shorter syntax for a function expression and does not have its own this, arguments, super, or new.target. 
```js
let add = (x,y,z) => {
    return x+y+z
}
let add = (x,y,z) => x + y + z;
console.log(add(1,2,3));
```
## Q.6 What are template literals in es6?
Template literals help make it simple to do string interpolation, or to include variables in a string.
```js
const person = { name: 'Tyler', age: 28 };
console.log(`Hi, my name is ${person.name} and I am ${person.age} years old!`);
// 'Hi, my name is Tyler and I am 28 years old!'

console.log(`This is line one.
This is line two.`);
// This is line one.
// This is line two.

  <div>
    <p>Name: ${person.name}</p>
    <p>Name: ${person.age}</p>
  </div>
```

## Q.7 What are the differences between variables created using let, var or const?
Variables declared using the var keyword are scoped to the function in which they are created, or if created outside of any function, to the global object. let and const are block scoped, meaning they are only accessible within the nearest set of curly braces (function, if-else block, or for-loop).
```js
/**
 * var declared variables are accessible anywhere in the function scope.
 * 
 **/
if (true) {
  var a = 10;
  let b = 20;
  const c = 30;
}

console.log(a); // 10
console.log(b); // ReferenceError: baz is not defined
console.log(c); // ReferenceError: qux is not defined
```
```js
/**
 * All variables are accessible within functions.
 * 
**/
function variableScope() {

  var x = 10;
  let y = 20;
  const z = 30;

  console.log(x); // 10
  console.log(y); // 20
  console.log(z); // 30
}

console.log(x); // ReferenceError: x is not defined
console.log(y); // ReferenceError: y is not defined
console.log(z); // ReferenceError: z is not defined

variableScope();
```
## Q.8 What is Hoisting in JavaScript?
JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code.
**Example 01:** Function Hoisting
```js
getName('Anupam Kumar')
function getName(name){
    console.log('Hello ' + name); //Hello Anupam Kumar
} 
```
**Example 02:** Variable Hoisting
```js
console.log(getName); //Undefine
var getName='Anupam Kumar';

var getName
console.log(getName); //Undefine
getName='Anupam Kumar'

```
**Example 03:** `let` and `const` hoisting
All declarations (function, var, let, const and class) are hoisted in JavaScript, while the var declarations are initialized with undefined, but let and const declarations remain uninitialized.
```js
console.log(x);  // Output: ReferenceError: x is not defined
let x = 52;
```
## Q.9 What is the precedence order between local and global variables?
A local variable takes precedence over a global variable with the same name.
```js
var msg = "Good morning";
function greeting() {
  msg = "Good Evening";
  console.log(msg);
}
greeting();
// Output
Good Evening
```
## Q.10 What is Undefine and null?
Undefined means a variable has been declared, but the value of that variable has not yet been defined
```js
let name;
console.log(name); // undefined
console.log(typeof(name))  // undefined

```
In JavaScript, null is a special value that represents empty or unknown value.
```js
const number = null;
console.log(number); // null
console.log(typeof number); // object
```
## Q.11 Difference between null and undefine
| Null | Undefined |
|---- | -----------|
| It is an assignment value which indicates that variable points to no object.  | It is not an assignment value where a variable has been declared but has not yet been assigned a value. |
| Type of null is object | Type of undefined is undefined  |
| The null value is a primitive value that represents the null, empty, or non-existent reference. | The undefined value is a primitive value used when a variable has not been assigned a value.|
| Indicates the absence of a value for a variable | Indicates absence of variable itself |
| Converted to zero (0) while performing primitive operations | Converted to NaN while performing primitive operations |

## Q.12 What is the difference between `==` and `===`?
The `==` is the abstract equality operator while `===` is the strict equality operator. The `==` operator will compare for equality after doing any necessary type conversions.

The `===` operator will not do type conversion, so if two values are not the same type `===` will simply return false. When using `==`, funky things can happen.
```js
1 == '1'; // true
1 == [1]; // true
1 == true; // true
0 == ''; // true
0 == '0'; // true
0 == false; // true

let x = null;
console.log(x == null); // true
console.log(x == undefined); // true
```
## Q.13  What is the difference between typeof and instanceof operator?
The typeof operator checks if a value has type of primitive type which can be one of boolean, function, object, number, string, undefined and symbol (ES6).
```js
const x = "Hello World";
const y = new String("Hello World");

typeof x; // returns 'string'
typeof y; // returns 'object'
```
The instanceof is a binary operator, accepting an object and a constructor. It returns a boolean indicating whether or not the object has the given constructor in its prototype chain.
```js
const a = "Hello World";
const b = new String("Hello World");
a instanceof String; // returns false
b instanceof String; // returns true
```
