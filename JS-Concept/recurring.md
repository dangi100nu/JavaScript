## Recurring In Javacript.

> Refers to any event, task, or operation that happens repeatedly at regular or irregular intervals.
>
> any repetitive action called recurring including loops, intervals, and events.
> in JavaScript, anything that happens repeatedly can be considered recurring.
>
> **Example :**
> setInterval, for loops, repeated event handling, polling with setTimeout.
> Implemented using constructs like loops (for, while), intervals (setInterval), and event listeners.

##### 1. Set Intervals:

```javascript
1. setInterval(() => {
  console.log("my name is sonu dangi");
});
// This code will log the message every 2 seconds indefinitely.

2. let count = 0;
const intervalId = setInterval(() => {
    count++;
    console.log(count);
    if (count === 5) {
        clearInterval(intervalId); // Stops the recurring action
    }
}, 1000);
```

##### 2. Loops:

```javascript
// Executing a block of code repeatedly.
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

##### 3. Recurring Events in UI:

```javascript
// Using event listeners to repeatedly handle events such as clicks.
document.getElementById("myButton").addEventListener("click", () => {
  console.log("Button was clicked");
});
```

##### 4. recurring with setTimeout:

```javascript
// Using setTimeout in a recursive manner to create recurring behavior.
function repeatMessage() {
  console.log("This message appears every 2 seconds");
  setTimeout(repeatMessage, 2000);
}
repeatMessage();
```

##### 4. Recurring Promises:

```javascript
// pollServer is a function that uses polling to repeatedly fetch data from a server every 5 seconds.
function pollServer() {
  fetch("https://api.example.com/data")
    .then((response) => response.json()) // Process the server's response
    .then((data) => {
      console.log(data); // Log the data received from the server
      setTimeout(pollServer, 5000); // Wait for 5 seconds before polling again
    });
}
pollServer();
```

##### 5. Creating UI elements that repeat, such as in list rendering with frameworks like React.

```javascript
/const numbers = [1, 2, 3, 4, 5];

function NumberList(props) {
    const numbers = props.numbers;
    const listItems = numbers.map((number) =>
        <li key={number.toString()}>
            {number}
        </li>
    );
    return (
        <ul>{listItems}</ul>
    );
}
// Usage
<NumberList numbers={numbers} />
```



## Recursion In JavaScript.

> **Definition:** A programming technique where a funtion calls itself to solve a problem. Recursion involves breaking down a problem into smaller subproblems and solving each by calling the same funtion.
>
> **Key Characteristics:**
>
> 1. Base Case: The condition under which the function stops calling itself.
> 2. Recursive Case: The part of the function where it continues to call itself.
>
> **examples:** Computing factorials, palimdrome, solving the Fibonacci sequence.

##### 1. Recursion with Factorial Calculation.

```javascript
function factorial(n) {
  if (n === 0) {
    return 1; // Base case
  }
  return n * factorial(n - 1); // Recursive case
}
console.log(factorial(5)); // Output: 120
```

##### 2. Recursion with Fibonacci Sequence:

```javascript
function fibonacci(n){
 if (n<=1){
     return n; // Base case
 }
 retrun fibonacci(n-1) + fibonacci(n-2); // Recursive case
}
console.log(fibonacci(10))
```

**important** The Fibonacci series is a sequence of numbers where each number is the sum of the two preceding ones, usually starting with 0 and 1. The sequence begins as follows:
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...
Definition and Formula
The Fibonacci sequence is defined recursively as:
F(0)=0
F(1)=1
F(n)=F(n-1) + F(n-2) for n>1
This means that the nth Fibonacci number 𝐹(𝑛) is the sum of the (n-1)th and (n-2)th Fibonacci numbers.


## Conclusion:

1. **True:** All recursive actions are recurring because they involve repetitive function calls.
2. **False:** Not all recurring actions are recursive, as recurring actions can also be implemented using loops, timers, and other constructs without involving self-calling functions.