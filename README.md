### Table of Contents

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

**[⬆ Back to Top](#table-of-contents)**

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
console.log(employee);  // { "id": 101, "name": "Rajiv Sandal", "age": 35, "country": "INDIA" }
```
**Rest Operator**

The rest operator (...) instructs the computer to add the rest of the user-supplied values into an array.
```js
const [firstName, lastName, ...otherInfo] = ["Oluwatobi", "Sofela", "CodeSweetly", "Web Developer", "Male"];
console.log(otherInfo);  // ["CodeSweetly", "Web Developer", "Male"]

const { firstName, lastName, ...otherInfo } = {
  firstName: "Oluwatobi",
  lastName: "Sofela", 
  companyName: "CodeSweetly",
  profession: "Web Developer",
  gender: "Male"
}
console.log(otherInfo);  // {companyName: "CodeSweetly", profession: "Web Developer", gender: "Male"}
```
<div align="right">
    <b><a href="Javascript-Theory-Qustions">↥ On top</a></b>
</div>

**[⬆ Back to Top](#table-of-contents)**

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
**[⬆ Back to Top](#table-of-contents)**

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
**[⬆ Back to Top](#table-of-contents)**

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
**[⬆ Back to Top](#table-of-contents)**

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

**[⬆ Back to Top](#table-of-contents)**

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

**[⬆ Back to Top](#table-of-contents)**

## Q.11 Difference between null and undefine
| Null | Undefined |
|---- | -----------|
| It is an assignment value which indicates that variable points to no object.  | It is not an assignment value where a variable has been declared but has not yet been assigned a value. |
| Type of null is object | Type of undefined is undefined  |
| The null value is a primitive value that represents the null, empty, or non-existent reference. | The undefined value is a primitive value used when a variable has not been assigned a value.|
| Indicates the absence of a value for a variable | Indicates absence of variable itself |
| Converted to zero (0) while performing primitive operations | Converted to NaN while performing primitive operations |

## Q.12 What is the difference between `==` and `===`?
The `==` is the abstract equality operator while `===` is the strict equality operator. The `==` operator will compare for equality after doing any necessary type conversions.The `===` operator will not do type conversion, so if two values are not the same type `===` will simply return false. When using `==`, funky things can happen.
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

**[⬆ Back to Top](#table-of-contents)**

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
## Q.14 What is isNaN?
The isNaN() function determines whether a value is NaN ( Not a Number ) or not. This function returns true if the value equates to NaN. The isNaN() method converts the value to a number before testing it.
```js
isNaN('Hello') // true

isNaN('100') // false

typeof NaN // Number

Number.isNaN('Hello'); // false
```

**[⬆ Back to Top](#table-of-contents)**

## Q.15 What is the difference between slice and splice?
The `slice()` method returns a new array with a copied slice from the original array. The first optional argument is the beginning index and the second optional argument is the ending index (non-inclusive).
```js
let languages = [ "JavaScript", "Python", "Java", "PHP" ];
languages.slice(1,3); // ["Python", "Java"]
languages.slice(2); // (from index 2 until the end of the array).
// ["Java", "PHP"]
console.log(languages); // the original array is not mutated.
// [ "JavaScript", "Python", "Java", "PHP" ]
```
The `splice()` method changes the content of the array in place and can be used to add or remove items from the array.
When only one argument is provided, all the items after the provided starting index are removed from the array.
```js
let numbers = [10, 20, 30];
numbers.splice(2, 1, 40, 50); // returns removed array:[30]
console.log(numbers); // Original array is mutated.
// returns: [10, 20, 40, 50]
```
**Difference:**
| Slice | Splice |
|---- | ---------|
| Doesn't modify the original array(immutable)  | Modifies the original array(mutable) |
| Returns the subset of original array | Returns the deleted elements as array  |
| Used to pick the elements from array | Used to insert or delete elements to/from array|

**[⬆ Back to Top](#table-of-contents)**

## Q.16 Explain arrays in JavaScript?
JavaScript array is an object that represents a collection of similar type of elements. It can holds values (of any type) not particularly in named properties/keys, but rather in numerically indexed positions.
```js
const array_name = [item-1, item-2, item-3, ...];    
```
```js
// array of numbers
const numbers = [10, 20, 30, 40, 50];

// using new keyword
const numbers = new Array(10, 20, 30, 40, 50);

// array of strings
let fruits = ["Apple", "Orange", "Plum", "Mango"];

// Accessing array elements
fruits[0]; // Apple
fruits[fruits.length - 1] // Mango

// Iterate array elements
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

**[⬆ Back to Top](#table-of-contents)**

## Q.17  Explain array methods join(), pop(), push(), shift(), unshift(), concat(), map(), filter(), reduce(), reduceRight(), every(), some(), indexOf(), lastIndexOf(), find(), findIndex(), includes(), forEach().
**1. array.join()**:
The `join()` method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.
```js
let elements = ['Anupam', 'Kumar', 'Rai'];
console.log(elements.join()); // Output: Anupam,Kumar,Rai
console.log(elements.join('')); // Output: AnupamKumarRai
console.log(elements.join('-')); // Output: Anupam-Kumar-Rai
```
**2. array.pop()**:
The pop() method removes the last element from an array and returns that element. This method changes the length of the array.
```js
let vegitables = ['broccoli', 'cauliflower', 'kale'];
console.log(vegitables.pop()); // Output: "kale"
console.log(vegitables); // Output: Array ["broccoli", "cauliflower"]
console.log(vegitables.pop()); // Output: "cauliflower"
console.log(vegitables.pop()); // Output: "broccoli"
console.log(vegitables.pop()); // Output: "undefined"
```
**3. array.push()**:
The push() method adds one or more elements to the end of an array and returns the new length of the array.
```js
let animals = ['pigs', 'goats', 'sheep'];
let count = animals.push('cows');
console.log(count); // Output: 4
console.log(animals); // Output: Array ["pigs", "goats", "sheep", "cows"]
```
**4. array.shift()**:
The shift() method removes the first element from an array and returns that removed element. This method 
changes the length of the array.
```js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift();
console.log(fruits) // Output: Array ["Orange", "Apple", "Mango"]
```
**5. array.unshift()**:
The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
```js
let fruits = ["Banana", "Orange", "Apple"];
fruits.unshift("Mango","Pineapple");
console.log(fruits); // Output: Array ["Mango", "Pineapple", "Banana", "Orange", "Apple"]
```
**6. array.concat()**:
The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.
```js
let array1 = ['a', 'b', 'c'];
let array2 = ['d', 'e', 'f'];

console.log(array1.concat(array2)); // Output: Array ["a", "b", "c", "d", "e", "f"]
```
**7. array.map()**:
The map() method creates a new array with the results of calling a provided function on every element in the calling array.
```js
let array1 = [1, 4, 9, 16];
// pass a function to map
let map1 = array1.map(x => x * 2); 
console.log(map1); // Output: Array [2, 8, 18, 32]
```
**8. array.filter()**:
The filter() method creates a new array with all elements that pass the test implemented by the provided function.
```js
let words = ['spray', 'limit', 'elite', 'exuberant', 'destruction'];
let result = words.filter(word => word.length > 6);
console.log(result); // Output: Array ["exuberant", "destruction"]
```
**9. array.reduce()**:
The reduce() method executes a reducer function (that you provide) on each element of the array, 
resulting in a single output value.
```js
let array1 = [1, 2, 3, 4];
let reducer = (accumulator, currentValue) => accumulator + currentValue;
console.log(array1.reduce(reducer)); // Output: 10
console.log(array1.reduce(reducer, 5)); // Output: 15
```
**10. array.reduceRight()**:
The reduceRight() method applies a function against an accumulator and each value of the array (from right-to-left) to reduce it to a single value.
```js
let array1 = [[0, 1], [2, 3], [4, 5]].reduceRight(
  (accumulator, currentValue) => accumulator.concat(currentValue)
);
console.log(array1); // Output: Array [4, 5, 2, 3, 0, 1]
```
**11. array.every()**:
The every() method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value. 
```js
function isBelowThreshold(currentValue) {
  return currentValue < 40;
}
let array1 = [1, 30, 39, 29, 10, 13];
console.log(array1.every(isBelowThreshold)); // Output: true
```
**[⬆ Back to Top](#table-of-contents)**

**12. array.some()**:
The some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.
```js
let array = [1, 2, 3, 4, 5];
let even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};
console.log(array.some(even)); // Output: true
```
**13. array.indexOf()**:
The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.
```js
let beasts = ['ant', 'bison', 'camel'];
console.log(beasts.indexOf('camel')); // Output: 2
console.log(beasts.indexOf('giraffe')); // Output: -1
```
**14. array.lastIndexOf()**:
The lastIndexOf() method returns the index within the calling String object of the last occurrence 
of the specified value, searching backwards from fromIndex. Returns -1 if the value is not found.
```js
let paragraph = 'The quick brown fox jumps over the lazy dog. If the dog barked, was it really lazy?';
let searchTerm = 'dog';
console.log('The index of the first "' + searchTerm + '" from the end is ' + paragraph.lastIndexOf(searchTerm));
// Output: "The index of the first "dog" from the end is 52"
```
**15. array.find()**:
The find() method returns the value of the first element in the provided array that satisfies the provided testing function.
```js
let array1 = [5, 12, 8, 130, 44];
let found = array1.find(function(element) {
  return element > 100;
});
console.log(found); // Output: 130
```
**16. array.findIndex()**:
The findIndex() method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.
```js
let array1 = [5, 12, 8, 130, 44];
function isLargeNumber(element) {
  return element > 20;
}
console.log(array1.findIndex(isLargeNumber)); // Output: 3
```
**17. array.includes()**:
The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.
```js
let array1 = [1, 2, 3];
console.log(array1.includes(2)); // Output: true
let pets = ['cat', 'dog', 'bat'];
console.log(pets.includes('at')); // Output: false
```
**18. array.forEach()**:
The forEach() method executes a provided function once for each array element.
```js
const array1 = ['a', 'b', 'c'];
array1.forEach(element => console.log(element));
// expected output: "a"
// expected output: "b"
// expected output: "c"
```
**18. array.sort()**:
The purpose of the compare function is to define an alternative sort order. When the sort() function compares two values, it sends the values to the compare function, and sorts the values according to the returned (negative, zero, positive) value.
```js
const numbers = [1, 2, 5, 3, 4];
numbers.sort((a, b) => a - b);
console.log(numbers); // [1,2,3,4,5]
```

**[⬆ Back to Top](#table-of-contents)**

## Q.18 Difference between Spread Syntex and Rest Syntax?
The main difference between `rest` and `spread` is that the rest operator puts the rest of some specific user-supplied values into a JavaScript array. But the spread syntax expands iterables into individual elements.

|Spread Syntax           |  Rest Syntax                    |
|------------------------|---------------------------------|
|Spread operator as its name suggests it spreads or expands the content of the given element.| Rest Syntax is just the opposite of spread syntax it collects the data and stores that data in a variable which we can use further in our code.|
|It expands an Array in form of elements, while in key-value pairs in the case of Objects. | It collects the data in the developer's desired format.|
|You may or may not use the strict mode inside the function containing the spread operator. | You can not use the strict mode inside function containing the rest operator.|
|It will overwrite the identical properties inside two objects and replace the former with the latter. | It simply collects all properties and wraps them inside a container.|

## Q.19 What is the difference between for..in and for..of?
for in: iterates over all enumerable properties of an object that are keyed by strings.
for of: iterates over the values of an iterable objects.
```js
// for..in
let list = [10, 20, 30];
for (let i in list) {
  console.log(i); // "0", "1", "2",
}
// for..of
for (let i of list) {
  console.log(i); // "10", "20", "30"
}
```

**[⬆ Back to Top](#table-of-contents)**

## Q.20 What is the difference forEach and map?
| forEach           |  map                     |
|-------------------|--------------------------|
|Iterates through the elements in an array.| Iterates through the elements in an array.|
|Executes a callback for each element.| "Maps" each element to a new element by calling the function on each element, creating a new array as a result.|
|Does not return a value.| Return new array.

## Q.21 What is a RegExp object?
A regular expression is an object that describes a pattern of characters.

## Q.22 What are the benefits of using arrow function function?
Arrow syntax automatically binds this to the surrounding code's context.And `=>` is shorter and simpler than function, although stylistic issues are often subjective.
```js
let greet = () => console.log('Hello'); //No Argument
greet(); // Hello

let greet = x => console.log(x); //One Argument
greet('Hello'); // Hello 

let age = 25;

let welcome = (age < 18) ?() => console.log('Baby') : () => console.log('Adult'); //An Expression
welcome(); // Adult

let area = (r) => {
  const pi = 3.14;
  return pi * r * r;
}
let result = area(10); // Multiline
console.log(result); // 314
```

**[⬆ Back to Top](#table-of-contents)**

## Q.23 What is a first class function?
In javaScript, functions can be stored as a variable inside an object or an array as well as it can be passed as an argument or be returned by another function. That makes function first-class function in JavaScript.
```js
const message = function() {
   console.log("Hello World!");
}
message(); //function to a variable

function sayHello() {
   return "Hello, ";
}
function greeting(helloMessage, name) {
  console.log(helloMessage() + name);
}
greeting(sayHello, "JavaScript!");//function as an Argument

function sayHello() {
   return function() {
      console.log("Hello!");
   }
} //Return a function

const sayHello = function() {
   return function() {
      console.log("Hello!");
   }
}
const myFunc = sayHello();
myFunc(); //Using a variable

function sayHello() {
   return function() {
      console.log("Hello!");
   }
}
sayHello()(); //Using double parentheses
```
We are using double parentheses ()() to invoke the returned function as well.

**[⬆ Back to Top](#table-of-contents)**

## Q.24 What is a higher order function?
A Higher-Order function is a function that receives a function as an argument or returns the function as output.
For e.g, Array.prototype.map(), Array.prototype.filter() , Array.prototype.forEach() and Array.prototype.reduce() are some of the Higher-Order functions in javascript.

## Q.25 What is a unary function?
Unary function (i.e. monadic) is a function that accepts exactly one argument. It stands for single argument accepted by a function.
```js
const unaryFunction = (number) => number + 10;
console.log(unaryFunction(10)); // 20
```
## Q.26 What is currying function?
Currying is the process of taking a function with multiple arguments and turning it into a sequence of functions each with only a single argument.

In other words, when a function, instead of taking all arguments at one time, takes the first one and return a new function that takes the second one and returns a new function which takes the third one, and so forth, until all arguments have been fulfilled.
```js
// Normal function
const add = (a, b, c) => {
  return a + b + c;
};
console.log(add(10, 10, 10)); // 30

// Currying function
const addCurry = (a) => {
  return (b) => {
    return (c) => {
      return a + b + c;
    };
  };
};
console.log(addCurry(20)(20)(20)); // 60
```
**[⬆ Back to Top](#table-of-contents)**

## Q.27 What is Constructor function in js?
A constructor is a special function that creates and initializes an object instance of a class. In JavaScript, a constructor gets called when an object is created using the `new` keyword.

The purpose of a constructor is to create a new object and set values for any existing object properties.
```js
function User() {
    this.name = 'Bob';
}
var user = new User();
var user = new User(); //Create Multiple Objects

function Employee(name, age) {
  this.name = name;
  this.age = age;
} //Constructor with Parameters
var emp1 = new Employee('Anupam Rai', 28);
console.log(emp1.name);// "Anupam Rai"
console.log(emp1.age );// 28
```
## Q.28 What is a pure function?
Pure functions are functions that accept an input and returns a value without modifying any data outside its scope(Side Effects). Its output or return value must depend on the input/arguments and pure functions must return a value.

It is a pure function because you always get a Hello `<name>` as output for the `<name>` pass as an input.
```js
// Pure Function
function sayGreeting(name) {
  return `Hello ${name}`;
}
console.log(sayGreeting("World"));
```

The function\'s output now depends on an outer state called greeting. What if someone changes the value of the greeting variable to `Hola`? It will change the output of the `sayGreeting()` function even when you pass the same input.

```js
let greeting = "Hello";
function sayGreeting(name) {
  return `${greeting} ${name}`;
}
```
A function must pass two tests to be considered **pure**:
* Same inputs always return same outputs
* No side-effects

**[⬆ Back to Top](#table-of-contents)**

##  Q.29  What is an arguments object?
The arguments object is an Array-like object ( arguments ) accessible inside functions that contains the values of the arguments passed to that function.
```js
function sum() {
  let total = 0;
  for (let i = 0, len = arguments.length; i < len; ++i) {
    total += arguments[i];
  }
  return total;
} // arguments object
sum(10, 20, 30); // returns 60
```
## Q.30 What is the way to find the number of parameters expected by a function?
The length property indicates the number of parameters expected by the function.
```js
// function.length
function fun1() {}
console.log(fun1.length); // 0

function fun2(arg1, arg2) {}
console.log(fun2.length); // 2
```

**[⬆ Back to Top](#table-of-contents)**

## Q.31 What is the difference between Call, Apply and Bind?
- Call invokes the function and allows you to pass in arguments one by one.
- Apply invokes the function and allows you to pass in arguments as an array.
- Bind returns a new function, allowing you to pass in a this array and any number of arguments.
```js
const employee1 = { firstName: "Sahima", lastName: "Mutti" };
const employee2 = { firstName: "Aarush", lastName: "Krishna" };

function say(greeting) {
  console.log(greeting + " " + this.firstName + " " + this.lastName);
} //call

say.call(employee1, "Hi");    // Hi Sahima Mutti 
say.call(employee2, "Hello"); // Hello Aarush Krishna 
```
```js
const employee1 = { firstName: "Sahima", lastName: "Mutti" };
const employee2 = { firstName: "Aarush", lastName: "Krishna" };

function say(greeting) {
  console.log(greeting + " " + this.firstName + " " + this.lastName);
} //apply

say.apply(employee1, ["Hi"]);    // Hi Sahima Mutti 
say.apply(employee2, ["Hello"]); // Hello Aarush Krishna 
```
```js
const employee1 = { firstName: "Sahima", lastName: "Mutti" };
const employee2 = { firstName: "Aarush", lastName: "Krishna" };

function say(greeting) {
  console.log(greeting + " " + this.firstName + " " + this.lastName);
} //Bind
var sayEmployee1 = say.bind(employee1);
var sayEmployee2 = say.bind(employee2);

sayEmployee1("Hi");    // Hi Sahima Mutti 
sayEmployee2("Hello"); // Hello Aarush Krishna 
```

**[⬆ Back to Top](#table-of-contents)**

## Q.32 What is an anonymous function?
An anonymous function is a function without a name. Anonymous functions are commonly assigned to a variable name or used as a callback function.
```js
// Anonymous function
let show = function () {
  console.log("Anonymous function");
};
show();

//Anonymous functions as arguments
setTimeout(function () {
  console.log("Execute later after 1 second");
}, 1000);

//Immediately invoked function execution
const person = {
  firstName: "Ayaan",
  lastName: "Memon"
};
(function () {
  console.log(person.firstName + " " + person.lastName); // Ayaan Memon
})(person);

//Arrow functions

let add = (a, b) => a + b;
add(10, 20); // 30
```
## Q.33 Explain how this works in JavaScript?
The this keyword refers to an object. Which object depends on how this is being invoked (used or called). The this keyword refers to different objects depending on how it is used.
- In an object method, this refers to the object.
- Alone, this refers to the global object.
- In a function, this refers to the global object.
- In a function, in strict mode, this is undefined.
- In an event, this refers to the element that received the event.
- Methods like call(), apply(), and bind() can refer this to any object.

**[⬆ Back to Top](#table-of-contents)**

## Q.34 What are closures?
A closure is the combination of a function bundled together with references to its surrounding state.A closure gives you access to an outer function's scope from an inner function.
```js
// lexical
 function me() {
     var name = "Anupam"; // name is a local variable created by init
     function displayName() { // displayName() is the inner function, a closure
         console.log(name); // displayName() uses variable declared in the parent function    
     }
     displayName();    
}
me();

//Dynamic
function fun1() {
  console.log(a); // 10
}
function fun2() {
  var a = 20;
  fun1();
}
var a = 10;
fun2();
// Output
10
```
- Variables created without a declaration keyword (var, let, or const) are always global, even if they are created inside a function. Global and local variables with the same name are different variables. Modifying one, does not modify the other.

**[⬆ Back to Top](#table-of-contents)**

## Q.35 What is callback() function in javascript?
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.
```js
// callback() function
function greeting(name) {
  alert('Hello ' + name);
}
function processUserInput(callback) {
  var name = prompt('Please enter your name:');
  callback(name);
}
console.log(processUserInput(greeting));
```
The above example is a synchronous callback, as it is executed immediately.
## Q.36 What is event handling in javascript?
The change in the state of an object is known as an `Event`. In html, there are various events which represents that some activity is performed by the user or by the browser.

When javascript code is included in HTML, js react over these events and allow the execution. This process of reacting over the events is called `Event Handling`. Thus, js handles the HTML events via `Event Handlers`.
|Event Handler | Description|
|onclick |	When mouse click on an element|
|onchange |	When the user modifies or changes the value of a form element|
|onload |	When the browser finishes the loading of the page|

## Q.37 What is an event delegation?
Event Delegation is basically a pattern to handle events efficiently. Instead of adding an event listener to each and every similar element, we can add an event listener to a parent element and call an event on a particular target using the event.target property of the event object.
```js
document.getElementById('buttons')
    .addEventListener('click', event => { 
      if (event.target.className === 'buttonClass') { 
        console.log('Click!');
      }
    });
```

**[⬆ Back to Top](#table-of-contents)**

## Q.38 What is the use of setTimeout?
The `setTimeout()` method is used to call a function or evaluates an expression after a specified number of milliseconds.
```js
setTimeout(() => {
  console.log("Delayed for 1 second.");
}, "1000")
```

## Q.39 What is the use of setInterval?
The `setInterval()` method is used to call a function or evaluates an expression at specified intervals (in milliseconds). The `setInterval()` method continues calling the function until `clearInterval()` is called, or the window is closed.
```js
setInterval(myTimer, 1000);
function(){}
```
## Q.40  What is the purpose of clearTimeout method?
The clearTimeout() function is used in javascript to clear the timeout which has been set by setTimeout() function before that. i.e, The return value of setTimeout() function is stored in a variable and it's passed into the clearTimeout() function to clear the timer.
```js
var msg;
function greeting() {
  console.log("Hello World!");
  stop();
  console.log('Bye World!');
}
function start() {
  console.log("start");
  msg = setTimeout(greeting, 3000);
}
function stop() {
  console.log("stop");
  clearTimeout(msg);
}

start();
//Output
start
Hello World!
stop
Bye World!
```

**[⬆ Back to Top](#table-of-contents)**

## Q.41 Explain the difference between mutable and immutable objects?
A mutable object is an object whose state can be modified after it is created. An immutable object is an object whose state cannot be modified after it is created.

In JavaScript numbers, strings, null, undefined and Booleans are primitive types which are immutable. Objects, arrays, functions, classes, maps, and sets are mutable.

## Q.42 How can you achieve immutability in your own code?
For "mutating" objects, use the spread operator,or Object.assign, Array.concat(), etc., to create new objects instead of mutate the original object.
```js
// Array Example
const arr = [10, 20, 30];
const newArr = [...arr, 40, 50]; // [10, 20, 30, 40, 50]

// Object Example
const human = Object.freeze({ race: "human" });
const aditya = { ...human, name: "Aditya" }; // {race: "human", name: "Aditya"}
const alienAditya = { ...aditya, race: "alien" }; // {race: "alien", name: "Aditya"}
```
## Q.43 What is Seal and Freeze methods in object?
**Seal**
It prevents additions or deletion of `properties. seal()` also prevents the modification of property descriptors.
```js
const myCar = {
  maxSpeed: 250,
  batteryLife: 300,
  weight: 123
};
Object.isSealed(myCar); // false
Object.seal(myCar);   //{ maxSpeed: 250, batteryLife: 300, weight: 123 }
Object.isSealed(myCar); // true
myCar.color = 'blue';
console.log(myCar.color); // undefined
delete myCar.batteryLife; // false
console.log(myCar.batteryLife); // 300
```
**Freeze**
It does the same that `Object.seal()` plus it makes the properties non-writable.
```js
const myCar = {
  maxSpeed: 250,
  batteryLife: 300,
  weight: 123
};

Object.isFrozen(myCar); // false
Object.freeze(myCar);
Object.isFrozen(myCar); // true

myCar.color = 'blue';
console.log(myCar.color); // undefined

delete myCar.batteryLife;
console.log(myCar.batteryLife); // 300
```

**[⬆ Back to Top](#table-of-contents)**

## Q.44 What is shallow copy and deep copy in javascript?
**Shallow Copy**

Shallow copy is a bit-wise copy of an object. A new object is created that has an exact copy of the values in the original object. If any of the fields of the object are references to other objects, just the reference addresses are copied i.e., only the memory address is copied.
A Shallow copy of the object can be done using object.assign()
```js
let obj = {
  a: 10,
  b: 20,
};

let objCopy = Object.assign({}, obj);
console.log(objCopy); // Result - { a: 1, b: 2 }
```
**Deep Copy**
A deep copy copies all fields, and makes copies of dynamically allocated memory pointed to by the fields. A deep copy occurs when an object is copied along with the objects to which it refers.

A Deep copy of the object can be done using JSON.parse(JSON.stringify(object))
```js
let obj2 = {
  a: 10,
  b: {
    c: 20
  }
};
let newObj = JSON.parse(JSON.stringify(obj2));
obj2.b.c = 30;
console.log(obj2); // { a: 10, b: { c: 20 } }
console.log(newObj); // { a: 10, b: { c: 20 } }
```

**[⬆ Back to Top](#table-of-contents)**

## Q.45 What is Class in js?
Classes are in fact `"special functions"`, and just as you can define function expressions and function declarations, the class syntax has two components: `class expressions` and `class declarations`.
```js
// Unnamed Class
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
console.log(Rectangle.name); // Rectangle

// Named Class
let Triangle = class TriangleClass {
  constructor(base, height) {
    this.base = base;
    this.height = height;
  }
};
console.log(Triangle.name); // TriangleClass
```
## Q.46 What is difference between private, public and static variables?
Private variables can be accessed by all the members (functions and variables) of the owner object but not by any other object. Public variables can be accessed by all the members of the owner as well as other objects that can access the owner. Static variables are related to a class. They come into existence as soon as a class come into existence.
```js
// Constructor Function
function MyClass () {
 
  var privateVariable = "I am private!";  // Private variable 
  this.publicVariable = "I am public!";  // Public variable 

  this.publicMethod = function () {  // Public Method
    return privateVariable;
  };
}
```
**[⬆ Back to Top](#table-of-contents)**

## Q.47 How does await and async works in es6?
The async and await keywords enable asynchronous, promise-based behavior to be written in a cleaner style, avoiding the need to explicitly configure promise chains.

Async keyword is used along with the function declaration which specifies that this function is now able to accept all types of asynchronous events on itself. Await basically waits for the results which are particularly to be fetched from the source from which that async function is about to fetch the data.
```js
// async() and await()
async function fetchMethod() {
  try {
    let response = await fetch("https://api.github.com/users/1");
    let data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchMethod();
```
## Q.48 Explain fetch() properties in JavaScript?
A fetch() function is available in the global window object. The fetch() function takes one mandatory argument, the path to the resource you want to fetch. It returns a Promise, whether it is successful or not. If request is successful .then() function will receive Response object, if request fails then .catch() function will receive an error object
```js
fetch("https://api.github.com/users/learning-zone")
  .then(function (response) {
    return response.json();
  })
  .then(function (data) {
    console.log(data);
  })
  .catch(function (err) {
    console.log("Something went wrong!", err);
  });
```

**[⬆ Back to Top](#table-of-contents)**

## Q.49 What is rendering in JavaScript?
JavaScript-powered content needs to be rendered before it can output meaningful code and be displayed for the client. 

## Q.50 What is throttling and debouncing in javascript?
`Throttling` enforces a maximum number of times a function can be called over time. As in "execute this function at most once every 100 milliseconds."

`Debouncing` enforces that a function not be called again until a certain amount of time has passed without it being called. As in "execute this function only if 100 milliseconds have passed without it being called."

**[⬆ Back to Top](#table-of-contents)**
