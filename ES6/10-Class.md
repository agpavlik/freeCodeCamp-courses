# Course - ECMAScript 6
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#es6

---

## 17. Write Concise Declarative Functions with ES6
When defining functions within objects in ES5, we have to use the keyword function as follows:
```javascript
const person = {
  name: "Taylor",
  sayHello: function() {
    return `Hello! My name is ${this.name}.`;
  }
};
```
With ES6, you can remove the function keyword and colon altogether when defining functions in objects. Here's an example of this syntax:
```javascript
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```