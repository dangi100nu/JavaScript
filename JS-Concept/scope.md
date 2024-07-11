## scope

>Scope in JS determines the accessibility of variables and functions at various parts of one’s code.

>In general terms, the scope will let us know at a given part of code, what are variables and functions we can or cannot access.

##### There are three types of scopes in JS:
1. Global Scope
2. Local or Function Scope
3. Block Scope

**Global Scope:** Variables or functions declared in the global namespace have global scope, which means all the variables and functions having global scope can be accessed from anywhere inside the code.

```javascript
var globalVariable = "Hello world";
function sendMessage(){
  return globalVariable; 
}
function sendMessage2(){
  return sendMessage(); 
}
sendMessage2();
```

**Function Scope:** Any variables or functions declared inside a function have local/function scope, which means that all the variables and functions declared inside a function, can be accessed from within the function and not outside of it.

```javascript
function awesomeFunction(){
  var a = 2;
  var multiplyBy2 = function(){
    console.log(a*2); // Can access variable "a" since a and multiplyBy2 both are written inside the same function
  }
}
console.log(a); // Throws reference error since a is written in local scope and cannot be accessed outside
multiplyBy2(); // Throws reference error since multiplyBy2 is written in local scope
```

**Block Scope:** Block scope is related to the variables declared using let and const. Variables declared with var do not have block scope. Block scope tells us that any variable declared inside a block { }, can be accessed only inside that block and cannot be accessed outside of it.

```javascript
{
  let x = 45;
}
console.log(x); // Gives reference error since x cannot be accessed outside of the block
for(let i=0; i<2; i++){
  // do something
}
console.log(i); // Gives reference error since i cannot be accessed outside of the for loop block
```

## scope chain

>JavaScript engine also uses Scope to find variables. Let’s understand that using an example:

```javascript
{
  let x = 45;
}
console.log(x); // Gives reference error since x cannot be accessed outside of the block
for(let i=0; i<2; i++){
  // do something
}
console.log(i); // Gives reference error since i cannot be accessed outside of the for loop block
```

>As you can see in the code above, if the javascript engine does not find the variable in local scope, it tries to check for the variable in the outer scope. If the variable does not exist in the outer scope, it tries to find the variable in the global scope.

>If the variable is not found in the global space as well, a reference error is thrown.