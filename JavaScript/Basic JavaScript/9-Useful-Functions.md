# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 100. Generate Random Fractions with JavaScript
Random numbers are useful for creating random behavior.

JavaScript has a `Math.random()` function that generates a random decimal number between 0 (inclusive) and 1 (exclusive). Thus Math.random() can return a 0 but never return a 1.

### Note:
Like Storing Values with the Assignment Operator, all function calls will be resolved before the return executes, so we can return the value of the Math.random() function.

---

## 101. Generate Random Whole Numbers with JavaScript
You can generate random decimal numbers with Math.random(), but sometimes you need to generate random whole numbers. The following process will give you a random whole number less than 20:

Use Math.random() to generate a random decimal number.
Multiply that random decimal number by 20.
Use `Math.floor()` to round this number down to its nearest whole number.
Remember that Math.random() can never quite return a 1, so it's impossible to actually get 20 since you are rounding down with Math.floor(). This process will give you a random whole number in the range from 0 to 19.

Putting everything together, this is what your code looks like:
```
Math.floor(Math.random() * 20);
```
You are calling Math.random(), multiplying the result by 20, then passing the value to Math.floor() to round the value down to the nearest whole number.

---

## 102. Generate Random Whole Numbers within a Range
You can generate a random whole number in the range from zero to a given number. You can also pick a different lower number for this range.

You'll call your minimum number min and your maximum number max.

This formula gives a random whole number in the range from min to max. Take a moment to read it and try to understand what this code is doing:
```
Math.floor(Math.random() * (max - min + 1)) + min
```
---

## 103. Use the parseInt Function
The `parseInt()` function parses a string and returns an integer. Here's an example:
```
const a = parseInt("007");
```
The above function converts the string 007 to the integer 7. If the first character in the string can't be converted into a number, then it returns NaN.

---

## 104.  Use the parseInt Function with a Radix
The parseInt() function parses a string and returns an integer. It takes a second argument for the `radix`, which specifies the base of the number in the string. The radix can be an integer between 2 and 36.

The function call looks like:
```
parseInt(string, radix);
```
And here's an example:
```
const a = parseInt("11", 2);
```
The radix variable says that 11 is in the binary system, or base 2. This example converts the string 11 to an integer 3.

---

## 105. Use the Conditional (Ternary) Operator
The conditional operator, also called the `ternary operator`, can be used as a one line if-else expression.

The syntax is `a ? b : c`, where a is the condition, b is the code to run when the condition returns true, and c is the code to run when the condition returns false.

The following function uses an if/else statement to check a condition:
```javascript
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater or equal";
  }
}
```
This can be re-written using the conditional operator:
```javascript
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
}
```
---

## 106. Use Multiple Conditional (Ternary) Operators
In the previous challenge, you used a single conditional operator. You can also chain them together to check for multiple conditions.

The following function uses if, else if, and else statements to check multiple conditions:
```javascript
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
```
The above function can be re-written using multiple conditional operators:
```javascript
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" 
    : (a > b) ? "a is greater" 
    : "b is greater";
}
```
It is considered best practice to format multiple conditional operators such that each condition is on a separate line, as shown above. Using multiple conditional operators without proper indentation may make your code hard to read. 
For example:
```javascript
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
}
```
---

## 107. Use Recursion to Create a Countdown
In a previous challenge, you learned how to use recursion to replace a for loop. Now, let's look at a more complex function that returns an array of consecutive integers starting with 1 through the number passed to the function.

As mentioned in the previous challenge, there will be a base case. The base case tells the recursive function when it no longer needs to call itself. It is a simple case where the return value is already known. There will also be a `recursive call` which executes the original function with different arguments. If the function is written correctly, eventually the base case will be reached.

For example, say you want to write a recursive function that returns an array containing the numbers 1 through n. This function will need to accept an argument, n, representing the final number. Then it will need to call itself with progressively smaller values of n until it reaches 1. You could write the function as follows:
```javascript
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5));
```
The value [1, 2, 3, 4, 5] will be displayed in the console.

At first, this seems counterintuitive since the value of n decreases, but the values in the final array are increasing. This happens because the push happens last, after the recursive call has returned. At the point where n is pushed into the array, countup(n - 1) has already been evaluated and returned [1, 2, ..., n - 1].

>Exercise

We have defined a function called countdown with one parameter (n). The function should use recursion to return an array containing the integers n through 1 based on the n parameter. If the function is called with a number less than 1, the function should return an empty array. For example, calling this function with n = 5 should return the array [5, 4, 3, 2, 1]. Your function must use recursion by calling itself and must not use loops of any kind.

>Answer
```javascript
function countdown(n){
  if (n < 1) {
    return [];
  } else {
    const countArray = countdown(n - 1);
    countArray.unshift(n);
    return countArray;
  }
}
```
---

## 108. Use Recursion to Create a Range of Numbers
Continuing from the previous challenge, we provide you another opportunity to create a recursive function to solve a problem.

>Exersize
We have defined a function named rangeOfNumbers with two parameters. The function should return an array of integers which begins with a number represented by the startNum parameter and ends with a number represented by the endNum parameter. The starting number will always be less than or equal to the ending number. Your function must use recursion by calling itself and not use loops of any kind. It should also work for cases where both startNum and endNum are the same.

>Answer
```javascript
function rangeOfNumbers(startNum, endNum) {
  if(endNum - startNum === 0){
    return [startNum];
  } else {
    let numbers = rangeOfNumbers(startNum, endNum - 1);
    numbers.push(endNum);
    return numbers;
  }
};
```