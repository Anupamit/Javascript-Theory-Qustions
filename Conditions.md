# conditionals-java-script
conditionals in java script


### 1. conditionals
Conditional statements are used to decide the flow of execution based on different conditions. If a condition is true, you can perform one action and if the condition is false, you can perform another action.
* Different Types of Conditional Statements
There are mainly three types of conditional statements in JavaScript.
    1. If statement
    2. If…Else statement
    3. If…Else If…Else statement
    
* If...else statements

If...else statements allow you to execute certain pieces of code based on a condition, or set of conditions, being met.

                `if (/* this expression is true */) {
                  // run this code
                } else {
                  // run this code
                }
                `
This is extremely helpful because it allows you to choose which piece of code you want to run based on the result of an expression. For example,

                `var a = 1;
                var b = 2;

                if (a > b) {
                  console.log("a is greater than b");
                } else {
                  console.log("a is less than or equal to b");
                }
                Prints: "a is less than or equal to b"
                `
* A couple of important things to notice about if...else statements.
The value inside the if statement is always converted to true or false. Depending on the value, the code inside the if statement is run or the code inside the else statement is run, but not both. The code inside the if and else statements are surrounded by curly braces {...} to separate the conditions and indicate which code should be run.
* When coding, sometimes you may only want to use an if statement. However, if you try to use only an else statement, then you will receive the error SyntaxError: Unexpected token else. You’ll see this error because else statements need an if statement in order to work. You can’t have an else statement without first having an ifstatement.

* Else if statements

In JavaScript, you can represent this secondary check by using an extra if statement called an else if statement.`          `              `var weather = "sunny";

            if (weather === "snow") {
              console.log("Bring a coat.");
            } else if (weather === "rain") {
              console.log("Bring a rain jacket.");
            } else {
              console.log("Wear what you have on.");
            }
           
            Prints: Wear what you have on.`
            
By adding the extra else if statement, you're adding an extra conditional statement.
If it’s not going to snow, then the code will jump to the else if statement to see if it’s going to rain. If it’s not going to rain, then the code will jump to the else statement.
The else statement essentially acts as the "default" condition in case all the other if statements are false.

### 2. Logical Operators program
Here’s the logical expression used to represent Julia’s weekend plans:

            `var colt = "not busy";
            var weather = "nice";

            if (colt === "not busy" && weather === "nice") {
              console.log("go to the park");
            }
            Prints: "go to the park"`

Notice the && in the code above.
The && symbol is the logical AND operator, and it is used to combine two logical expressions into one larger logical expression. If both smaller expressions are true, then the entire expression evaluates to true. If either one of the smaller expressions is false, then the whole logical expression is false.
Another way to think about it is when the && operator is placed between the two statements, the code literally reads, "if Colt is not busy AND the weather is nice, then go to the park".
### 3. Logical expressions
Logical expressions are similar to mathematical expressions, except logical expressions evaluate to either true or false.
11 != 12
Returns: true
You’ve already seen logical expressions when you write comparisons. A comparison is just a simple logical expression.
Similar to mathematical expressions that use +, -, *, / and %, there are logical operators &&, || and ! that you can use to create more complex logical expressions.
### 4. Logical operators symbols
Logical operators can be used in conjunction with boolean values (true and false) to create complex logical expressions.
By combining two boolean values together with a logical operator, you create a logical expression that returns another boolean value. Here’s a table describing the different logical operators:
Operator
Meaning
Example-
            `How it works
            &&
            Logical AND
            value1 && value2
            Returns true if both value1 and value2 evaluate to true.
            ||
            Logical OR
            value1 || value2
            Returns true if either value1 or value2 (or even both!) evaluates to true.
            !
            Logical NOT
            !value1
            Returns the opposite of value1. If value1 is true, then !value1 is false.`


### 5. Logical AND and OR
* Before you advance any further in the lesson, here’s the truth tables for logical AND ( && ) and logical OR ( || ).

         && (AND)
        A
        B
        A && B`
                  `  true
                    true
                    true
                    true
                    false
                    false
                    false
                    true
                    false
                    false
                    false
                    false`
       ` || (OR)
        A
        B
        A || B
                    true
                    true
                    true
                    true
                    false
                    true
                    false
                    true
                    true
                    false
                    false
                    False`
Truth tables are used to represent the result of all the possible combinations of inputs in a logical expression. A represents the boolean value on the left-side of the expression and B represents the boolean value on the right-side of the expression.
Truth tables can be helpful for visualizing the different outcomes from a logical expression. However, do you notice anything peculiar about the truth tables for logical AND and OR?
### 6.Short-circuiting

* In some scenarios, the value of B in logical AND and OR doesn't matter
* In both tables, there are specific scenarios where regardless of the value of B, the value of A is enough to satisfy the condition.
* For example-
if you look at A AND B, if A is false, then regardless of the value B, the total expression will always evaluate to false because both A and B must be true in order for the entire expression to be true.

* This behavior is called short-circuiting because it describes the event when later arguments in a logical expression are not considered because the first argument already satisfies the condition.


### 7. Truthy and Falsy
Every value in JavaScript has an inherent boolean value. When that value is evaluated in the context of a boolean expression, the value will be transformed into that inherent boolean value.
The paragraph above is pretty dense with information. You should probably re-read it again! ☝️

* Falsy values

A value is falsy if it converts to false when evaluated in a boolean context. For example, an empty String "" is falsy because, "" evaluates to false. You already know if...else statements, so let's use them to test the truthy-ness of "".

                `if ("") {
                    console.log("the value is truthy");
                } else {
                    console.log("the value is falsy");
                }
                Returns: "the value is falsy"
                `
Here’s the list of all of the falsy values:
    1. the Boolean value false
    2. the null type
    3. the undefined type
    4. the number 0
    5. the empty string ""
    6. the odd value NaN (stands for "not a number", check out the NaN MDN article)
That's right, there are only six falsy values in all of JavaScript!

* Truthy values

A value is truthy if it converts to true when evaluated in a boolean context. For example, the number 1 is truthy because, 1 evaluates to true. Let's use an if...else statement again to test this out:

                `if (1) {
                    console.log("the value is truthy");
                } else {
                    console.log("the value is falsy");
                }
                Returns: "the value is truthy"
                `
Here are some other examples of truthy values:
true
42
"pizza"
"0"
"null"
"undefined"
{}
[]
Essentially, if it's not in the list of falsy values, then it's truthy!

### 8. Ternary operator
* The ternary operator provides you with a shortcut alternative for writing lengthy if...else statements.
conditional ? (if condition is true) : (if condition is false)
* To use the ternary operator, first provide a conditional statement on the left-side of the ?. Then, between the ? and : write the code that would run if the condition is true and on the right-hand side of the : write the code that would run if the condition is false. For example, you can rewrite the example code above as:

       `     var isGoing = true;
            var color = isGoing ? "green" : "red";
            console.log(color);
            Prints: "green"
            `
* This code not only replaces the conditional, but it also handles the variable assignment for color.
* If you breakdown the code, the condition isGoing is placed on the left side of the ?. Then, the first expression, after the ?, is what will be run if the condition is true and the second expression after the, :, is what will be run if the condition is false.


### 9. Switch statement
A switch statement is an another way to chain multiple else if statements that are based on the same value without using conditional statements. Instead, you just switch which piece of code is executed based on a value.


                   `     switch (option) {
                          case 1:
                            console.log("You selected option 1.");
                          case 2:
                            console.log("You selected option 2.");
                          case 3:
                            console.log("You selected option 3.");
                          case 4:
                            console.log("You selected option 4.");
                          case 5:
                            console.log("You selected option 5.");
                          case 6:
                            console.log("You selected option 6.");
                        }`

Here, each else if statement (option === [value]) has been replaced with a case clause (case: [value]) and those clauses have been wrapped inside the switch statement.
When the switch statement first evaluates, it looks for the first case clause whose expression evaluates to the same value as the result of the expression passed to the switch statement. Then, it transfers control to that case clause, executing the associated statements.

                    `So, if you set option equal to 3...
                    var option = 3;

                    switch (option) {
                      ...
                    }
                    Prints:
                    You selected option 3.
                    You selected option 4.
                    You selected option 5.
                    You selected option 6.

                    ...then the switch statement prints out options 3, 4, 5, and 6. `

But that’s not exactly like the original if...else code at the top? So what’s missing?
### 9. Break statement
The break statement can be used to terminate a switch statement and transfer control to the code following the terminated statement. By adding a break to each case clause, you fix the issue of the switch statement falling-through to other case clauses.

                `
                var option = 3;

                switch (option) {
                  case 1:
                    console.log("You selected option 1.");
                    break;
                  case 2:
                    console.log("You selected option 2.");
                    break;
                  case 3:
                    console.log("You selected option 3.");
                    break;
                  case 4:
                    console.log("You selected option 4.");
                    break;
                  case 5:
                    console.log("You selected option 5.");
                    break;
                  case 6:
                    console.log("You selected option 6.");
                    break; // technically, not needed
                }

                Prints: You selected option 3.`


### 10. Falling Through
 In some situations, you might want to leverage the "falling-through" behavior of switch statements to your advantage.
For example, when your code follows a hierarchical-type structure.


                `var tier = "nsfw deck";
                var output = "You’ll receive "

                switch (tier) {
                  case "deck of legends":
                    output += "a custom card, ";
                  case "collector's deck":
                    output += "a signed version of the Exploding Kittens deck, ";
                  case "nsfw deck":
                    output += "one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and ";
                  default:
                    output += "one copy of the Exploding Kittens card game.";
                }

                console.log(output);

                Prints: You’ll receive one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and one copy of                    the Exploding Kittens card game.`
