# Data-Type-And-Variables
Data Type And Variables in java script





### 1. Numbers

Defining a number in JavaScript is actually pretty simple. The Number data type includes any positive or negative integer, as well as decimals. Entering a number into the console will return it right back to you.

3 

Returns: 3





### 2. Arithmetic operations

You can also perform calculations with numbers pretty easily. Basically type out an expression the way you would type it in a calculator.

3 + 2.1

Returns: 5.1




### 3. Comparing numbers

What about comparing numbers? Can you do that? Well of course you can!

Just like in mathematics, you can compare two numbers to see if one’s greater than, less than, or equal to the other.

5 > 10

Returns: false

5 < 10

Returns: true

5 == 10

Returns: false




### 4. comparing sign
Comparisons between numbers will either evaluate to true or false. Here are some more examples, so you can try it out!

Operator

Meaning

<

Less than

>

Greater than

<=

Less than or Equal to

>=

Greater than or Equal to

==

Equal to

!=

Not Equal to




### 5. Comments

You can use comments to help explain your code and make things clearer. In JavaScript, comments are marked with a double forward-slash //. Anything written on the same line after the // will not be executed or displayed. To have the comment span multiple lines, mark the start of your comment with a forward-slash and star, and then enclose your comment inside a star and forward-slash /* … */.

// this is a single-line comment



/*

this is

a multi-line

comment

*/

Some of the quizzes in this course might include comments that give you hints or instructions to complete the quiz. Comments are often used to clarify and document non-obvious code. It's good practice to include code comments to improve code readability.





### 6. strings

It is correct to either use double " or single ' quotes with strings, as long as you're consistent. 

for labs and projects suggests using single quotes to define string literals.




### 7. String concatenation

Strings are a collection of characters enclosed inside double or single quotes. You can use strings to represent data like sentences, names, addresses, and more. Did you know you can even add strings together? In JavaScript, this is called concatenating. Concatenating two strings together is actually pretty simple!

"Hello," + " New York City"

Returns: "Hello, New York City"

You will see other ways to concatenate and do even more with strings later in this course. But for now, practice using the addition + operator.





### 8. Variable

With variables, you no longer need to work with one-time-use data.

At the beginning of this course, you declared the value of a string, but you didn't have a way to access or reuse the string later.

"Hello"; // Here's a String "Hello"

"Hello" + " World"; // Here's a new String (also with the value "Hello") concatenated with " World"

Storing the value of a string in a variable is like packing it away for later use.

var greeting = "Hello";

Now, if you want to use "Hello" in a variety of sentences, you don't need to duplicate "Hello" strings. You can just reuse the greeting variable.

You can also change the start of the greeting by reassigning a new string value to the variable greeting.

greeting = "Hola";

greeting + " World!";

Returns: Hola World!

greeting + " Mike!";

Returns: Hola Mike!





### 9. Naming conventions

When you create a variable, you write the name of the variable using camelCase (the first word is lowercase, and all following words are uppercase). Also try to use a variable name that accurately, but succinctly describes what the data is about.

var totalAfterTax = 53.03; // uses camelCase if the variable name is multiple words

var tip = 8; // uses lowercase if the variable name is one word

Not using camelCase for your variables names is not going to necessarily break anything in JavaScript. But there are recommended style guides used in all programming languages that help keep code consistent, clean, and easy-to-read. This is especially important when working on larger projects that will be accessed by multiple developers.





### 10. Indexing

Did you know that you can access individual characters in a string? To access an individual character, you can use the character's location in the string, called its index. Just put the index of the character inside square brackets (starting with [0] as the first character) immediately after the string. For example:

"James"[0];

Returns: "J"

or more commonly, you will see it like this, using a variable:

var name = "James";

name[0];

Returns: "J"




### 11. Escaping strings

There are some cases where you might want to create a string that contains more than just numbers and letters. For example, what if you want to use quotes in a string?

"The man whispered, "please speak to me.""

Uncaught SyntaxError: Unexpected identifier

If you try to use quotes within a string, you will receive a SyntaxError like the one above.

Because you need to use quotes to denote the beginning and end of strings, the JavaScript engine misinterprets the meaning of your string by thinking "The man whispered, " is the string. Then, it sees the remaining please speak to me."" and returns a SyntaxError.

If you want to use quotes inside a string, and have JavaScript not misunderstand your intentions, you’ll need a different way to write quotes. Thankfully, JavaScript has a way to do this using the backslash character ( \ ).





### 12. Escaping characters

In JavaScript, you use the backslash to escape other characters.

Escaping a character tells JavaScript to ignore the character's special meaning and just use the literal value of the character. This is helpful for characters that have special meanings like in our previous example with quotes "…".

Because quotes are used to signify the beginning and end of a string, you can use the backslash character to escape the quotes in order to access the literal quote character.

"The man whispered, \"please speak to me.\""

Returns: The man whispered, "please speak to me."

This guarantees that the JavaScript engine doesn’t misinterpret the string and result in an error.




### 13. Special characters

Quotes aren’t the only special characters that need to be escaped, there’s actually quite a few. However, to keep it simple, here’s a list of some common special characters in JavaScript.

Code

Character

\\

\ (backslash)

\"

'' (double quote)

\'

' (single quote)

\n

newline

\t

tab

The last two characters listed in the table, newline \n and tab \t, are unique because they add additional whitespace to your Strings. A newline character will add a line break and a tab character will advance your line to the next tab stop.

"Up up\n\tdown down"

Returns:

Up up

 down down




### 14.Comparing strings

Another way to work with strings is by comparing them. You've seen the comparison operators ==and != when you compared numbers for equality. You can also use them with strings! For example, let’s compare the string "Yes" to "yes".

"Yes" == "yes"

Returns: false

When you run this in the console, it returns false. Why is that? "Yes" and "yes" are the same string, right? Well not quite.





### 15. Case-sensitive

When you compare strings, case matters. While both string use the same letters (and those letters appear in the same order), the first letter in the first string is a capital Y while the first letter in the second string is a lowercase y.

'Y' != 'y'

Returns: true




### 16. Booliean

Boolean, or boolean logic, is a subset of algebra used for creating true/false statements. Boolean expressions use the operators AND, OR, XOR, and NOT to compare values and return a true or false result. These boolean operators are described in the following four examples.

x AND y - returns True if both x and y are true; returns False if either x or y are false.

• x OR y - returns True if either x or y, or both x and y are true; returns False only if x and y are both false.

• x XOR y - returns True if only x or y is true; returns False if x and y are both true or both false.

• NOT x - returns True if x is false (or null); returns False if x is true.

Since computers operate in binary (using only zeros and ones), computer logic can often expressed in boolean terms. For example, a true statement returns a value of 1, while a false statement returns a value of 0. Of course, most calculations require more than a simple true/false statement. Therefore, computer processors perform complex calculations by linking multiple binary (or boolean) statements together. Complex boolean expressions can be expressed as a series of logic gates.

Boolean expressions are also supported by most search engines. When you enter keywords in a search engine, you can refine your search using boolean operators. For example, if you want to look up information about the Apple iMac, but want avoid results about apples (the fruit) you might search for "Apple AND iMac NOT fruit." This would produce results about iMac computers, while avoiding results with the word "fruit." While most search engines support boolean operators, their syntaxrequirements may vary. For example, instead of the words AND and NOT, the operators "+" and "-" may be required. You can look up the correct syntax in the help section of each search engine's website.




### 17. Javascript Undefined vs NULL

Many a times we often get confused on whats the difference between UNDEFINED and NULL.

undefined means a variable has been declared but has not yet been assigned a value. On the other hand, null is an assignment value. It can be assigned to a variable as a representation of no value.

Also, undefined and null are two distinct types: undefined is a type itself (undefined) while null is an object.

Unassigned variables are initialized by JavaScript with a default value of undefined. JavaScript never sets a value to null. That must be done programmatically.




### 18. What is NaN?

NaN stands for "Not-A-Number" and it's often returned indicating an error with number operations. For instance, if you wrote some code that performed a math calculation, and the calculation failed to produce a valid number, NaN might be returned.

// calculating the square root of a negative number will return NaN

Math.sqrt(-10)



// trying to divide a string by 5 will return NaN

"hello"/5




### 19. Equality

So far, you’ve seen how you can use == and != to compare numbers and strings for equality. However, if you use == and != in situations where the data you’re comparing is mixed, it can lead to some interesting results. For example,

"1" == 1

Returns: true

and

0 == false

Returns: true

both evaluate to true. Why is that?




### 20.Implicit type coercion

JavaScript is known as a loosely typed language.

Basically, this means that when you’re writing JavaScript code, you do not need to specify data types. Instead, when your code is interpreted by the JavaScript engine it will automatically be converted into the "appropriate" data type. This is called implicit type coercion and you’ve already seen examples like this before when you tried to concatenate strings with numbers.

"julia" + 1

Returns: "julia1"



### 21. semicolons

One thing to take notice of in all the examples you've seen so far is the use of semicolons ; at the end of each line. Semicolons make it clear where one statement ends and another begins. This is especially handy when multiple lines of code are written on the same line (which is valid JavaScript, but definitely not recommended!). For instance:

var totalAfterTax = 53.03 var tip = 8 // this is incorrect!

Uncaught SyntaxError: Unexpected token var

vs.

var totalAfterTax = 53.03; var tip = 8; // this is correct!

Not adding semicolons to the end of each line can cause bugs and errors in your programs. JavaScript does have ways to occasionally predict where semicolons should be, but just like how type coercion can result in some unexpected quirky behavior in JavaScript, it's good practice to not depend on it.




### 22. Directions

Define two variables called thingOne and thingTwo and assign them values. Print the values of both variables in one console.log statement using concatenation. For example,

red blue

where "red" is the value of thingOne and "blue" is the value of thingTwo. Don't forget to use semicolons!

