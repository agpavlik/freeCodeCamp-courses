# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 1. Comment Your JavaScript Code
Comments are lines of code that JavaScript will intentionally ignore. Comments are a great way to leave notes to yourself and to other people who will later need to figure out what that code does.

There are two ways to write comments in JavaScript:

Using // will tell JavaScript to ignore the remainder of the text on the current line. This is an in-line comment:

// This is an in-line comment.
You can make a multi-line comment beginning with /* and ending with */. This is a multi-line comment:

/* This is a
multi-line comment */
### NOTE: 
As you write code, you should regularly add comments to clarify the function of parts of your code. Good commenting can help communicate the intent of your code—both for others and for your future self.

---

## 2. Declare JavaScript Variables
In computer science, data is anything that is meaningful to the computer. JavaScript provides seven different data types which are undefined, null, boolean, string, symbol, number, and object.

For example, computers distinguish between numbers, such as the number 12, and strings, such as "12", "dog", or "123 cats", which are collections of characters. Computers can perform mathematical operations on a number, but not on a string.

Variables allow computers to store and manipulate data in a dynamic fashion. They do this by using a "label" to point to the data rather than using the data itself. Any of the seven data types may be stored in a variable.

Variables are similar to the x and y variables you use in mathematics, which means they're a simple name to represent the data we want to refer to. Computer variables differ from mathematical variables in that they can store different values at different times.

We tell JavaScript to create or declare a variable by putting the keyword var in front of it, like so:

```javascript
var ourName;
```
 
creates a variable called ourName. In JavaScript we end statements with semicolons.

Variable names can be made up of numbers, letters, and $ or _, but may not contain spaces or start with a number.

---

## 3. Storing Values With the assignment Operator

In JavaScript, you can store a value in a variable with the assignment operator.

```javascript
myVariable = 5;
```

This assigns the Number value 5 to myVariable.

If there are any calculations to the right of the = operator, those are performed before the value is assigned to the variable on the left of the operator.

```javascript
myVar = 5;
myNum = myVar;
```
First, this code creates a variable named myVar. Then, the code assigns 5 to myVar. Now, if myVar appears again in the code, the program will treat it as if it is 5.

Assigns 5 to myVar and then resolves myVar to 5 again and assigns it to myNum.

---

## 4. Assigning the Value of One Variable to Another

After a value is assigned to a variable using the assignment operator, you can assign the value of that variable to another variable using the assignment operator.

```javascript
var myVar;
myVar = 5;
var myNum;
myNum = myVar;
```

The above declares a myVar variable with no value, then assigns it the value 5. Next, a variable named myNum is declared with no value. Then, the contents of myVar (which is 5) is assigned to the variable myNum. Now, myNum also has the value of 5.

---

## 5. Initializing Variables with the Assignment Operator
It is common to initialize a variable to an initial value in the same line as it is declared.

```javascript
var myVar = 0;
```
Creates a new variable called myVar and assigns it an initial value of 0.

---

## 6. Declare String Variables
Previously you used the following code to declare a variable:

```javascript
var myName;
```
But you can also declare a string variable like this:
```javascript
var myName = "your name";
```
"your name" is called a string literal. A string literal, or string, is a series of zero or more characters enclosed in single or double quotes.

---

## 7. Understanding Uninitialized Variables
When JavaScript variables are declared, they have an initial value of undefined. If you do a mathematical operation on an undefined variable your result will be `NaN` which means "Not a Number". If you concatenate a string with an undefined variable, you will get a string of undefined.

---

## 8. Understanding Case Sensitivity in Variables
In JavaScript all variables and function names are case sensitive. This means that capitalization matters.

MYVAR is not the same as MyVar nor myvar. It is possible to have multiple distinct variables with the same name but different casing. It is strongly recommended that for the sake of clarity, you do not use this language feature.

Best Practice

Write variable names in JavaScript in camelCase. In camelCase, multi-word variable names have the first word in lowercase and the first letter of each subsequent word is capitalized.

Examples:
```javascript
var someVariable;
var anotherVariableName;
var thisVariableNameIsSoLong;
```
---

## 9. Explore Differences Between the var and let Keywords
One of the biggest problems with declaring variables with the var keyword is that you can easily overwrite variable declarations:
```javascript
var camper = "James";
var camper = "David";
console.log(camper);
```
In the code above, the camper variable is originally declared as James, and is then overridden to be David. The console then displays the string David.

In a small application, you might not run into this type of problem. But as your codebase becomes larger, you might accidentally overwrite a variable that you did not intend to. Because this behavior does not throw an error, searching for and fixing bugs becomes more difficult.

A keyword called `let` was introduced in ES6, a major update to JavaScript, to solve this potential issue with the `var` keyword. You'll learn about other ES6 features in later challenges.

If you replace var with let in the code above, it results in an error:
```javascript
let camper = "James";
let camper = "David";
```
The error can be seen in your browser console.

So unlike var, when you use let, a variable with the same name can only be declared once.

---

## 10. Declare a Read-Only Variable with the const Keyword
The keyword let is not the only new way to declare variables. In ES6, you can also declare variables using the const keyword.

`const` has all the awesome features that `let` has, with the added bonus that variables declared using const are read-only. They are a constant value, which means that once a variable is assigned with const, it cannot be reassigned:

```javascript
const FAV_PET = "Cats";
FAV_PET = "Dogs";
```
The console will display an error due to reassigning the value of FAV_PET.

You should always name variables you don't want to reassign using the const keyword. This helps when you accidentally attempt to reassign a variable that is meant to stay constant.

### Note: 
It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays). You will learn more about objects, arrays, and immutable and mutable values in later challenges. Also in later challenges, you will see examples of uppercase, lowercase, or camelCase variable identifiers.

---

## 11. Add Two Numbers with JavaScript
Number is a data type in JavaScript which represents numeric data.

Now let's try to add two numbers using JavaScript.

JavaScript uses the + symbol as an addition operator when placed between two numbers.

Example:
```javascript
const myVar = 5 + 10;
```
myVar now has the value 15.

---

## 12. Subtract One Number from Another with JavaScript
We can also subtract one number from another.

JavaScript uses the - symbol for subtraction.

Example
```javascript
const myVar = 12 - 6;
```
myVar would have the value 6.

---

## 13. Multiply Two Decimals with JavaScript
In JavaScript, you can also perform calculations with decimal numbers, just like whole numbers.

Let's multiply two decimals together to get their product.
```javascript
var product = 2.0 * 2.5;
```

---

## 14. Divide One Decimal by Another with JavaScript
Now let's divide one decimal by another.

```javascript
var quotient = 4.4 / 2.0;
```
---

## 15. Finding a Remainder in JavaScript
The remainder operator % gives the remainder of the division of two numbers.

Example
```javascript
5 % 2 = 1
5 / 2 = 2 remainder 1
2 * 2 = 4
5 - 4 = 1
```
### Usage
In mathematics, a number can be checked to be even or odd by checking the remainder of the division of the number by 2. Even numbers have a remainder of 0, while odd numbers a remainder of 1.
```javascript
17 % 2 = 1
48 % 2 = 0
```
###Note: 
The remainder operator is sometimes incorrectly referred to as the modulus operator. It is very similar to modulus, but does not work properly with negative numbers.

---

## 16. Compound Assignment With Augmented Addition
In programming, it is common to use assignments to modify the contents of a variable. Remember that everything to the right of the equals sign is evaluated first, so we can say:
```javascript
myVar = myVar + 5;
```
to add 5 to myVar. Since this is such a common pattern, there are operators which do both a mathematical operation and assignment in one step.

One such operator is the += operator.
```javascript
let myVar = 1;
myVar += 5;
console.log(myVar);
```
6 would be displayed in the console.

---

## 17. Compound Assignment With Augmented Subtraction
Like the `+=` operator, `-=` subtracts a number from a variable.
```javascript
myVar = myVar - 5;
```
will subtract 5 from myVar. This can be rewritten as:
```javascript
myVar -= 5;
```
---

## 18. Compound Assignment With Augmented Multiplication
The `*=` operator multiplies a variable by a number.
```javascript
myVar = myVar * 5;
```
will multiply myVar by 5. This can be rewritten as:
```javascript
myVar *= 5;
```
---

## 19. Compound Assignment With Augmented Division
The `/=` operator divides a variable by another number.
```javascript
myVar = myVar / 5;
```
Will divide myVar by 5. This can be rewritten as:
```javascript
myVar /= 5;
```
---

## 20. Escaping Literal Quotes in Strings
When you are defining a string you must start and end with a single or double quote. What happens when you need a literal quote: " or ' inside of your string?

In JavaScript, you can escape a quote from considering it as an end of string quote by placing a backslash (\) in front of the quote.
```javascript
const sampleStr = "Alan said, \"Peter is learning JavaScript\".";
```
This signals to JavaScript that the following quote is not the end of the string, but should instead appear inside the string. So if you were to print this to the console, you would get:

Alan said, "Peter is learning JavaScript".

---

## 21. Quoting Strings with Single Quotes
String values in JavaScript may be written with single or double quotes, as long as you start and end with the same type of quote. Unlike some other programming languages, single and double quotes work the same in JavaScript.
```javascript
const doubleQuoteStr = "This is a string"; 
const singleQuoteStr = 'This is also a string';
```
The reason why you might want to use one type of quote over the other is if you want to use both in a string. This might happen if you want to save a conversation in a string and have the conversation in quotes. Another use for it would be saving an `<a>` tag with various attributes in quotes, all within a string.

const conversation = 'Finn exclaims to Jake, "Algebraic!"';
However, this becomes a problem if you need to use the outermost quotes within it. Remember, a string has the same kind of quote at the beginning and end. But if you have that same quote somewhere in the middle, the string will stop early and throw an error.
```javascript
const goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"'; 
const badStr = 'Finn responds, "Let's go!"';
```
Here badStr will throw an error.

In the goodStr above, you can use both quotes safely by using the backslash \ as an escape character.

### Note:
The backslash \ should not be confused with the forward slash /. They do not do the same thing.

---

## 22. Escape Sequences in Strings
Quotes are not the only characters that can be escaped inside a string. Escape sequences allow you to use characters you may not otherwise be able to use in a string.
```
Code	Output
\'	single quote
\"	double quote
\\	backslash
\n	newline
\t	tab
\r	carriage return
\b	backspace
\f	form feed
```
Note that the backslash itself must be escaped in order to display as a backslash.

---

## 23. Concatenating Strings with Plus Operator
In JavaScript, when the + operator is used with a String value, it is called the concatenation operator. You can build a new string out of other strings by concatenating them together.

Example
```javascript
'My name is Alan,' + ' I concatenate.'
```
### Note:
Watch out for spaces. Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.

Example:
```javascript
const ourStr = "I come first. " + "I come second.";
```
The string `I come first. I come second.` would be displayed in the console.

---

## 24. Concatenating Strings with the Plus Equals Operator
We can also use the `+=` operator to concatenate a string onto the end of an existing string variable. This can be very helpful to break a long string over several lines.

### Note:
Watch out for spaces. Concatenation does not add spaces between concatenated strings, so you'll need to add them yourself.

Example:
```javascript
let ourStr = "I come first. ";
ourStr += "I come second.";
```
ourStr now has a value of the string `I come first. I come second.`.

---

## 25. Constructing Strings with Variables
Sometimes you will need to build a string. By using the concatenation operator (+), you can insert one or more variables into a string you're building.

Example:
```javascript
const ourName = "freeCodeCamp";
const ourStr = "Hello, our name is " + ourName + ", how are you?";
```
ourStr would have a value of the string `Hello, our name is freeCodeCamp, how are you?.`

---

## 26. Appending Variables to Strings
Just as we can build a string over multiple lines out of string literals, we can also append variables to a string using the plus equals (+=) operator.

Example:
```javascript
const anAdjective = "awesome!";
let ourStr = "freeCodeCamp is ";
ourStr += anAdjective;
```
ourStr would have the value `freeCodeCamp is awesome!.`

---

## 27. Find the Length of a String
You can find the length of a String value by writing .length after the string variable or string literal.
```javascript
console.log("Alan Peter".length);
```
The value 10 would be displayed in the console. Note that the space character between "Alan" and "Peter" is also counted.

For example, if we created a variable `const firstName = "Ada"`, we could find out how long the string Ada is by using the `firstName.length` property.

---

## 28. Use Bracket Notation to Find the First Character in a String
Bracket notation is a way to get a character at a specific index within a string.

Most modern programming languages, like JavaScript, don't start counting at 1 like humans do. They start at 0. This is referred to as Zero-based indexing.

For example, the character at index 0 in the word Charles is C. So if const firstName = "Charles", you can get the value of the first letter of the string by using firstName[0].

Example:
```javascript
const firstName = "Charles";
const firstLetter = firstName[0];
```
firstLetter would have a value of the string C.

---

## 29. Understand String Immutability
In JavaScript, String values are `immutable`, which means that they cannot be altered once created.

For example, the following code will produce an error because the letter B in the string Bob cannot be changed to the letter J:
```javascript
let myStr = "Bob";
myStr[0] = "J";
```
Note that this does not mean that myStr could not be re-assigned. The only way to change myStr would be to assign it with a new value, like this:
```javascript
let myStr = "Bob";
myStr = "Job";
```
---

## 30. Use Bracket Notation to Find the Nth Character in a String
You can also use bracket notation to get the character at other positions within a string.

Remember that computers start counting at 0, so the first character is actually the zeroth character.

Example:
```javascript
const firstName = "Ada";
const secondLetterOfFirstName = firstName[1];
```
secondLetterOfFirstName would have a value of the string d.

---

## 31 . Use Bracket Notation to Find the Last Character in a String
In order to get the last letter of a string, you can subtract one from the string's length.

For example, if const firstName = "Ada", you can get the value of the last letter of the string by using firstName[firstName.length - 1].

Example:
```javascript
const firstName = "Ada";
const lastLetter = firstName[firstName.length - 1];
```
lastLetter would have a value of the string a.

---

## 32. Use Bracket Notation to Find the Nth-to-Last Character in a String
You can use the same principle we just used to retrieve the last character in a string to retrieve the Nth-to-last character.

For example, you can get the value of the third-to-last letter of the const firstName = "Augusta" string by using firstName[firstName.length - 3]

Example:
```javascript
const firstName = "Augusta";
const thirdToLastLetter = firstName[firstName.length - 3];
```
thirdToLastLetter would have a value of the string s.

---

## 33. Word Blanks
You are provided sentences with some missing words, like nouns, verbs, adjectives and adverbs. You then fill in the missing pieces with words of your choice in a way that the completed sentence makes sense.

Consider this sentence:
```
It was really ____, and we ____ ourselves ____.
```
This sentence has three missing pieces- an adjective, a verb and an adverb, and we can add words of our choice to complete it. We can then assign the completed sentence to a variable as follows:
```javascript
const sentence = "It was really " + "hot" + ", and we " + "laughed" + " ourselves " + "silly" + ".";
```

