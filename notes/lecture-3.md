# Episode 3 : Hoisting in JavaScript (variables & functions)

* Let's observe the below code and it's explaination:
```js
getName(); // Namaste Javascript
console.log(x); // undefined
var x = 7;
function getName() {
 console.log("Namaste Javascript");
}
```

* It should have been an outright error in many other languages, as it is not possible to even access something which is not even created (defined) yet But in JS, We know that in memory creation phase it assigns undefined and puts the content of function to function's memory. And in execution, it then executes whatever is asked. Here, as execution goes line by line and not after compiling, it could only print undefined and nothing else. This phenomenon, is not an error. However, if we remove var x = 7; then it gives error. Uncaught ReferenceError: x is not defined

* **Hoisting** is a concept which enables us to extract values of variables and functions even before initialising/assigning value without getting error and this is happening due to the 1st phase (memory creation phase) of the Execution Context. ![image](https://github.com/snigdhob/namaste-javascript-notes/assets/20543966/5331ad19-7c42-49e9-8ce4-3fa3f97fab61) ![image](https://github.com/snigdhob/namaste-javascript-notes/assets/20543966/f2fd777a-d210-4dde-a244-db4e0a7fb441)



* So in previous lecture, we learnt that execution context gets created in two phase, so even before code execution, memory is created so in case of variable, it will be initialized as undefined while in case of function the whole function code is placed in the memory. Example:

```js
getName(); // Namaste JavaScript
console.log(x); // Uncaught Reference: x is not defined.
console.log(getName); // f getName(){ console.log("Namaste JavaScript); }
function getName(){
    console.log("Namaste JavaScript");
}
```

* Now let's observe a different example and try to understand the output.
```js
getName(); // Uncaught TypeError: getName is not a function
console.log(getName);
var getName = function () {
    console.log("Namaste JavaScript");
}
// The code won't execute as the first line itself throws an TypeError.
```
This happens because getName is a function expression. So, in the memory creation phase, JS treats it as a variable and initializes it as undefined. Same thing happens for arrow functions as well.
![image](https://github.com/snigdhob/namaste-javascript-notes/assets/20543966/1f14ca48-add7-4151-965b-5491d8e8c246)


<hr>

Watch Live On Youtube below:

<a href="https://www.youtube.com/watch?v=Fnlnw8uY6jo&ab_channel=AkshaySaini" target="_blank"><img src="https://img.youtube.com/vi/Fnlnw8uY6jo/0.jpg" width="750"
alt="Hoisting Youtube Link"/></a>
