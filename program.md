# JavaScript Program

## Write a JavaScript function to calculate the sum of two numbers.  

```javascript
const addNumbers = (a, b) => a+b
let result = addNumbers(5, 3);
console.log("Result:", result); 
```

## Write a JavaScript program to find the maximum and minimum number in an array.  

```javascript
// using core js
function maxNumber(array){
    if(!Array.isArray(array) || array.length === 0) return null;
    let maxValue = array[0];
    for(let i = 1 ; i<=array.length-1 ; i++) {
        if(array[i]>maxValue){
            maxValue = array[i]
        }
    }
    return maxValue
}
console.log("max number-1",maxNumber([1,2,3]));
// using method 
let array = [1,2,3]
console.log("max number-2",Math.max(...array))
console.log("min number",Math.min(...array))
```

