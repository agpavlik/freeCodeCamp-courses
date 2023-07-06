# Course - Basic JavaScript
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-javascript

---

## 78. Build JavaScript Objects
You may have heard the term object before.

`Objects` are similar to arrays, except that instead of using indexes to access and modify their data, you access the data in objects through what are called properties.

Objects are useful for storing data in a structured way, and can represent real world objects, like a cat.

Here's a sample cat object:
```javascript
const cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```
In this example, all the properties are stored as strings, such as name, legs, and tails. However, you can also use numbers as properties. You can even omit the quotes for single-word string properties, as follows:
```javascript
const anotherObject = {
  make: "Ford",
  5: "five",
  "model": "focus"
};
```
However, if your object has any non-string properties, JavaScript will automatically typecast them as strings.

---

## 79. Accessing Object Properties with Dot Notation
There are two ways to access the properties of an object: `dot notation (.)` and `bracket notation ([])`, similar to an array.

Dot notation is what you use when you know the name of the property you're trying to access ahead of time.

Here is a sample of using `dot notation (.)` to read an object's property:
```javascript
const myObj = {
  prop1: "val1",
  prop2: "val2"
};

const prop1val = myObj.prop1;
const prop2val = myObj.prop2;
```
prop1val would have a value of the string val1, and prop2val would have a value of the string val2.

---

## 80. Accessing Object Properties with Bracket Notation
The second way to access the properties of an object is bracket notation ([]). If the property of the object you are trying to access has a space in its name, you will need to use bracket notation.

However, you can still use bracket notation on object properties without spaces.

Here is a sample of using `bracket notation` to read an object's property:
```javascript
const myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};

myObj["Space Name"];
myObj['More Space'];
myObj["NoSpace"];
```
myObj["Space Name"] would be the string Kirk, myObj['More Space'] would be the string Spock, and myObj["NoSpace"] would be the string USS Enterprise.

Note that property names with spaces in them must be in quotes (single or double).

---

## 81. Accessing Object Properties with Variables
Another use of bracket notation on objects is to access a property which is stored as the value of a variable. This can be very useful for iterating through an object's properties or when accessing a lookup table.

Here is an example of using a variable to access a property:
```javascript
const dogs = {
  Fido: "Mutt",
  Hunter: "Doberman",
  Snoopie: "Beagle"
};

const myDog = "Hunter";
const myBreed = dogs[myDog];
console.log(myBreed);
```
The string Doberman would be displayed in the console.

Note that we do not use quotes around the variable name when using it to access the property because we are using the value of the variable, not the name.

---

## 82. Updating Object Properties
After you've created a JavaScript object, you can update its properties at any time just like you would update any other variable. You can use either dot or bracket notation to update.

For example, let's look at ourDog:
```javascript
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
```
Since he's a particularly happy dog, let's change his name to the string Happy Camper. Here's how we update his object's name property: 
```javascript
ourDog.name = "Happy Camper";
```
or 
```javascript
ourDog["name"] = "Happy Camper";
```
Now when we evaluate ourDog.name, instead of getting Camper, we'll get his new name, Happy Camper.

---

## 83. Add New Properties to a JavaScript Object
You can add new properties to existing JavaScript objects the same way you would modify them.

Here's how we would add a bark property to ourDog:
```javascript
ourDog.bark = "bow-wow";
```
or
```javascript
ourDog["bark"] = "bow-wow";
```
Now when we evaluate ourDog.bark, we'll get his bark, bow-wow.

Example:
```javascript
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};

ourDog.bark = "bow-wow";
```
---

## 84. Delete Properties from a JavaScript Object
We can also delete properties from objects like this:
```
delete ourDog.bark;
```
Example:
```javascript
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};

delete ourDog.bark;
```
After the last line shown above, ourDog looks like:
```javascript
{
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
}
```
---

## 85. Using Objects for Lookups
Objects can be thought of as a key/value storage, like a dictionary. If you have tabular data, you can use an object to lookup values rather than a switch statement or an if/else chain. This is most useful when you know that your input data is limited to a certain range.

Here is an example of an article object:
```javascript
const article = {
  "title": "How to create objects in JavaScript",
  "link": "https://www.freecodecamp.org/news/",
  "author": "Kaashan Hussain",
  "language": "JavaScript",
  "tags": "TECHNOLOGY",
  "createdAt": "NOVEMBER 28, 2018"
};

const articleAuthor = article["author"];
const articleLink = article["link"];

const value = "title";
const valueLookup = article[value];
```
articleAuthor is the string Kaashan Hussain, articleLink is the string https://www.freecodecamp.org/news/, and valueLookup is the string How to create objects in JavaScript.

---

## 86. Testing Objects for Properties
To check if a property on a given object exists or not, you can use the `.hasOwnProperty() method`. someObject.hasOwnProperty(someProperty) returns true or false depending on if the property is found on the object or not.

Example
```javascript
function checkForProperty(object, property) {
  return object.hasOwnProperty(property);
}
checkForProperty({ top: 'hat', bottom: 'pants' }, 'top'); // true
checkForProperty({ top: 'hat', bottom: 'pants' }, 'middle'); // false
```
The first checkForProperty function call returns true, while the second returns false.

>Exercise

Modify the function checkObj to test if the object passed to the function parameter obj contains the specific property passed to the function parameter checkProp. If the property passed to checkProp is found on obj, return that property's value. If not, return Not Found.

```javascript
function checkObj(obj, checkProp) {
  // Only change code below this line
  return "Change Me!";
  // Only change code above this line
}

checkObj({gift: "pony", pet: "kitten", bed: "sleigh"}, "gift")
checkObj({gift: "pony", pet: "kitten", bed: "sleigh"}, "pet")
```
>Answer
```javascript
function checkObj(obj, checkProp) {
  if (obj.hasOwnProperty(checkProp)) return obj[checkProp];
  return "Not Found";
}
``` 




















