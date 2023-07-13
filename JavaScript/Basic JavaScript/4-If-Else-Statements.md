# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 54. Use Conditional Logic with If Statements
`if statements` are used to make decisions in code. The keyword if tells JavaScript to execute the code in the curly braces under certain conditions, defined in the parentheses. These conditions are known as `Boolean` conditions and they may only be true or false.

When the condition evaluates to true, the program executes the statement inside the curly braces. When the Boolean condition evaluates to false, the statement inside the curly braces will not execute.
```
Pseudocode

if (condition is true) {
  statement is executed
}
```
Example
```javascript
function test (myCondition) {
  if (myCondition) {
    return "It was true";
  }
  return "It was false";
}

test(true);
test(false);
```
test(true) returns the string It was true, and test(false) returns the string It was false.

When test is called with a value of true, the if statement evaluates myCondition to see if it is true or not. Since it is true, the function returns It was true. When we call test with a value of false, myCondition is not true and the statement in the curly braces is not executed and the function returns It was false.

---

## 55. Comparison with the Equality Operator
There are many comparison operators in JavaScript. All of these operators return a boolean true or false value.

The most basic operator is the `equality operator ==`. The equality operator compares two values and returns true if they're equivalent or false if they are not. Note that equality is different from assignment (=), which assigns the value on the right of the operator to a variable on the left.

```javascript
function equalityTest(myVal) {
  if (myVal == 10) {
    return "Equal";
  }
  return "Not Equal";
}
```
If myVal is equal to 10, the equality operator returns true, so the code in the curly braces will execute, and the function will return Equal. Otherwise, the function will return Not Equal. In order for JavaScript to compare two different data types (for example, numbers and strings), it must convert one type to another. This is known as Type Coercion. Once it does, however, it can compare terms as follows:
```
1   ==  1  // true
1   ==  2  // false
1   == '1' // true
"3" ==  3  // true
```
---

## 56. Comparison with the Strict Equality Operator
`Strict equality (===)` is the counterpart to the equality operator (==). However, unlike the equality operator, which attempts to convert both values being compared to a common type, the strict equality operator does not perform a type conversion.

If the values being compared have different types, they are considered unequal, and the strict equality operator will return false.

Examples
```
3 ===  3  // true
3 === '3' // false
```
In the second example, 3 is a Number type and '3' is a String type.

---

## 57. Practice comparing different values
In the last two challenges, we learned about the equality operator (==) and the strict equality operator (===). Let's do a quick review and practice using these operators some more.

If the values being compared are not of the same type, the equality operator will perform a type conversion, and then evaluate the values. However, the strict equality operator will compare both the data type and value as-is, without converting one type to the other.

Examples
```
3 == '3' returns true because JavaScript performs type conversion from string to number. 
3 === '3' returns false because the types are different and type conversion is not performed.
```
### Note:
In JavaScript, you can determine the type of a variable or a value with the `typeof operator`, as follows:
```
typeof 3
typeof '3'
```
typeof 3 returns the string number, and typeof '3' returns the string string.

---

## 58. Comparison with the Inequality Operator
The `inequality operator (!=)` is the opposite of the equality operator. It means not equal and returns false where equality would return true and vice versa. Like the equality operator, the inequality operator will convert data types of values while comparing.

Examples
```
1 !=  2    // true
1 != "1"   // false
1 != '1'   // false
1 != true  // false
0 != false // false
```
---

## 59. Comparison with the Strict Inequality Operator
The `strict inequality operator (!==)` is the logical opposite of the strict equality operator. It means "Strictly Not Equal" and returns false where strict equality would return true and vice versa. The strict inequality operator will not convert data types.

Examples
```
3 !==  3  // false
3 !== '3' // true
4 !==  3  // true
```
---

## 60. Comparison with the Greater Than Operator
The `greater than operator (>)` compares the values of two numbers. If the number to the left is greater than the number to the right, it returns true. Otherwise, it returns false.

Like the equality operator, the greater than operator will convert data types of values while comparing.

Examples
```
5   >  3  // true
7   > '3' // true
2   >  3  // false
'1' >  9  // false
```
---

## 61. Comparison with the Greater Than Or Equal To Operator
The `greater than or equal to operator (>=)` compares the values of two numbers. If the number to the left is greater than or equal to the number to the right, it returns true. Otherwise, it returns false.

Like the equality operator, the greater than or equal to operator will convert data types while comparing.

Examples
```
6   >=  6  // true
7   >= '3' // true
2   >=  3  // false
'7' >=  9  // false
```
---

## 62. Comparison with the Less Than Operator
The `less than operator (<)` compares the values of two numbers. If the number to the left is less than the number to the right, it returns true. Otherwise, it returns false. Like the equality operator, the less than operator converts data types while comparing.

Examples
```
2   < 5 // true
'3' < 7 // true
5   < 5 // false
3   < 2 // false
'8' < 4 // false
```
---

## 63. Comparison with the Less Than Or Equal To Operator
The `less than or equal to operator (<=)` compares the values of two numbers. If the number to the left is less than or equal to the number to the right, it returns true. If the number on the left is greater than the number on the right, it returns false. Like the equality operator, the less than or equal to operator converts data types.

Examples
```
4   <= 5 // true
'7' <= 7 // true
5   <= 5 // true
3   <= 2 // false
'8' <= 4 // false
```
---

## 64. Comparisons with the Logical And Operator
Sometimes you will need to test more than one thing at a time. The `logical and operator (&&)` returns true if and only if the operands to the left and right of it are true.

The same effect could be achieved by nesting an if statement inside another if.
```
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```
This code will return Yes if num is greater than 5 and less than 10. The same logic can be written with the logical and operator.
```javascript
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```
---

## 65. Comparisons with the Logical Or Operator
The `logical or operator (||)` returns true if either of the operands is true. Otherwise, it returns false.

The logical or operator is composed of two pipe symbols: (||). This can typically be found between your Backspace and Enter keys.

The pattern below should look familiar from prior waypoints.
```
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```
This code will return Yes if num is between 5 and 10 (5 and 10 included). The same logic can be written with the logical or operator.
```javascript
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```
---

## 66. Introducing Else Statements
When a condition for an if statement is true, the block of code following it is executed. What about when that condition is false? Normally nothing would happen. With an `else statement`, an alternate block of code can be executed.
```javascript
if (num > 10) {
  return "Bigger than 10";
} else {
  return "10 or Less";
}
```
---

## 67. Introducing Else If Statements
If you have multiple conditions that need to be addressed, you can chain if statements together with `else if statements`.
```javascript
if (num > 15) {
  return "Bigger than 15";
} else if (num < 5) {
  return "Smaller than 5";
} else {
  return "Between 5 and 15";
}
```
---

## 68. Logical Order in If Else Statements
Order is important in if, else if statements.

The function is executed from top to bottom so you will want to be careful of what statement comes first.

Take these two functions as an example.

Here's the first:
```javascript
function foo(x) {
  if (x < 1) {
    return "Less than one";
  } else if (x < 2) {
    return "Less than two";
  } else {
    return "Greater than or equal to two";
  }
}
```
And the second just switches the order of the statements:
```javascript
function bar(x) {
  if (x < 2) {
    return "Less than two";
  } else if (x < 1) {
    return "Less than one";
  } else {
    return "Greater than or equal to two";
  }
}
```
While these two functions look nearly identical if we pass a number to both we get different outputs.
```
foo(0)
bar(0)
```
foo(0) will return the string Less than one, and bar(0) will return the string Less than two.

---

## 69. Chaining If Else Statements
if/else statements can be chained together for complex logic. Here is pseudocode of multiple chained if / else if statements:
```javascript
if (condition1) {
  statement1
} else if (condition2) {
  statement2
} else if (condition3) {
  statement3
. . .
} else {
  statementN
}
```
---

## 70. Golf Code
>Exercise

In the game of Golf, each hole has a par, meaning, the average number of strokes a golfer is expected to make in order to sink the ball in the hole to complete the play. Depending on how far above or below par your strokes are, there is a different nickname.

Your function will be passed par and strokes arguments. Return the correct string according to this table which lists the strokes in order of priority; top (highest) to bottom (lowest):
```
Strokes	    Return
1	          "Hole-in-one!"
<= par - 2	"Eagle"
par - 1    	"Birdie"
par	        "Par"
par + 1	    "Bogey"
par + 2	    "Double Bogey"
>= par + 3	"Go Home!"
```
par and strokes will always be numeric and positive. We have added an array of all the names for your convenience.
> Answer
```javascript
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
  if (strokes === 1) return "Hole-in-one!";
  else if ((strokes - par) <= -2) return 'Eagle';
  else if ((strokes - par) === -1) return 'Birdie';
  else if (strokes === par) return 'Par';
  else if ((strokes - par) === 1) return 'Bogey';
  else if ((strokes - par) === 2) return 'Double Bogey';
  else return 'Go Home!';
  // Only change code above this line
}
golfScore(5, 4);
```
## 75. Returning Boolean Values from Functions
You may recall from `Comparison with the Equality Operator` that all comparison operators return a boolean true or false value.

Sometimes people use an if/else statement to do a comparison, like this:
```javascript
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
```
But there's a better way to do this. Since === returns true or false, we can return the result of the comparison:
```javascript
function isEqual(a, b) {
  return a === b;
}
```
---

## 76. Return Early Pattern for Functions
When a return statement is reached, the execution of the current function stops and control returns to the calling location.

Example
```javascript
function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye")
}
myFun();
```
The above will display the string Hello in the console, and return the string World. The string byebye will never display in the console, because the function exits at the return statement.



