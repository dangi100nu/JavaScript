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
};
console.log(primeNumber(17));
```

#### Write a JavaScript function to check if a given string is a palindrome

```javascript
// Using Js Core Method
function palimdrome(str) {
  let reverseValue = "";
  for (let i = str.length - 1; i >= 0; i--) {
    reverseValue += str[i];
  }
  return str === reverseValue;
}
console.log(palimdrome("radar"));
// Write a JavaScript program to reverse a given string.
const reverseString = (str) => str.split("").reverse().join("");
```

#### write the js program to get duplicate charactar from the string and stored into object with key as a charactar and value as a number of time duplicate.

```javascript
function duplicateValue(str) {
  let charValue = {};
  let duplicateValue = {};
  for (let i = 0; i < str.length; i++) {
    let char = str[i]; // Get the current character
    // Check if the character has already been encountered
    if (charValue[char]) {
      charValue[char]++;
      // If the character count is greater than 1, add it to the duplicateValue object
      if (charValue[char] > 1) {
        duplicateValue[char] = charValue[char];
      }
    } else {
      // If the character is encountered for the first time, set its count to 1
      charValue[char] = 1;
    }
  }
  return duplicateValue;
}
console.log(duplicateValue("programming"));
```

#### Write a JavaScript program to computing factorials.

```javascript
function factorial(num) {
  if (num < 0) return null;
  if (num === 0) return 1; // base case

  return num * factorial(num - 1); // recursive case
}
console.log(factorial(5));
```

#### Write a JavaScript program to convert a string to title case (capitalize the first letter of each word).
```javascript
// 1. js core 
function toTitleCase(str) {
  let result = '';
  let capitalizeNext = true; // Flag to indicate if the next character should be capitalized
  for (let i = 0; i < str.length; i++) {
    let char = str[i];
    if (char === ' ') {
      // If the current character is a space, add it to the result and set the flag to capitalize the next character
      result += char;
      capitalizeNext = true;
    } else {
      // If capitalizeNext is true, convert the character to uppercase, otherwise to lowercase
      if (capitalizeNext) {
        result += char.toUpperCase();
        capitalizeNext = false; // Reset the flag
      } else {
        result += char.toLowerCase();
      }
    }
  }
  return result;
}
const exampleString = "hello world! this is a test string.";
const titleCasedString = toTitleCase(exampleString);
console.log(titleCasedString); 

// 2. inbuilt methods
function toTitleCase(str) {
  return str
    .toLowercase()
    .split(' ')
    .map((ele) => ele[0].toUpperCase() + ele.slice(1));
    .join(' ')
}
console.log(toTitleCase("my name is sOnu dangi"));
```

#### Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and  "fizzbuzz" at multiples of 3 and 5.

```javascript
let fizzbuzzCount = 0
for (let i = 1; i <= 100; i++) {
  // Check if the number is a multiple of both 3 and 5 first
  if (i % 3 === 0 && i % 5 === 0) {
    console.log("fizzbuzz");
  }
  // Check if the number is a multiple of 3
  else if (i % 3 === 0) {
    console.log("fizz");
  }
  // Check if the number is a multiple of 5
  else if (i % 5 === 0) {
    console.log("buzz");
  }
  // If none of the above conditions are met, just print the number
  else {
    console.log(i);
  }
}
console.log("Number of times 'fizzbuzz' appeared:", fizzbuzzCount);
```

#### write a function that would allow for to do this.
```javascript
var addSix = createBase(6)
addSix(10)
```

```javascript

function createBase(x){
  return function (num) {
     return x+num
  }
}
let addSix = createBase(6) // here createBase funtion return a function that is assign to addSix variable.

console.log(addSix(10))
```

#### how can we check if a given array is array or not.

```javascript
we can check using Array.isArray(). if we going with typeof it always return object because all non-primitive data type typeof are object.
```



