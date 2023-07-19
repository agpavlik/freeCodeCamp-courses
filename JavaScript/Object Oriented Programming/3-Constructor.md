# Course - Object Oriented Programming
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming

---

## 5. Define a Constructor Function
`Constructors` are functions that create new objects. They define properties and behaviors that will belong to the new object. Think of them as a blueprint for the creation of new objects.

Here is an example of a constructor:
```javascript
function Bird() {
  this.name = "Albert";
  this.color = "blue";
  this.numLegs = 2;
}
```
`This constructor` defines a Bird object with properties name, color, and numLegs set to Albert, blue, and 2, respectively. Constructors follow a few conventions:

Constructors are defined with a capitalized name to distinguish them from other functions that are not constructors.
Constructors use the keyword this to set properties of the object they will create. Inside the constructor, this refers to the new object it will create.
Constructors define properties and behaviors instead of returning a value as other functions might.

---

## 6. Use a Constructor to Create Objects
Here's the Bird constructor from the previous challenge:
```javascript
function Bird() {
  this.name = "Albert";
  this.color  = "blue";
  this.numLegs = 2;
}

let blueBird = new Bird();
```
### NOTE: 
`this` inside the constructor always refers to the object being created.

Notice that the new operator is used when calling a constructor. `This` tells JavaScript to create a new instance of Bird called blueBird. Without the new operator, `this` inside the constructor would not point to the newly created object, giving unexpected results. Now blueBird has all the properties defined inside the Bird constructor:
```javascript
blueBird.name;
blueBird.color;
blueBird.numLegs;
```
Just like any other object, its properties can be accessed and modified:
```javascript
blueBird.name = 'Elvira';
blueBird.name;
```
---

## 7. Extend Constructors to Receive Arguments
The Bird and Dog constructors from the last challenge worked well. However, notice that all Birds that are created with the Bird constructor are automatically named Albert, are blue in color, and have two legs. What if you want birds with different values for name and color? It's possible to change the properties of each bird manually but that would be a lot of work:
```javascript
let swan = new Bird();
swan.name = "Carlos";
swan.color = "white";
```
Suppose you were writing a program to keep track of hundreds or even thousands of different birds in an aviary. It would take a lot of time to create all the birds, then change the properties to different values for every one. To more easily create different Bird objects, you can design your Bird constructor to accept parameters:
```javascript
function Bird(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}
```
Then pass in the values as arguments to define each unique bird into the Bird constructor: let cardinal = new Bird("Bruce", "red"); This gives a new instance of Bird with name and color properties set to Bruce and red, respectively. The numLegs property is still set to 2. The cardinal has these properties:
```javascript
cardinal.name
cardinal.color
cardinal.numLegs
```
The constructor is more flexible. It's now possible to define the properties for each Bird at the time it is created, which is one way that JavaScript constructors are so useful. They group objects together based on shared characteristics and behavior and define a blueprint that automates their creation.

---

## 8.Verify an Object's Constructor with instanceof
Anytime a constructor function creates a new object, that object is said to be an instance of its constructor. JavaScript gives a convenient way to verify this with the `instanceof` operator. instanceof allows you to compare an object to a constructor, returning true or false based on whether or not that object was created with the constructor. Here's an example:
```javascript
let Bird = function(name, color) {
  this.name = name;
  this.color = color;
  this.numLegs = 2;
}

let crow = new Bird("Alexis", "black");

crow instanceof Bird;
```
This instanceof method would return true.

If an object is created without using a constructor, instanceof will verify that it is not an instance of that constructor:
```javascript
let canary = {
  name: "Mildred",
  color: "Yellow",
  numLegs: 2
};

canary instanceof Bird;
```
This instanceof method would return false.

---

## 9. Understand Own Properties
In the following example, the Bird constructor defines two properties: name and numLegs:
```javascript
function Bird(name) {
  this.name = name;
  this.numLegs = 2;
}

let duck = new Bird("Donald");
let canary = new Bird("Tweety");
```
name and numLegs are called own properties, because they are defined directly on the instance object. That means that duck and canary each has its own separate copy of these properties. In fact every instance of Bird will have its own copy of these properties. The following code adds all of the own properties of duck to the array ownProps:
```javascript
let ownProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  }
}

console.log(ownProps);
```
The console would display the value ["name", "numLegs"].

---

## 10. Use Prototype Properties to Reduce Duplicate Code
Since numLegs will probably have the same value for all instances of Bird, you essentially have a duplicated variable numLegs inside each Bird instance.

This may not be an issue when there are only two instances, but imagine if there are millions of instances. That would be a lot of duplicated variables.

A better way is to use the prototype of Bird. Properties in the prototype are shared among ALL instances of Bird. Here's how to add numLegs to the Bird prototype:
```
Bird.prototype.numLegs = 2;
```
Now all instances of Bird have the numLegs property.
```
console.log(duck.numLegs);
console.log(canary.numLegs);
```
Since all instances automatically have the properties on the prototype, think of a prototype as a "recipe" for creating objects. Note that the prototype for duck and canary is part of the Bird constructor as Bird.prototype.

---

## 11. Iterate Over All Properties
You have now seen two kinds of properties: own properties and prototype properties. Own properties are defined directly on the object instance itself. And prototype properties are defined on the prototype.
```javascript
function Bird(name) {
  this.name = name;  //own property
}

Bird.prototype.numLegs = 2; // prototype property

let duck = new Bird("Donald");
```
Here is how you add duck's own properties to the array ownProps and prototype properties to the array prototypeProps:
```javascript
let ownProps = [];
let prototypeProps = [];

for (let property in duck) {
  if(duck.hasOwnProperty(property)) {
    ownProps.push(property);
  } else {
    prototypeProps.push(property);
  }
}

console.log(ownProps);
console.log(prototypeProps);
```
console.log(ownProps) would display ["name"] in the console, and console.log(prototypeProps) would display ["numLegs"].

---

## 12. 




































