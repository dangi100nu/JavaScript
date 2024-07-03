## Pure Functions in JavaScript.

##### A Pure Function is a function (a block of code) that always returns the same result if the same arguments are passed. It does not depend on any state or data change during a program’s execution. Rather, it only depends on its input arguments.

##### Also, a pure function does not produce any observable side effects such as network requests or data mutation, etc.

#### JavaScript Pure Function example:
##### examples : addition function, square function, array mapping function, filtering, string Concatenation, factorial function.
```javascript
1. function add(a,b){
    return a+b
}

2. function arrayMapping (arr) {
    return arr.map(ele => ele*2)
}

3. function filterEvenNumbers(arr) {
  return arr.filter(num => num % 2 === 0);
}

4. function factorial(n) {
  if (n === 0) {
    return 1;
  }
  return n * factorial(n - 1);
}

5. function concatenateStrings(str1, str2) {
  return str1 + str2;
}
```

#### JavaScript ImPure Function example:
##### Modifying External State, Random Number Generator, Fetching Data from an API, Date and Time Function.
```javascript
1. let count = 0;
function increment() {
  count += 1;
  return count;
}
console.log(increment());

2. function generateRandomNumber() {
  return Math.random();
}
console.log(generateRandomNumber());

3. async function fetchData(url) {
  const response = await fetch(url);
  const data = await response.json();
  return data;
}
// The function fetchData interacts with an external API, making it dependent on the external environment and hence impure.

4. function getCurrentDate() {
  return new Date();
}

5. function logMessage(message) {
  console.log(message); // This is a side effect
  return message;
}
logMessage('Hello');
// 
```
**NOTE : if a function uses console.log inside it, the function is considered impure. This is because console.log causes a side effect by performing an I/O operation, interacting with the external environment (i.e., the console)**
