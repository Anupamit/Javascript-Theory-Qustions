# Functions in JavaScript

## 1. Functions?

* Functions are one of the fundamental building blocks in JavaScript. A function is a JavaScript procedure—a set of statements that performs a task or calculates a value. To use a function, you must define it somewhere in the scope from which you wish to call it.

## 2. Function Declaration?

* A function definition (also called a function declaration or function statement) consists of the `function` keyword, followed by:
    1. The name of the function.
    2. A list of parameters to the function, enclosed in parentheses and separated by commas.
    3. The JavaScript statements that define the function, enclosed in curly brackets, `{}`.
For example, the following code defines a simple function named `square`:

```js
    function square(number) {
      return number * number;
    }
```

* The function square takes one parameter, called number. The function consists of one statement that says to return the parameter of the function (that is, number) multiplied by itself. The statement return specifies the value returned by the function:
    
```js
    return number * number;
```
* Primitive parameters (such as a number) are passed to functions by value; the value is passed to the function, but if the function changes the value of the parameter, this change is not reflected globally or in the calling function.

* If you pass an object (i.e. a non-primitive value, such as Array or a user-defined object) as a parameter and the function changes the object's properties, that change is visible outside the function, as shown in the following example:
```js
   function myFunc(theObject) {
      theObject.make = 'Toyota';
    }

    var mycar = {make: 'Honda', model: 'Accord', year: 1998};
    var x, y;

    x = mycar.make; // x gets the value "Honda"

    myFunc(mycar);
    y = mycar.make; // y gets the value "Toyota"
                    // (the make property was changed by the function)`
```
## 3. Function expressions?

* While the function declaration above is syntactically a statement, functions can also be created by a function expression. Such a function can be anonymous; it does not have to have a name. For example, the function square could have been defined as:

```js
      var square = function(number) { return number * number; };
      var x = square(4); // x gets the value 16
```

* However, a name can be provided with a function expression and can be used inside the function to refer to itself, or in a debugger to identify the function in stack traces:
```js
      var factorial = function fac(n) { return n < 2 ? 1 : n * fac(n - 1); };
    
      console.log(factorial(3));
```
* Function expressions are convenient when passing a function as an argument to another function. The following example shows a map function that should receive a function as first argument and an array as second argument. 
```js
    function map(f, a) {
      var result = [],i; // Create a new Array
      for (i = 0; i != a.length; i++)
        result[i] = f(a[i]);
      return result;
    }
```
* In the following code our function receives a function defined by a function expression and executes it for every element of the array received as a second argument. 
```js
    function map(f, a) {
      var result = []; // Create a new Array
      var i; // Declare variable
      for (i = 0; i != a.length; i++)
        result[i] = f(a[i]);
      return result;
    }
    var f = function(x) {
       return x * x * x; 
    }
    var numbers = [0, 1, 2, 5, 10];
    var cube = map(f,numbers);
    console.log(cube);
    Function returns: [0, 1, 8, 125, 1000].

```
* In JavaScript, a function can be defined based on a condition. For example, the following function definition defines myFunc only if num equals 0:
```js
    var myFunc;
    if (num === 0) {
      myFunc = function(theObject) {
        theObject.make = 'Toyota';
      }
    }
```
* In addition to defining functions as described here, you can also use the Functionconstructor to create functions from a string at runtime, much like eval().
* A method is a function that is a property of an object. Read more about objects and methods in Working with objects.

## 4. Calling functions?

* Defining a function does not execute it. Defining the function simply names the function and specifies what to do when the function is called. Calling the function actually performs the specified actions with the indicated parameters. For example,
```js
    if you define the function square, you could call it as follows:
    square(5);
```
* The preceding statement calls the function with an argument of 5. The function executes its statements and returns the value 25.
* Functions must be in scope when they are called, but the function declaration can be hoisted (appear below the call in the code), as in this example:

```js
    console.log(square(5));
    /* ... */
    function square(n) { return n * n; }
```
* The scope of a function is the function in which it is declared, or the entire program if it is declared at the top level.
`Note: This works only when defining the function using the above syntax (i.e. function funcName(){}). The code below will not work. That means, function hoisting only works with function declaration and not with function expression.`

```js
    console.log(square); // square is hoisted with an initial value undefined.
    console.log(square(5)); // Uncaught TypeError: square is not a function
    var square = function(n) { 
      return n * n; 
    }
  ```

* The arguments of a function are not limited to strings and numbers. You can pass whole objects to a function. The show_props() function (defined in Working with objects) is an example of a function that takes an object as an argument.

* A function can call itself. For example, here is a function that computes factorials recursively:
```js
    function factorial(n) {
      if ((n === 0) || (n === 1))
        return 1;
      else
        return (n * factorial(n - 1));
    }
```
* You could then compute the factorials of one through five as follows:
```js
      var a, b, c, d, e;
      a = factorial(1); // a gets the value 1
      b = factorial(2); // b gets the value 2
      c = factorial(3); // c gets the value 6
      d = factorial(4); // d gets the value 24
      e = factorial(5); // e gets the value 120
```

* There are other ways to call functions. There are often cases where a function needs to be called dynamically, or the number of arguments to a function vary, or in which the context of the function call needs to be set to a specific object determined at runtime. It turns out that functions are, themselves, objects, and these objects in turn have methods (see the Function object). One of these, the apply() method, can be used to achieve this goal.

## 5. Function scope?

* Variables defined inside a function cannot be accessed from anywhere outside the function, because the variable is defined only in the scope of the function. However, a function can access all variables and functions defined inside the scope in which it is defined. In other words, a function defined in the global scope can access all variables defined in the global scope. A function defined inside another function can also access all variables defined in its parent function and any other variable to which the parent function has access.
  
```js
    // The following variables are defined in the global scope
    var num1 = 20,
      num2 = 3,
      name = 'Chamahk';
    
    // This function is defined in the global scope
    function multiply() {
    return num1 * num2;
    }
    
    multiply(); // Returns 60
    
    // A nested function example
    function getScore() {
            var num1 = 2,
                num2 = 3;

    function add() {
      return name + ' scored ' + (num1 + num2);
    }
    
    return add();
    }
    
    getScore(); // Returns "Chamahk scored 5"
  ```
          
## 6. Scope and the function stack?

### 6.1. Recursion?

* A function can refer to and call itself. There are three ways for a function to refer to itself:
    1. the function's name
    2. arguments.callee
    3. an in-scope variable that refers to the function
* For example, consider the following function definition:
```js
    var foo = function bar() {
     // statements go here
    };
```

* Within the function body, the following are all equivalent:

    1.bar()
    2.arguments.callee()
    3.foo()
    
* A function that calls itself is called a recursive function. In some ways, recursion is analogous to a loop. Both execute the same code multiple times, and both require a condition (to avoid an infinite loop, or rather, infinite recursion in this case). For example, the following loop:
```js
    var x = 0;
    while (x < 10) { // "x < 10" is the loop condition
     // do stuff
     x++;
    }
    
    * can be converted into a recursive function and a call to that function:
    
    function loop(x) {
    if (x >= 10) // "x >= 10" is the exit condition (equivalent to "!(x < 10)")
      return;
    // do stuff
    loop(x + 1); // the recursive call
    }
    loop(0);
```
However, some algorithms cannot be simple iterative loops. For example, getting all the nodes of a tree structure (e.g. the DOM) is more easily done using recursion:
```js
    function walkTree(node) {
    if (node == null) // 
      return;
    // do something with node
    for (var i = 0; i < node.childNodes.length; i++) {
      walkTree(node.childNodes[i]);
    }
    }
```
* Compared to the function loop, each recursive call itself makes many recursive calls here.
It is possible to convert any recursive algorithm to a non-recursive one, but often the logic is much more complex and doing so requires the use of a stack. In fact, recursion itself uses a stack: the function stack.
* The stack-like behavior can be seen in the following example:
```js
    function foo(i) {
      if (i < 0)
        return;
      console.log('begin: ' + i);
      foo(i - 1);
      console.log('end: ' + i);
    }
    foo(3);
    
    // Output:
    
    // begin: 3
    // begin: 2
    // begin: 1
    // begin: 0
    // end: 0
    // end: 1
    // end: 2
    // end: 3
```

### 6.2. Nested functions and closures?

* You can nest a function within a function. The nested (inner) function is private to its containing (outer) function. It also forms a closure. A closure is an expression (typically a function) that can have free variables together with an environment that binds those variables (that "closes" the expression).
Since a nested function is a closure, this means that a nested function can "inherit" the arguments and variables of its containing function. In other words, the inner function contains the scope of the outer function.
* To summarize:
      1.The inner function can be accessed only from statements in the outer function.
      2.The inner function forms a closure: the inner function can use the arguments and variables of the outer function, while the outer function cannot use the arguments and variables of the inner function.
The following example shows nested functions:
```js
    function addSquares(a, b) {
      function square(x) {
        return x * x;
      }
      return square(a) + square(b);
    }
    a = addSquares(2, 3); // returns 13
    b = addSquares(3, 4); // returns 25
    c = addSquares(4, 5); // returns 41
```
Since the inner function forms a closure, you can call the outer function and specify arguments for both the outer and inner function:
```js
    function outside(x) {
    function inside(y) {
      return x + y;
    }
    return inside;
    }
    fn_inside = outside(3); // Think of it like: give me a function that adds 3 to whatever you give
                          // it
    result = fn_inside(5); // returns 8
    
    result1 = outside(3)(5); // returns 8
```
### 6.3. Preservation of variables?

* Notice how x is preserved when inside is returned. A closure must preserve the arguments and variables in all scopes it references. Since each call provides potentially different arguments, a new closure is created for each call to outside. The memory can be freed only when the returned inside is no longer accessible.

* This is not different from storing references in other objects, but is often less obvious because one does not set the references directly and cannot inspect them.

### 6.4. Multiply-nested functions?

* Functions can be multiply-nested, i.e. a function (A) containing a function (B) containing a function (C). Both functions B and C form closures here, so B can access A and C can access B. In addition, since C can access B which can access A, C can also access A. Thus, the closures can contain multiple scopes; they recursively contain the scope of the functions containing it. This is called scope chaining. (Why it is called "chaining" will be explained later.)
Consider the following example:
```js
    function A(x) {
      function B(y) {
        function C(z) {
          console.log(x + y + z);
        }
        C(3);
      }
      B(2);
    }
    A(1); // logs 6 (1 + 2 + 3)
```
* In this example, C accesses B's y and A's x. This can be done because:
    1. B forms a closure including A, i.e. B can access A's arguments and variables.
    2. C forms a closure including B.
    3. Because B's closure includes A, C's closure includes A, C can access both B and A's arguments and variables. In other words, C chains the scopes of B and A in that order.
The reverse, however, is not true. A cannot access C, because A cannot access any argument or variable of B, which C is a variable of. Thus, C remains private to only B.

###6.5. Name conflicts?

* When two arguments or variables in the scopes of a closure have the same name, there is a name conflict. More inner scopes take precedence, so the inner-most scope takes the highest precedence, while the outer-most scope takes the lowest. This is the scope chain. The first on the chain is the inner-most scope, and the last is the outer-most scope. Consider the following:
```js
    function outside() {
      var x = 5;
      function inside(x) {
        return x * 2;
      }
      return inside;
    }

    outside()(10); // returns 20 instead of 10
```
* The name conflict happens at the statement return x and is between inside's parameter x and outside's variable x. The scope chain here is {inside, outside, global object}. Therefore inside's x takes precedences over outside's x, and 20 (inside's x) is returned instead of 10 (outside's x).

## 7. Using the arguments object?

* The arguments of a function are maintained in an array-like object. Within a function, you can address the arguments passed to it as follows:
 
arguments[i]

* where i is the ordinal number of the argument, starting at zero. So, the first argument passed to a function would be arguments[0]. The total number of arguments is indicated by arguments.length.

* Using the arguments object, you can call a function with more arguments than it is formally declared to accept. This is often useful if you don't know in advance how many arguments will be passed to the function.

* You can use arguments.length to determine the number of arguments actually passed to the function, and then access each argument using the arguments object.

* For example, consider a function that concatenates several strings. The only formal argument for the function is a string that specifies the characters that separate the items to concatenate. The function is defined as follows:
```js
  function myConcat(separator) {
     var result = ''; // initialize list
     var i;
     // iterate through arguments
     for (i = 1; i < arguments.length; i++) {
        result += arguments[i] + separator;
     }
     return result;
  }

    You can pass any number of arguments to this function, and it concatenates each argument into a string "list":
    // returns "red, orange, blue, "
    myConcat(', ', 'red', 'orange', 'blue');

    // returns "elephant; giraffe; lion; cheetah; "
    myConcat('; ', 'elephant', 'giraffe', 'lion', 'cheetah');

    // returns "sage. basil. oregano. pepper. parsley. "
    myConcat('. ', 'sage', 'basil', 'oregano', 'pepper', 'parsley');
                
```

`* Note: The arguments variable is "array-like", but not an array. It is array-like in that it has a numbered index and a length property. However, it does not possess all of the array-manipulation methods.`


## 8. Function parameters?

* Starting with ECMAScript 2015, there are two new kinds of parameters: default parameters and rest parameters.

### 8.1. Default parameters?

* In JavaScript, parameters of functions default to undefined. However, in some situations it might be useful to set a different default value. This is where default parameters can help.
* In the past, the general strategy for setting defaults was to test parameter values in the body of the function and assign a value if they are undefined. If in the following example, no value is provided for b in the call, its value would be undefined  when evaluating a*b and the call to multiply would have returned NaN. However, this is caught with the second line in this example:
  
```js
     function multiply(a, b) {
        b = typeof b !== 'undefined' ?  b : 1;

        return a * b;
      }

      multiply(5); // 5
```

With default parameters, the check in the function body is no longer necessary. Now, you can simply put 1 as the default value for b in the function head:

```js
    function multiply(a, b = 1) {
      return a * b;
    }

    multiply(5); // 5
```

### 8.2. Rest parameters?

* The rest parameter syntax allows us to represent an indefinite number of arguments as an array. In the example, we use the rest parameters to collect arguments from the second one to the end. We then multiply them by the first one. This example is using an arrow function, which is introduced in the next section.
```js
    function multiply(multiplier, ...theArgs) {
      return theArgs.map(x => multiplier * x);
    }

    var arr = multiply(2, 1, 2, 3);
    console.log(arr); // [2, 4, 6]
 ```
       
## 9. Arrow functions?

* An arrow function expression (previously, and now incorrectly known as fat arrow function) has a shorter syntax compared to function expressions and does not have its own this, arguments, super, or new.target. Arrow functions are always anonymous. See also this hacks.mozilla.org blog post: "ES6 In Depth: Arrow functions".

* Two factors influenced the introduction of arrow functions: shorter functions and non-binding of this.

### 9.1. Shorter functions?

* In some functional patterns, shorter functions are welcome. Compare:
```js
    var a = [
      'Hydrogen',
      'Helium',
      'Lithium',
      'Beryllium'
    ];

    var a2 = a.map(function(s) { return s.length; });

    console.log(a2); // logs [8, 6, 7, 9]

    var a3 = a.map(s => s.length);

    console.log(a3); // logs [8, 6, 7, 9]
```

### 9.2. No separate this?
 
* Until arrow functions, every new function defined its own this value (a new object in the case of a constructor, undefined in strict mode function calls, the base object if the function is called as an "object method", etc.). This proved to be less than ideal with an object-oriented style of programming.
```js
    function Person() {
      // The Person() constructor defines `this` as itself.
      this.age = 0;

      setInterval(function growUp() {
        // In nonstrict mode, the growUp() function defines `this` 
        // as the global object, which is different from the `this`
        // defined by the Person() constructor.
        this.age++;
      }, 1000);
    }

    var p = new Person();
```
In ECMAScript 3/5, this issue was fixed by assigning the value in this to a variable that could be closed over.
```js
      function Person() {
        var self = this; // Some choose `that` instead of `self`. 
                         // Choose one and be consistent.
        self.age = 0;

        setInterval(function growUp() {
          // The callback refers to the `self` variable of which
          // the value is the expected object.
          self.age++;
        }, 1000);
      }
```
* Alternatively, a bound function could be created so that the proper this value would be passed to the growUp() function.

* An arrow function does not have its own this; the this value of the enclosing execution context is used. Thus, in the following code, the this within the function that is passed to setInterval has the same value as this in the enclosing function:
```js
      function Person() {
        this.age = 0;

        setInterval(() => {
          this.age++; // |this| properly refers to the person object
        }, 1000);
      }

      var p = new Person();
 ```             
## 10. Function Recap?

* Functions package up code so you can easily use (and reuse) a block of code. Parameters are variables that are used to store the data that's passed into a function for the function to use. Arguments are the actual data that's passed into a function when it is invoked:
```js
      // x and y are parameters in this function declaration
      function add(x, y) {
        // function body
        var sum = x + y;
        return sum; // return statement
      }

      // 1 and 2 are passed into the function as arguments
      var sum = add(1, 2);
```
The function body is enclosed inside curly brackets:DEMICS
Departments
Teaching Faculty
Academic Calendar
Examinations
Syllabus
Meritorious Students
RESEARCH & INNOVATIONAWARDSPLACEMENTSADMISSIONS

```js
      function add(x, y) {
        // function body!
      }

      Return statements explicitly make your function return a value:

      return sum;

      You invoke or call a function to have it do something:

      add(1, 2);

      Returns: 3
```
## 11. Function Invocation?

The code inside the function will execute when "something" invokes (calls) the function:
    • When an event occurs (when a user clicks a button)
    • When it is invoked (called) from JavaScript code
    • Automatically (self invoked)
    
## 12.  Function Return?

* When JavaScript reaches a return statement, the function will stop executing.
If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.
* Functions often compute a return value. The return value is "returned" back to the "caller":
* ex-; Calculate the product of two numbers, and return the result:

```js
   var x = myFunction(4, 3);   // Function is called, return value will end up in x

    function myFunction(a, b) {
      return a * b;             // Function returns the product of a and b
    }
    The result in x will be:
    12
```
## 13. Using Return Values?

Returning a value from a function is great, but what's the use of a return value if you're not going to use the value to do something?
A function's return value can be stored in a variable or reused throughout your program as a function argument. Here, we have a function that adds two numbers together, and another function that divides a number by 2. We can find the average of 5 and 7 by using the add() function to add a pair of numbers together, and then by passing the sum of the two numbers add(5, 7) into the function divideByTwo() as an argument.
And finally, we can even store the final answer in a variable called average and use the variable to perform even more calculations in more places!
```js
      // returns the sum of two numbers
      function add(x, y) {
        return x + y;
      }
    
    
      // returns the value of a number divided by 2
      function divideByTwo(num) {
        return num / 2;
      }
    
    
      var sum = add(5, 7); // call the "add" function and store the returned value in the "sum" variable
      var average = divideByTwo(sum); // call the "divideByTwo" function and store the returned value in the "average" variable
```

## 14. Inline Function?

Call the emotions() function so that it prints the output you see below, but instead of passing the laugh() function as an argument, pass an inline function expression instead.
```js
    emotions("happy", laugh(2)); // you can use your laugh function from the previous quizzes
    Prints: "I am happy, haha!"

```
