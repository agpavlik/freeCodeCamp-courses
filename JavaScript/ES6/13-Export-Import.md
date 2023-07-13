# Course - ECMAScript 6
https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#es6

---

## 21. Use export to Share a Code Block
Imagine a file called math_functions.js that contains several functions related to mathematical operations. One of them is stored in a variable, add, that takes in two numbers and returns their sum. You want to use this function in several different JavaScript files. In order to share it with these other files, you first need to export it.
```javascript
export const add = (x, y) => {
  return x + y;
}
```
The above is a common way to export a single function, but you can achieve the same thing like this:
```javascript
const add = (x, y) => {
  return x + y;
}

export { add };
```
When you export a variable or function, you can import it in another file and use it without having to rewrite the code. You can export multiple things by repeating the first example for each thing you want to export, or by placing them all in the export statement of the second example, like this:
```javascript
export { add, subtract };
```

---

## 22. Reuse JavaScript Code Using import
`import` allows you to choose which parts of a file or module to load. In the previous lesson, the examples exported add from the math_functions.js file. Here's how you can import it to use in another file:
```javascript
import { add } from './math_functions.js';
```
Here, import will find add in math_functions.js, import just that function for you to use, and ignore the rest. The ./ tells the import to look for the math_functions.js file in the same folder as the current file. The relative file path (./) and file extension (.js) are required when using import in this way.

You can import more than one item from the file by adding them in the import statement like this:
```javascript
import { add, subtract } from './math_functions.js';
```

---

## 23. Use * to Import Everything from a File
Suppose you have a file and you wish to import all of its contents into the current file. This can be done with the import * as syntax. Here's an example where the contents of a file named math_functions.js are imported into a file in the same directory:
```javascript
import * as myMathModule from "./math_functions.js";
```
The above import statement will create an object called myMathModule. This is just a variable name, you can name it anything. The object will contain all of the exports from math_functions.js in it, so you can access the functions like you would any other object property. Here's how you can use the add and subtract functions that were imported:
```javascript
myMathModule.add(2,3);
myMathModule.subtract(5,3);
```
---

## 24. Create an Export Fallback with export default
In the export lesson, you learned about the syntax referred to as a named export. This allowed you to make multiple functions and variables available for use in other files.

There is another export syntax you need to know, known as export default. Usually you will use this syntax if only one value is being exported from a file. It is also used to create a fallback value for a file or module.

Below are examples using export default:
```javascript
export default function add(x, y) {
  return x + y;
}

export default function(x, y) {
  return x + y;
}
```
The first is a named function, and the second is an anonymous function.

Since export default is used to declare a fallback value for a module or file, you can only have one value be a default export in each module or file. Additionally, you cannot use export default with var, let, or const

---

## 25. Import a Default Export
In the last challenge, you learned about export default and its uses. To import a default export, you need to use a different import syntax. In the following example, add is the default export of the math_functions.js file. Here is how to import it:
```javascript
import add from "./math_functions.js";
```
The syntax differs in one key place. The imported value, add, is not surrounded by curly braces ({}). add here is simply a variable name for whatever the default export of the math_functions.js file is. You can use any name here when importing a default.
