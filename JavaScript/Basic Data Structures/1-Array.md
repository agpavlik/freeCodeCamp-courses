# Course - Basic Data Structures
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-data-structures

---

## 1. Use an Array to Store a Collection of Data
The below is an example of the simplest implementation of an array data structure. This is known as a `one-dimensional array`, meaning it only has one level, or that it does not have any other arrays nested within it. Notice it contains booleans, strings, and numbers, among other valid JavaScript data types:
```javascript
let simpleArray = ['one', 2, 'three', true, false, undefined, null];
console.log(simpleArray.length);
```
The console.log call displays 7.

All arrays have a length property, which as shown above, can be very easily accessed with the syntax Array.length. A more complex implementation of an array can be seen below. This is known as a `multi-dimensional array`, or an array that contains other arrays. Notice that this array also contains JavaScript objects, which we will examine very closely in our next section, but for now, all you need to know is that arrays are also capable of storing complex objects.
```javascript
let complexArray = [
  [
    {
      one: 1,
      two: 2
    },
    {
      three: 3,
      four: 4
    }
  ],
  [
    {
      a: "a",
      b: "b"
    },
    {
      c: "c",
      d: "d"
    }
  ]
];
```
---

## 2. Access an Array's Contents Using Bracket Notation
The fundamental feature of any data structure is, of course, the ability to not only store data, but to be able to retrieve that data on command. So, now that we've learned how to create an array, let's begin to think about how we can access that array's information.

When we define a simple array as seen below, there are 3 items in it:
```javascript
let ourArray = ["a", "b", "c"];
```
In an array, each array item has an index. This index doubles as the position of that item in the array, and how you reference it. However, it is important to note, that JavaScript arrays are zero-indexed, meaning that the first element of an array is actually at the zeroth position, not the first. In order to retrieve an element from an array we can enclose an index in brackets and append it to the end of an array, or more commonly, to a variable which references an array object. This is known as bracket notation. For example, if we want to retrieve the a from ourArray and assign it to a variable, we can do so with the following code:
```javascript
let ourVariable = ourArray[0];
```
Now ourVariable has the value of a.

In addition to accessing the value associated with an index, you can also set an index to a value using the same notation:
```javascript
ourArray[1] = "not b anymore";
```
Using bracket notation, we have now reset the item at index 1 from the string b, to not b anymore. Now ourArray is ["a", "not b anymore", "c"].

---

## 3. Add Items to an Array with push() and unshift()
An array's length, like the data types it can contain, is not fixed. Arrays can be defined with a length of any number of elements, and elements can be added or removed over time; in other words, arrays are mutable. In this challenge, we will look at two methods with which we can programmatically modify an array: `Array.push()` and `Array.unshift()`.

Both methods take one or more elements as parameters and add those elements to the array the method is being called on; `the push()` method adds elements to the end of an array, and `unshift()` adds elements to the beginning. Consider the following:
```javascript
let twentyThree = 'XXIII';
let romanNumerals = ['XXI', 'XXII'];

romanNumerals.unshift('XIX', 'XX');
```
romanNumerals would have the value ['XIX', 'XX', 'XXI', 'XXII'].
```javascript
romanNumerals.push(twentyThree);
```
romanNumerals would have the value ['XIX', 'XX', 'XXI', 'XXII', 'XXIII']. Notice that we can also pass variables, which allows us even greater flexibility in dynamically modifying our array's data.

---

## 4. Remove Items from an Array with pop() and shift()
Both `push()` and `unshift()` have corresponding methods that are nearly functional opposites: `pop()` and `shift()`. As you may have guessed by now, instead of adding, `pop()` removes an element from the end of an array, while `shift()` removes an element from the beginning. The key difference between `pop()` and `shift()` and their cousins `push()` and `unshift()`, is that neither method takes parameters, and each only allows an array to be modified by a single element at a time.

Let's take a look:
```javascript
let greetings = ['whats up?', 'hello', 'see ya!'];

greetings.pop();
```
greetings would have the value ['whats up?', 'hello'].
```javascript
greetings.shift();
```
greetings would have the value ['hello'].
We can also return the value of the removed element with either method like this:
```javascript
let popped = greetings.pop();
```
greetings would have the value [], and popped would have the value hello.

---

## 5. Remove Items Using splice()
Ok, so we've learned how to remove elements from the beginning and end of arrays using `shift()` and `pop()`, but what if we want to remove an element from somewhere in the middle? Or remove more than one element at once? Well, that's where `splice()` comes in. `splice()`` allows us to do just that: remove any number of consecutive elements from anywhere in an array.

`splice()` can take up to 3 parameters, but for now, we'll focus on just the first 2. The first two parameters of `splice()` are integers which represent indexes, or positions, of items in the array that `splice()` is being called upon. And remember, arrays are zero-indexed, so to indicate the first element of an array, we would use 0. splice()'s first parameter represents the index on the array from which to begin removing elements, while the second parameter indicates the number of elements to delete. For example:
```javascript
let array = ['today', 'was', 'not', 'so', 'great'];

array.splice(2, 2);
```
Here we remove 2 elements, beginning with the third element (at index 2). array would have the value ['today', 'was', 'great'].

`splice()` not only modifies the array it's being called on, but it also returns a new array containing the value of the removed elements:
```javascript
let array = ['I', 'am', 'feeling', 'really', 'happy'];

let newArray = array.splice(3, 2);
```
newArray has the value ['really', 'happy'].

> Exercise

We've initialized an array arr. Use splice() to remove elements from arr, so that it only contains elements that sum to the value of 10.
```javascript
const arr = [2, 4, 5, 1, 7, 5, 2, 1];
// Only change code below this line

// Only change code above this line
console.log(arr);
```
> Answer
```javascript
const arr = [2, 4, 5, 1, 7, 5, 2, 1];
// Only change code below this line
arr.splice(1,4)
// Only change code above this line
console.log(arr);
```
---

## 6. Add Items Using splice()
Remember in the last challenge we mentioned that `splice()` can take up to three parameters? Well, you can use the third parameter, comprised of one or more element(s), to add to the array. This can be incredibly useful for quickly switching out an element, or a set of elements, for another.
```javascript
const numbers = [10, 11, 12, 12, 15];
const startIndex = 3;
const amountToDelete = 1;

numbers.splice(startIndex, amountToDelete, 13, 14);
console.log(numbers);
```
The second occurrence of 12 is removed, and we add 13 and 14 at the same index. The numbers array would now be [ 10, 11, 12, 13, 14, 15 ].

Here, we begin with an array of numbers. Then, we pass the following to splice(): The index at which to begin deleting elements (3), the number of elements to be deleted (1), and the remaining arguments (13, 14) will be inserted starting at that same index. Note that there can be any number of elements (separated by commas) following amountToDelete, each of which gets inserted.

---

## 7. Copy Array Items Using slice()
The next method we will cover is `slice()`. Rather than modifying an array, `slice()` copies or extracts a given number of elements to a new array, leaving the array it is called `upon untouched`. `slice()` takes only 2 parameters — the first is the index at which to begin extraction, and the second is the index at which to stop extraction (extraction will occur up to, but not including the element at this index). Consider this:
```javascript
let weatherConditions = ['rain', 'snow', 'sleet', 'hail', 'clear'];

let todaysWeather = weatherConditions.slice(1, 3);
```
todaysWeather would have the value ['snow', 'sleet'], while weatherConditions would still have ['rain', 'snow', 'sleet', 'hail', 'clear'].

In effect, we have created a new array by extracting elements from an existing array.

---

## 8. Copy an Array with the Spread Operator
While `slice()` allows us to be selective about what elements of an array to copy, among several other useful tasks, ES6's new `spread operator` allows us to easily copy all of an array's elements, in order, with a simple and highly readable syntax. The spread syntax simply looks like this: `...`

In practice, we can use the spread operator to copy an array like so:
```javascript
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
```
thatArray equals [true, true, undefined, false, null]. thisArray remains unchanged and thatArray contains the same elements as thisArray.

> Exercise

We have defined a function, copyMachine which takes arr (an array) and num (a number) as arguments. The function is supposed to return a new array made up of num copies of arr. We have done most of the work for you, but it doesn't work quite right yet. Modify the function using spread syntax so that it works correctly (hint: another method we have already covered might come in handy here!).
```javascript
function copyMachine(arr, num) {
  let newArr = [];
  while (num >= 1) {
    // Only change code below this line

    // Only change code above this line
    num--;
  }
  return newArr;
}

console.log(copyMachine([true, false, true], 2));
```

> Answer
``` javascript
function copyMachine(arr, num) {
  let newArr = [];
  while (num >= 1) {
    // Only change code below this line
    newArr.push([...arr]);
    // Only change code above this line
    num--;
  }
  return newArr;
}

console.log(copyMachine([true, false, true], 2));
```
---

## 9. Combine Arrays with the Spread Operator
Another huge advantage of the spread operator is the ability to combine arrays, or to insert all the elements of one array into another, at any index. With more traditional syntaxes, we can concatenate arrays, but this only allows us to combine arrays at the end of one, and at the start of another. Spread syntax makes the following operation extremely simple:
```javascript
let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];

let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
```
thatArray would have the value ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander'].

Using spread syntax, we have just achieved an operation that would have been more complex and more verbose had we used traditional methods.

---

## 10. Check For The Presence of an Element With indexOf()
Since arrays can be changed, or mutated, at any time, there's no guarantee about where a particular piece of data will be on a given array, or if that element even still exists. Luckily, JavaScript provides us with another built-in method, `indexOf()`, that allows us to quickly and easily check for the presence of an element on an array. `indexOf()` takes an element as a parameter, and when called, it returns the position, or index, of that element, or -1 if the element does not exist on the array.

For example:
```javascript
let fruits = ['apples', 'pears', 'oranges', 'peaches', 'pears'];

fruits.indexOf('dates');
fruits.indexOf('oranges');
fruits.indexOf('pears');
```
indexOf('dates') returns -1, indexOf('oranges') returns 2, and indexOf('pears') returns 1 (the first index at which each element exists).

> Exercise

indexOf() can be incredibly useful for quickly checking for the presence of an element on an array. We have defined a function, quickCheck, that takes an array and an element as arguments. Modify the function using indexOf() so that it returns true if the passed element exists on the array, and false if it does not.

```javascript
function quickCheck(arr, elem) {
  // Only change code below this line

  // Only change code above this line
}

console.log(quickCheck(['squash', 'onions', 'shallots'], 'mushrooms'));
```

> Answer
```javascript
function quickCheck(arr, elem) {
  if (arr.indexOf(elem) === -1) {
    return false
  }
  return true
}
console.log(quickCheck(['squash', 'onions', 'shallots'], 'mushrooms'));
```
---

## 11. Iterate Through All an Array's Items Using For Loops
Sometimes when working with arrays, it is very handy to be able to iterate through each item to find one or more elements that we might need, or to manipulate an array based on which data items meet a certain set of criteria. JavaScript offers several built in methods that each iterate over arrays in slightly different ways to achieve different results (such as `every()`, `forEach()`, `map()`, etc.), however the technique which is most flexible and offers us the greatest amount of control is a simple `for loop`.

Consider the following:
```javascript
function greaterThanTen(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 10) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

greaterThanTen([2, 12, 8, 14, 80, 0, 1]);
```
Using a for loop, this function iterates through and accesses each element of the array, and subjects it to a simple test that we have created. In this way, we have easily and programmatically determined which data items are greater than 10, and returned a new array, [12, 14, 80], containing those items.

>Exercise

We have defined a function, filteredArray, which takes arr, a nested array, and elem as arguments, and returns a new array. elem represents an element that may or may not be present on one or more of the arrays nested within arr. Modify the function, using a for loop, to return a filtered version of the passed array such that any array nested within arr containing elem has been removed.

```javascript
function filteredArray(arr, elem) {
  let newArr = [];
  // Only change code below this line

  // Only change code above this line
  return newArr;
}

console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));
```
> Answer
```javascript
function filteredArray(arr, elem) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i].indexOf(elem) === -1) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));
```
---

## 12. Create complex multi-dimensional arrays
Awesome! You have just learned a ton about arrays! This has been a fairly high level overview, and there is plenty more to learn about working with arrays, much of which you will see in later sections. But before moving on to looking at Objects, let's take one more look, and see how arrays can become a bit more complex than what we have seen in previous challenges.

One of the most powerful features when thinking of arrays as data structures, is that arrays can contain, or even be completely made up of other arrays. We have seen arrays that contain arrays in previous challenges, but fairly simple ones. However, arrays can contain an infinite depth of arrays that can contain other arrays, each with their own arbitrary levels of depth, and so on. In this way, an array can very quickly become a very complex data structure, known as a `multi-dimensional`, or `nested array`. Consider the following example:
```javascript
let nestedArray = [
  ['deep'],
  [
    ['deeper'], ['deeper'] 
  ],
  [
    [
      ['deepest'], ['deepest']
    ],
    [
      [
        ['deepest-est?']
      ]
    ]
  ]
];
```
The deep array is nested 2 levels deep. The deeper arrays are 3 levels deep. The deepest arrays are 4 levels, and the deepest-est? is 5.

While this example may seem convoluted, this level of complexity is not unheard of, or even unusual, when dealing with large amounts of data. However, we can still very easily access the deepest levels of an array this complex with bracket notation:
```javascript
console.log(nestedArray[2][1][0][0][0]);
```
This logs the string deepest-est?. And now that we know where that piece of data is, we can reset it if we need to:
```javascript
nestedArray[2][1][0][0][0] = 'deeper still';
console.log(nestedArray[2][1][0][0][0]);
```
Now it logs deeper still.