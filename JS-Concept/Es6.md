## ES6 Javacript

>ES6, also known as ECMAScript 2015, is a significant update to the JavaScript language standard. It introduced many new features and improvements to JavaScript, enhancing its capabilities and making it more expressive and efficient for developers.
>
#### Key Features Introduced in ES6:
##### 1. let and const Declarations:
let and const introduced block-scoped variable declarations, replacing the older var.
```javascript 
let count = 10;
count = 20; // Valid reassignment
console.log(count); 
// Using const
const PI = 3.14;
console.log(PI); 
```

##### 2. Arrow Functions:
Arrow functions provide a more concise syntax for writing function expressions.
```javascript 
// Traditional function expression
const square = function(num) {
    return num * num;
};
// Arrow function with implicit return
const square = num => num * num;
console.log(square(4)); 
```

##### 3. Template Literals:
Template literals offer a new way to create strings with embedded expressions.
```javascript 
const name = "Alice";
const greeting = `hello ${name}`
```

##### 4. Enhanced Object Literals:
Object literals gained shorthand syntax for defining methods and computed property names.

> You can omit the function keyword and the colon (:) when defining methods inside objects.
```javascript 
// ES5
var obj = {
    method: function() {
        return 'Hello';
    }
};
// ES6 Enhanced Object Literal
const obj = {
    method() {
        return 'Hello';
    }
};
```
> When the property name in an object literal is the same as the variable name being assigned as its value, you can omit the duplicate declaration.
```javascript 
const name = 'Alice';
const age = 30;
// ES5
var person = {
    name: name,
    age: age
};
// ES6 Enhanced Object Literal
const person = {
    name,
    age
};
```
> You can use expressions and variables to compute property names within object literals.
> This allows for more flexibility in defining object properties based on dynamic values.
```javascript 
const dynamicKey = 'propertyName';
// ES5
var obj = {};
obj[dynamicKey] = 'value';
// ES6 Enhanced Object Literal
const obj = {
    [dynamicKey]: 'value'
};
```

##### 5. Destructuring Assignment:
>Destructuring assignment allows for extracting values from arrays or objects into distinct variables.
```javascript 
// Array destructuring
const [first, second] = [1, 2, 3, 4];
console.log(first); // Output: 1
console.log(second); // Output: 2
// Object destructuring
const person = { name: 'John', age: 30 };
const { name, age } = person;
console.log(name); // Output: John
console.log(age); // Output: 30
```

##### 6. Modules:
> ES6 introduced a standardized module format with import and export statements for better code organization and reusability. 
```javascript 
// Exporting module
// math.js
export const add = (a, b) => a + b;
// Importing module
// app.js
import { add } from './math.js';
console.log(add(5, 3)); // Output: 8
```

##### 7. Classes:
>Classes were introduced as syntactical sugar over JavaScript's existing prototype-based inheritance, making it easier to define and inherit from classes.
```javascript 
// ES6 Class syntax
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
}

// Creating instances
const john = new Person('John', 30);
const jane = new Person('Jane', 25);

console.log(john.greet()); 
console.log(jane.greet()); 


//before ES6 we are using constructor function like this:
// Constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
}

// Method added to prototype
Person.prototype.greet = function() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
};

// Creating instances
const john = new Person('John', 30);
const jane = new Person('Jane', 25);

console.log(john.greet()); 
console.log(jane.greet());
```

##### 8. Promises:
>Promises provide a cleaner way to work with asynchronous code compared to callbacks.
```javascript
// Promise example
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve('Data fetched successfully');
        }, 2000);
    });
};
fetchData()
    .then(data => console.log(data)) 
    .catch(error => console.error(error));
```

##### 9. Default Parameters:
>unctions can have default parameter values.
```javascript
const greet = (name = 'Guest') => {
    console.log(`Hello, ${name}!`);
};
greet(); // Output: Hello, Guest!
greet('Alice'); // Output: Hello, Alice!
```

##### 10. Spread and Rest Operators:
>Spread (...) and rest (...) operators provide a convenient way to work with arrays and function arguments.
```javascript
// Spread operator (arrays)
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // Output: [1, 2, 3, 4, 5]

// Rest parameter (functions)
const sum = (...nums) => {
    return nums.reduce((acc, num) => acc + num, 0);
};
console.log(sum(1, 2, 3, 4, 5)); // Output: 15
```

##### 11.  for...of Loop
>The for...of loop iterates over iterable objects like arrays.
```javascript
const arr = [1, 2, 3];
for (const num of arr) {
    console.log(num); // Output: 1 2 3
}
```

##### 12.  for...of Loop
>The for...of loop iterates over iterable objects like arrays.
```javascript
const arr = [1, 2, 3];
for (const num of arr) {
    console.log(num); // Output: 1 2 3
}
```

##### 13.  Block-Scoped Functions
>Functions declared within a block are now scoped to that block.

```javascript
{
    function blockScopedFunction() {
        return 'Scoped to this block';
    }
    console.log(blockScopedFunction()); // Output: Scoped to this block
}
console.log(blockScopedFunction()); // Error: blockScopedFunction is not defined
```

##### 14.  symbols
>Symbols are a new primitive type, often used as unique object property keys.
```javascript
const sym = Symbol('description');
const obj = {
    [sym]: 'value'
};
console.log(obj[sym]); // Output: value
```

##### 15.  Map and set
>New collections Map and Set provide more powerful data structures.
```javascript
const sym = Symbol('description');
const obj = {
    [sym]: 'value'
};
console.log(obj[sym]); // Output: value
```

##### 16.  Generators
>Generators provide a way to define an iterative algorithm by writing a single function whose execution is not continuous.

```javascript
function* generatorFunction() {
    yield 'Hello';
    yield 'World';
    return '!';
}
const generator = generatorFunction();
console.log(generator.next().value); // Output: Hello
console.log(generator.next().value); // Output: World
console.log(generator.next().value); // Output: !
// we case use generator function in an api call.
```

**Release Timeline:**
>ES6 (ECMAScript 2015) was finalized in June 2015.
>
>It was a major update to the language, following several years after ES5 (ECMAScript 2009).
>ES6 marked a turning point in JavaScript's evolution, introducing many modern features that significantly improved the developer experience and code maintainability.