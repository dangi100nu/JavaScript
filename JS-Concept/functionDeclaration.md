## In JavaScript, there are several ways to define functions.

##### 1. Function Declaration with name

```javascript
function greet(name) {
  return `hello ${name}`;
}
greet("sonu");
```

##### 2. Anonymous Function Expression

```javascript
// An anonymous function expression defines a function without a name and assigns it to a variable:
2.1 const greet = function (value) {
   return `good ${value}`
}
console.log(greet("morning"))
2.2 const greet = (value) => value * 2;
```

##### 3. Named Function Expression

```javascript
// A named function expression is similar to an anonymous function expression but includes a name, which can be useful for recursion or debugging:
const greet = function greetFunction(value) {
  return `${value}`;
};
console.log(greet("hello world"));
```

##### 4. immediately Invoked Function Expression (IIFE)

```javascript
const person =
  (function (name) {
    return name;
  },
  "sonu");
console.log(person);
```

##### 5. Methods in Object Literals

```javascript
// You can define functions as methods inside object literals:
const person = {
  name: "sonu",
  greet: function (value) {
    return `name:${this.name},${value}`;
  },
};
console.log(person.greet("dangi"));
```

##### 6. Methods in ES6 Classes(Constructor Function)

```javascript
// Classes in ES6 allow you to define methods inside class definitions:
class Person {
  constructor(name) {
    this.name = name;
  }
  greet() {
    return `hello ${this.name}`;
  }
}
const alice = new Person("alice");
console.log(alice.greet());
```
