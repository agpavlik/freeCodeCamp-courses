# Course - Basic JavaScript

https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#debugging

---

## 1. Use the JavaScript Console to Check the Value of a Variable
Both Chrome and Firefox have excellent JavaScript consoles, also known as DevTools, for debugging your JavaScript.

You can find Developer tools in your Chrome's menu or Web Console in Firefox's menu. If you're using a different browser, or a mobile phone, we strongly recommend switching to desktop Firefox or Chrome.

The console.log() method, which "prints" the output of what's within its parentheses to the console, will likely be the most helpful debugging tool. Placing it at strategic points in your code can show you the intermediate values of variables. It's good practice to have an idea of what the output should be before looking at what it is. Having check points to see the status of your calculations throughout your code will help narrow down where the problem is.

Here's an example to print the string Hello world! to the console:
```
console.log('Hello world!');
```
---

## 2. Understanding the Differences between the freeCodeCamp and Browser Console
You may have noticed that some freeCodeCamp challenges include their own console. This console behaves a little differently than the browser console.

There are many methods to use with `console` to output messages. `log`, `warn`, and `clear` to name a few. The freeCodeCamp console will only output log messages, while the browser console will output all messages. When you make changes to your code, it will automatically run and show the logs. The freeCodeCamp console is then cleared each time your code runs.

---

## 3. Use typeof to Check the Type of a Variable
You can use `typeof` to check the data structure, or type, of a variable. This is useful in debugging when working with multiple data types. If you think you're adding two numbers, but one is actually a string, the results can be unexpected. Type errors can lurk in calculations or function calls. Be careful especially when you're accessing and working with external data in the form of a `JavaScript Object Notation (JSON)` object.

Here are some examples using typeof:
```
console.log(typeof "");
console.log(typeof 0);
console.log(typeof []);
console.log(typeof {});
```
In order, the console will display the strings string, number, object, and object.

JavaScript recognizes seven primitive (immutable) data types: `Boolean, Null, Undefined, Number, String, Symbol` (new with ES6), and `BigInt` (new with ES2020), and one type for mutable items: `Object`. Note that in JavaScript, arrays are technically a type of object.

---

## 4. Catch Misspelled Variable and Function Names
The console.log() and typeof methods are the two primary ways to check intermediate values and types of program output. Now it's time to get into the common forms that bugs take. One syntax-level issue that fast typers can commiserate with is the humble spelling error.

Transposed, missing, or mis-capitalized characters in a variable or function name will have the browser looking for an object that doesn't exist - and complain in the form of a reference error. JavaScript variable and function names are case-sensitive.

---

## 5. Catch Unclosed Parentheses, Brackets, Braces and Quotes
Another syntax error to be aware of is that all opening parentheses, brackets, curly braces, and quotes have a closing pair. Forgetting a piece tends to happen when you're editing existing code and inserting items with one of the pair types. Also, take care when nesting code blocks into others, such as adding a callback function as an argument to a method.

One way to avoid this mistake is as soon as the opening character is typed, immediately include the closing match, then move the cursor back between them and continue coding. Fortunately, most modern code editors generate the second half of the pair automatically.

---

## 6. Catch Mixed Usage of Single and Double Quotes
JavaScript allows the use of both single `(')` and double `(")` quotes to declare a string. Deciding which one to use generally comes down to personal preference, with some exceptions.

Having two choices is great when a string has contractions or another piece of text that's in quotes. Just be careful that you don't close the string too early, which causes a syntax error.

Here are some examples of mixing quotes:
```javascript
const grouchoContraction = "I've had a perfectly wonderful evening, but this wasn't it.";
const quoteInString = "Groucho Marx once said 'Quote me as saying I was mis-quoted.'";
const uhOhGroucho = 'I've had a perfectly wonderful evening, but this wasn't it.';
```
The first two are correct, but the third is incorrect.

Of course, it is okay to use only one style of quotes. You can escape the quotes inside the string by using the backslash (\) escape character:
```javascript
const allSameQuotes = 'I\'ve had a perfectly wonderful evening, but this wasn\'t it.';
```
---

## 7. 