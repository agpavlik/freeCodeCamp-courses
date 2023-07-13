# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 44. Write Reusable JavaScript with Functions
In JavaScript, we can divide up our code into reusable parts called `functions`.

Here's an example of a function:
```javascript
function functionName() {
  console.log("Hello World");
}
```
You can call or invoke this function by using its name followed by parentheses, like this: functionName(); Each time the function is called it will print out the message Hello World on the dev console. All of the code between the curly braces will be executed every time the function is called.

---

## 45. Passing Values to Functions with Arguments
`Parameters` are variables that act as placeholders for the values that are to be input to a function when it is called. When a function is defined, it is typically defined along with one or more parameters. The actual values that are input (or "passed") into a function when it is called are known as arguments.

Here is a function with two parameters, param1 and param2:
```javascript
function testFun(param1, param2) {
  console.log(param1, param2);
}
```
Then we can call testFun like this: testFun("Hello", "World");. We have passed two string arguments, Hello and World. Inside the function, param1 will equal the string Hello and param2 will equal the string World. Note that you could call testFun again with different arguments and the parameters would take on the value of the new arguments.

---

## 46. Return a Value from a Function with Return
We can pass values into a function with arguments. You can use a return statement to send a value back out of a function.

Example
```javascript
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```
answer has the value 8.

plusThree takes an argument for num and returns a value equal to num + 3.

---

## 47. Global Scope and Functions
In JavaScript, scope refers to the visibility of variables. Variables which are defined outside of a function block have `Global scope`. This means, they can be seen everywhere in your JavaScript code.

Variables which are declared without the let or const keywords are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with let or const.

---

## 48. Local Scope and Functions
Variables which are declared within a function, as well as the function parameters, have `local scope`. That means they are only visible within that function.

Here is a function myTest with a local variable called loc.
```javascript
function myTest() {
  const loc = "foo";
  console.log(loc);
}

myTest();
console.log(loc);
```
The myTest() function call will display the string foo in the console. The console.log(loc) line (outside of the myTest function) will throw an error, as loc is not defined outside of the function.

---

## 49. Global vs. Local Scope in Functions
It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

In this example:
```javascript
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```
The function myFun will return the string Head because the local version of the variable is present.

---

## 50. Understanding Undefined Value returned from a Function
A function can include the return statement but it does not have to. In the case that the function doesn't have a return statement, when you call it, the function processes the inner code but the returned value is undefined.

Example
```javascript
let sum = 0;

function addSum(num) {
  sum = sum + num;
}

addSum(3);
```
addSum is a function without a return statement. The function will change the global sum variable but the returned value of the function is undefined.

---

## 51. Assignment with a Returned Value
If you'll recall from our discussion about `Storing Values with the Assignment Operator`, everything to the right of the equal sign is resolved before the value is assigned. This means we can take the return value of a function and assign it to a variable.

Assume we have defined a function sum which adds two numbers together.
```javascript
ourSum = sum(5, 12);
```
Calling the sum function with the arguments of 5 and 12 produces a return value of 17. This return value is assigned to the ourSum variable.

>Exercise

 Call the processArg function with an argument of 7 and assign its `return` value to
 the variable processed.

```javascript
// Setup
var processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

// Only change code below this line
```

>Answer

```javascript
var processed = 0;

function processArg(num) {
  return (num + 3) / 5;
}

// Only change code below this line

processed = processArg(7);
```
---

## 52. Stand in Line
In Computer Science a `queue` is an abstract Data Structure where items are kept in order. New items can be added at the back of the queue and old items are taken off from the front of the queue.

>Exercise
 - Write a function nextInLine which takes an array (arr) and a number (item) as arguments.
 - Add the number to the end of the array.
 - Then remove the first element of array. The nextInLine function
 should then return the element that was removed.

```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  
  return item;
  // Only change code above this line
}

// Setup
var testArr = [1,2,3,4,5];

// Display Code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

> Answer
```javascript
function nextInLine(arr, item) {

  arr.push(item);
  let removedElement = arr.shift();
  return removedElement;
}

var testArr = [1,2,3,4,5];

console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));

```
---

## 53. Understanding Boolean Values
Another data type is the `Boolean`. Booleans may only be one of two values: true or false. They are basically little on-off switches, where true is on and false is off. These two states are mutually exclusive.

### Note:
Boolean values are never written with quotes. The strings "true" and "false" are not Boolean and have no special meaning in JavaScript.