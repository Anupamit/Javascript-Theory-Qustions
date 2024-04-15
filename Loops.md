# Looping JavaScripts

## 1. Loop

* There are many different kinds of loops, but they all essentially do the same thing: they repeat an action some number of times (and it's actually possible that number could be zero). The various loop mechanisms offer different ways to determine the start and end points of the loop. There are various situations that are more easily served by one type of loop over the others.
The statements for loops provided in JavaScript are:
    * `for` statement
    * `do...while` statement
    * `while` statement
    * `labeled` statement
    * `break` statement
    * `continue` statement
    * `for...in` statement
    * `for...of` statement

## 2. for Loop
* A `for` loop repeats until a specified condition evaluates to false. The JavaScript `for` loop is similar to the Java and C `for` loop. A `for` statement looks as follows:

            for ([initialExpression]; [condition]; [incrementExpression])
 
 Statements--
 
* When a `for` loop executes, the following occurs:
   The initializing expression `initialExpression`, if any, is executed. This expression usually initializes one or more loop      counters, but the syntax allows an expression of any degree of complexity. This expression can also declare variables.
    1. The `condition` expression is evaluated. If the value of `condition` is true, the loop statements execute. If the value          of `condition` is false, the `for` loop terminates. If the `condition` expression is omitted entirely, the condition is            assumed to be true.
    2. The `statement` executes. To execute multiple statements, use a block statement ({ ... }) to group those statements.
    3. If present, the update expression `incrementExpression` is executed.
    4. Control returns to step 2.

## 3. do.while  Loop
The `do...while` statement repeats until a specified condition evaluates to false. A `do...while` statement looks as follows:
do
    Statement--
    
while (condition);
* `statement` is always executed once before the condition is checked (and then again until the while condition returns false). * To execute multiple statements, use a block statement ({ ... }) to group those statements. If `condition` is true, the          `statement` executes again. At the end of every execution, the condition is checked. When the condition is false, execution    stops and control passes to the statement following `do...while`.
  
```js
      // Initialize a variable
    let count = 0;
    
    // Execute the loop at least once, then check the condition
    do {
        console.log("Count is: " + count);
        count++;
    } while (count < 5);
```

## 4. while  Loop
* A `while` statement executes its statements as long as a specified condition evaluates to true.                         *  * * A `while` statement looks as follows: 
  while (condition)
  statement
* If the condition becomes false, `statement` within the loop stops executing and control passes to the statement following the loop.
* The condition test occurs before `statement` in the loop is executed. If the condition returns true, `statement` is executed and the condition is tested again. If the condition returns false, execution stops and control is passed to the statement following `while`.
* To execute multiple statements, use a block statement ({ ... }) to group those statements.

```js
    // Initialize a variable
    let count = 0;
    
    // Execute the loop only if the condition is true
    while (count < 5) {
        console.log("Count is: " + count);
        count++;
    }

```
## 5. Parts of a While Loop
There are many different kinds of loops, but they all essentially do the same thing: they repeat an action some number of times.
Three main pieces of information that any loop should have are:

1. When to start: The code that sets up the loop — defining the starting value of a variable for instance.
2. When to stop: The logical condition to test whether the loop should continue.
3. How to get to the next item: The incrementing or decrementing step — for example, x = x * 3or x = x - 1
    
Here's a basic while loop example that includes all three parts.

```js
    var start = 0; // when to start
    while (start < 10) { // when to stop
     console.log(start);
     start = start + 2; // how to get to the next item
    }
    Prints:
    0
    2
    4
    6
    8
```
                
If a loop is missing any of these three things, then you might find yourself in trouble. For instance, a missing stop condition can result in a loop that never ends!

## 6.Part of For  Loop
The `for loop` explicitly forces you to define the start point, stop point, and each step of the loop. In fact, you'll get an `Uncaught SyntaxError: Unexpected token )` if you leave out any of the three required pieces.
```js
    for ( start; stop; step ) {
      // do this thing
    }
    Here's an example of a for loop that prints out the values from 0 to 5.
    Notice the semicolons separating the different statements of the for loop: `var i = 0; i < 6; i = i + 1`
    for (var i = 0; i < 6; i = i + 1) {
      console.log("Printing out i = " + i);
    }
    Prints:
    Printing out i = 0
    Printing out i = 1
    Printing out i = 2
    Printing out i = 3
    Printing out i = 4
    Printing out i = 5
```
## 7. labeled statement
* A `label` provides a statement with an identifier that lets you refer to it elsewhere in your program. For example, you can use a label to identify a loop, and then use the `break` or `continue` statements to indicate whether a program should interrupt the loop or continue its execution.
* The syntax of the labeled statement looks like the following:
`label : statement`
* The value of `label` may be any JavaScript identifier that is not a reserved word. The `statement` that you identify with a label may be any statement.


## 8.break statement
* Use the `break` statement to terminate a loop, `switch`, or in conjunction with a labeled statement.
    * When you use `break` without a label, it terminates the innermost enclosing `while`, `do-while`, `for`, or `switch` immediately and transfers control to the following statement.
    * When you use `break` with a label, it terminates the specified labeled statement.
* The syntax of the `break` statement looks like this:
break [label];
* The first form of the syntax terminates the innermost enclosing loop or `switch`; the second form of the syntax terminates the specified enclosing labeled statement.


## 9. continue statement
* The `continue` statement can be used to restart a `while`, `do-while`, `for`, or `label`statement.
    * When you use `continue` without a label, it terminates the current iteration of the innermost enclosing `while`, `do-while`, or `for` statement and continues execution of the loop with the next iteration. In contrast to the `break` statement, `continue` does not terminate the execution of the loop entirely. In a `while` loop, it jumps back to the condition. In a `for` loop, it jumps to the `increment-expression`.
    * When you use `continue` with a label, it applies to the looping statement identified with that label.
* The syntax of the `continue` statement looks like the following:
continue [label];


## 10. for...in statement
The `for...in` statement iterates a specified variable over all the enumerable properties of an object. For each distinct property, JavaScript executes the specified statements. A `for...instatement` looks as follows:
```js
    for (variable in object) {
      statements
    }
```
## 11. Nested Loop
Did you know you can also nest loops inside of each other? Paste this nested loop in your browser and take a look at what it prints out:
```js
    for (var x = 0; x < 5; x = x + 1) {
      for (var y = 0; y < 3; y = y + 1) {
        console.log(x + "," + y);
      }
    }
    Prints:
    0, 0
    0, 1
    0, 2
    1, 0
    1, 1
    1, 2
    2, 0
    2, 1
    2, 2
    3, 0
    3, 1
    3, 2
    4, 0
    4, 1
    4, 2
```                  
Notice the order that the output is being displayed.
For each value of `x` in the outer loop, the inner for loop executes completely. The outer loop starts with `x = 0`, and then the inner loop completes its cycle with all values of `y`:
`x = 0` and `y = 0, 1, 2` // corresponds to (0, 0), (0, 1), and (0, 2)
Once the inner loop is done iterating over `y`, then the outer loop continues to the next value, `x = 1`, and the whole process begins again.
`x = 0` and `y = 0, 1, 2` // (0, 0) (0, 1) and (0, 2)
`x = 1` and `y = 0, 1, 2` // (1, 0) (1, 1) and (1, 2)
`x = 2` and `y = 0, 1, 2` // (2, 0) (2, 1) and (2, 2)
etc.

            NOTE: Nested loops can be tricky at first. 

## 12. Increment and Decrement
The JavaScript Increment and Decrement Operators are used to increase or decrease the value by 1. For instance, Incremental operator `++` is used to increase the existing variable value by 1 (x = x + 1). The decrement operator `– –` is used to decrease or subtract the existing value by 1 (x = x – 1).
```js
    // Here is a summary of operators you've learned so far:
    `x++` or `++x` // same as x = x + 1 
    `x--` or `--x` // same as x = x - 1
    `x += 3` // same as x = x + 3
    `x -= 6` // same as x = x - 6
    `x *= 2` // same as x = x * 2
    `x /= 5` // same as x = x / 5
```
* Let’s explore the JavaScript prefix and postfix
    1. `++i` (Pre increment): It will increment the value of i even before assigning it to the variable i.
    2. `i++` (Post-increment): The operator will return the variable value first (i.e, i value) then only i value will incremented by 1.
    3. `–i` (Pre decrement): It decrement the value of i even before assigning it to the variable i.
    4. `i–` (Post decrement): The operator will return the variable value first (i.e, i value) then only i value is decrements by 1.
