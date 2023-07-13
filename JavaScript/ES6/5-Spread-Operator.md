# Course - ECMAScript 6
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#es6

---

## 8. Use the Spread Operator to Evaluate Arrays In-Place
ES6 introduces the spread operator, which allows us to expand arrays and other expressions in places where multiple parameters or elements are expected.

The ES5 code below uses apply() to compute the maximum value in an array:
```javascript
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr);
```
maximus would have a value of 89.

We had to use Math.max.apply(null, arr) because Math.max(arr) returns NaN. Math.max() expects comma-separated arguments, but not an array. The spread operator makes this syntax much better to read and maintain.
```javascript
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
```
maximus would have a value of 89.

...arr returns an unpacked array. In other words, it spreads the array. However, the spread operator only works in-place, like in an argument to a function or in an array literal. For example:
```javascript
const spreaded = [...arr];
```
However, the following code will not work:
```javascript
const spreaded = ...arr;
```