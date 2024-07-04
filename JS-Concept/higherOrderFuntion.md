## Higher-Order Function (HOF)

##### A higher-order function is a function that either:

1. Takes one or more functions as arguments, or
2. Returns a function as its result.

This allows functions to be more abstract and reusable. Common examples in JavaScript include map, filter, and reduce.

 ###### 1. Higher-Order Function that take a funtion as an arguments ex: map, reduce, filter etc
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const result = numbers
    .map(num => num * 2)
    .filter(num => num >= 10)
    .reduce((acc, num)=> acc + num, 0);
console.log(result);
```

##### 2. Higher-Order Function that returns a function
```javascript
 function createMultiplier (multiplier) {
    return function(num) {
        return num*multiplier
    }
 }
 const multiplyByTwo = createMultiplier(2)
 console.log(multiplyByTwo(10))
```

 ##### 3. Higher-Order Function that takes two functions as arguments
 ```javascript
function compose(func1, func2) {
    return function (value) {
        return func1(func2(value));
    };
}
// Define two simple functions
function add5(num) {
    return num + 5;
}
function multiplyBy2(num) {
    return num * 2;
}
const add5ThenMultiplyBy2 = compose(multiplyBy2, add5);

console.log(add5ThenMultiplyBy2(10)); // Output: 30
```

## Higher-Order Component (HOC)

A higher-order component is a function that takes a component and returns a new component. HOCs are used in React to reuse component logic.

```javascript
import React from 'react';
// Define a higher-order component (HOC) function
const withBackgroundColor = (WrappedComponent) => {
    // Return a new functional component
    return function WithBackgroundColor(props) {
        const { isAdmin } = props; 
        const backgroundColor = isAdmin ? 'lightgreen' : 'lightcoral';
        return <WrappedComponent {...props} backgroundColor={backgroundColor} />;
    };
};
// Define a basic component to be enhanced
const UserProfile = ({ backgroundColor }) => (
    <div style={{ backgroundColor, padding: '20px', borderRadius: '5px' }}>
        <h2>User Profile</h2>
        <p>This component's background color changes based on isAdmin prop.</p>
    </div>
);
// Enhance the component using the HOC
const EnhancedUserProfile = withBackgroundColor(UserProfile);

// Example usage of the EnhancedUserProfile component
const App = () => (
    <div>
        <EnhancedUserProfile isAdmin={true} />
    </div>
);
export default App;
```


