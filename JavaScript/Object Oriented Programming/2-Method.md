# Course - Object Oriented Programming
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#object-oriented-programming

---

## 3. Create a Method on an Object
Objects can have a special type of property, called a `method`.

`Methods` are properties that are functions. This adds different behavior to an object. Here is the duck example with a method:
```javascript
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + duck.name + ".";}
};
duck.sayName();
```
The example adds the sayName method, which is a function that returns a sentence giving the name of the duck. Notice that the method accessed the name property in the return statement using duck.name. The next challenge will cover another way to do this.

---

## 4. Make Code More Reusable with the this Keyword
The last challenge introduced a `method` to the duck object. It used duck.name dot notation to access the value for the name property within the return statement:
```javascript
sayName: function() {return "The name of this duck is " + duck.name + ".";}
```
While this is a valid way to access the object's property, there is a pitfall here. If the variable name changes, any code referencing the original name would need to be updated as well. In a short object definition, it isn't a problem, but if an object has many references to its properties there is a greater chance for error.

A way to avoid these issues is with the `this` keyword:
```javascript
let duck = {
  name: "Aflac",
  numLegs: 2,
  sayName: function() {return "The name of this duck is " + this.name + ".";}
};
```
`this` is a deep topic, and the above example is only one way to use it. In the current context, `this` refers to the object that the method is associated with: duck. If the object's name is changed to mallard, it is not necessary to find all the references to duck in the code. It makes the code reusable and easier to read.
