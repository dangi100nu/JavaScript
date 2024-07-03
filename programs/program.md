## JavaScript Program

#### Write a JavaScript function to calculate the sum of two numbers.
```javascript
const addNumbers = (a, b) => a + b;
let result = addNumbers(5, 3);
console.log("Result:", result);
```

#### Write a JavaScript program to find the maximum and minimum number in an array.
```javascript
// using built
function maxNumber(array) {
  if (!Array.isArray(array) || array.length === 0) return null;
  let maxValue = array[0];
  for (let i = 1; i <= array.length - 1; i++) {
    if (array[i] > maxValue) {
      maxValue = array[i];
    }
  }
  return maxValue;
}
console.log(maxNumber([1, 2, 3]));
// Using Js Core Method
let array = [1, 2, 3];
console.log(Math.max(...array));
console.log(Math.min(...array));
```

#### Write a JavaScript function to check if a given number is prime. 
```javascript
const primeNumber = (num) => {
    if (num <= 1) return false;
    for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false; 
    }
    return true;
}
console.log(primeNumber(17));  
```

#### Write a JavaScript function to check if a given string is a palindrome
```javascript
// Using Js Core Method
function palimdrome(str){
    let reverseValue = ""
    for(let i=str.length-1; i>=0 ; i--) {
        reverseValue += str[i]
    }
    return str === reverseValue
}
console.log(palimdrome("radar"));
// Write a JavaScript program to reverse a given string. 
const reverseString = (str) => str.split("").reverse().join(""); 
```
