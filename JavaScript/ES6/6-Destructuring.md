# Course - ECMAScript 6
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#es6

---

## 9. Use Destructuring Assignment to Extract Values from Objects
`Destructuring assignment` is special syntax introduced in ES6, for neatly assigning values taken directly from an object.

Consider the following ES5 code:
```javascript
const user = { name: 'John Doe', age: 34 };

const name = user.name;
const age = user.age;
```
name would have a value of the string John Doe, and age would have the number 34.

Here's an equivalent assignment statement using the ES6 destructuring syntax:
```javascript
const { name, age } = user;
```
Again, name would have a value of the string John Doe, and age would have the number 34.

Here, the name and age variables will be created and assigned the values of their respective values from the user object. You can see how much cleaner this is.

You can extract as many or few values from the object as you want.

---

## 10. Use Destructuring Assignment to Assign Variables from Objects
Destructuring allows you to assign a new variable name when extracting values. You can do this by putting the new name after a colon when assigning the value.

Using the same object from the last example:
```javascript
const user = { name: 'John Doe', age: 34 };
```
Here's how you can give new variable names in the assignment:
```javascript
const { name: userName, age: userAge } = user;
```
You may read it as "get the value of user.name and assign it to a new variable named userName" and so on. The value of userName would be the string John Doe, and the value of userAge would be the number 34.

---

## 11. Use Destructuring Assignment to Assign Variables from Nested Objects
You can use the same principles from the previous two lessons to destructure values from nested objects.

Using an object similar to previous examples:
```javascript
const user = {
  johnDoe: { 
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```
Here's how to extract the values of object properties and assign them to variables with the same name:
```javascript
const { johnDoe: { age, email }} = user;
```
And here's how you can assign an object properties' values to variables with different names:
```javascript
const { johnDoe: { age: userAge, email: userEmail }} = user;
```
---

## 12. Use Destructuring Assignment to Assign Variables from Arrays
ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:
```javascript
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b);
```
The console will display the values of a and b as 1, 2.

The variable a is assigned the first value of the array, and b is assigned the second value of the array. We can also access the value at any index in an array with destructuring by using commas to reach the desired index:
```javascript
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c);
```
The console will display the values of a, b, and c as 1, 2, 5.

---

## 13. Destructuring via rest elements
In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.

The result is similar to Array.prototype.slice(), as shown below:
```javascript
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b);
console.log(arr);
```
The console would display the values 1, 2 and [3, 4, 5, 7].

Variables a and b take the first and second values from the array. After that, because of the rest syntax presence, arr gets the rest of the values in the form of an array. The rest element only works correctly as the last variable in the list. As in, you cannot use the rest syntax to catch a subarray that leaves out the last element of the original array.

---

## 14. Use Destructuring Assignment to Pass an Object as a Function's Parameters
In some cases, you can destructure the object in a function argument itself.

Consider the code below:
```javascript
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
}
```
This effectively destructures the object sent into the function. This can also be done in-place:
```javascript
const profileUpdate = ({ name, age, nationality, location }) => {
}
```
When profileData is passed to the above function, the values are destructured from the function parameter for use within the function.
