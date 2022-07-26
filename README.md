## Javascript-Theory-Qustions


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
<div align="right">
    <b><a href="Javascript-Theory-Qustions">↥ On top</a></b>
</div>

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
## Q.14 What is isNaN?
The isNaN() function determines whether a value is NaN ( Not a Number ) or not. This function returns true if the value equates to NaN. The isNaN() method converts the value to a number before testing it.
```js
isNaN('Hello') // true

isNaN('100') // false

typeof NaN // Number

Number.isNaN('Hello'); // false
```
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
## Q.20 What is the difference forEach and map?
| forEach           |  map                     |
|-------------------|--------------------------|
|Iterates through the elements in an array.| Iterates through the elements in an array.|
|Executes a callback for each element.| "Maps" each element to a new element by calling the function on each element, creating a new array as a result.|
|Does not return a value.| Return new array.
