#### Write a "mul" function which will properly when invoked as below

> Problem
> console.log(mul(2) (3) (4)); // output : 24
> console.log(mul(4) (3) (4)); // output : 48

```javascript
function mul(x) {
  return function (y) {
    // anonymous function
    return function (z) {
      // anonymous function
      return x * y * z;
    };
  };
}
```

#### make a function according to below context

> duplicate([1, 2, 3, 4, 5]) ; // [1,2, 3, 4, 5, 1, 2,3,4,5]

```javascript
function duplicate(arr) {
  return arr.concat(arr);
}
console.log(duplicate([1, 2, 3, 4, 5]));

// without method
function duplicate(arr) {
  let duplicatedArray = [];
  for (let i = 0; i < arr.length; i++) {
    duplicatedArray[i] = arr[i];
  }
  for (let i = 0; i < arr.length; i++) {
    duplicatedArray[duplicatedArray.length] = arr[i];
  }
  return duplicatedArray;
}

console.log(duplicate([1, 2, 3, 4, 5]));
```

#### how would you check if a number an integer??

```javascript
function isInt(num) {
  return num % 1 === 0;
}
console.log(isInt(4.5));
// using method
Number.isInteger(5.6)
```

#### write a function to check given word and phrases are anagrams or not?
>In anagrams, we are checking whether two words or phrases are composed of the exact same characters, with the same frequencies, but arranged in a different order.

```javascript
// using method
function anagrams (str1, str2) {
    let str11 = str1.toLowerCase()
    let str22 = str2.toLowerCase()
    return str11.split('').sort().join('') === str22.split('').sort().join('')
}

console.log(anagrams("integral","triangle"))
console.log(anagrams("silent","listen"))