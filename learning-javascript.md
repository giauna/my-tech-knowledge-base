# Learning Javascript

https://github.com/mbeaudru/modern-js-cheatsheet
http://es6-features.org
https://codeburst.io/es6-tutorial-for-beginners-5f3c4e7960be

https://codeburst.io/we-boosted-our-javascript-projects-maintainability-by-following-these-guidelines-62536e6e0d04

https://codeburst.io/master-javascript-prototypes-inheritance-d0a9a5a75c4e

https://codeburst.io/generators-in-javascript-1a7f9f884439

## [10 javascript concept you need to know](https://codeburst.io/10-javascript-concepts-you-need-to-know-for-interviews-136df65ecce)

## Basic concepts

### Variables

Before ES6, ```var``` was the only keyword used to declare variables in JavaScript. 

With ES6 JavaScript introduced two other variable declaration keywords ```let``` and ```const```

```const``` is just like any other variable with some exceptions:
- Need to initialize the value when declared
- A new value can’t be assigned afterward

```var``` ignores the blocks and is defined to the closest function or global scope (```var``` is function-scoped). 

```let``` and ```const``` on the other hand are **block scoped variables** (block = code between the opening and closing curly braces).

```
let count = 5;
// 20 lines of code

for(let count = 0; count < 15; count++) {
  // do stuff
}

// 10 lines of code
console.log(count); // 5 -- as expected
```

![](https://cdn-images-1.medium.com/max/800/1*0YTEqYUeagQ34e31n4D6Fw.png)
![](https://cdn-images-1.medium.com/max/800/1*C3JNKH2fVZLllE9MSiU1zg.png)

*There isn’t a solid argument for why anyone should keep using ```var``` anymore in ES6 JavaScript*

### Functions

Javascript is a functional language meaning that functions are the primary modular units of execution.

Functions are first-class objects. They are treated like any other JavaScript object.

#### Definition

**Function declaration (or function statement)**

```
function sayHello() {
  console.log('Hello!')
}
```

When you are declaring functions like this, the content of the function get’s compiled and an object with the same name as the function’s name is created.

**Function expression**

```
var sayHello = function () {
  console.log('Hello!')
}
```
If there is no name given then that is an **anonymous function**. This anonymous function is getting assigned to a variable and this variable is used to invoke the function.

**Self Invoked Function**

```
(function greet() {
  console.log("Hello all from inside.");
})(); //=> Self invoked!
```


#### Parameters and Arguments

- *Parameters* are variables listed as a part of the function definition.
- *Arguments* are values passed to the function when it is invoked.

JavaScript does not throw an error if the number of arguments passed during a function invocation are different than the number of parameters listed during function definition.

#### The argument parameter
The ```arguments``` parameter is local variable accessible within all functions and contains an entry for each argument passed to that function. The arguments object is an array-like construct which can be used to access arguments passed to the function even if a matching parameter isn’t explicitly defined.
```javascript
function argumentVar(parameter1, parameter2, parameter3){
  console.log(arguments.length); // Logs the number of arguments passed.
  console.log(arguments[3]); // Logs the 4th argument. Follows array indexing notations. 
}

argumentVar(1,2,3,4,5);
// Log would be as follows
// 5
// 4

// 5 is the number of arguments
// 4 is the 4th argument
```

#### Rest Parameters

Rest Parameter is an ES6 addition to JavaScript. To create a rest parameter prefix the last parameter in a function definition with ellipsis(…). 

```javascript
function restParam(...restArgs){
  console.log(restArgs.length); // Logs the number of arguments passed
  console.log(restArgs[3]); // Logs the 4th argument
}

restParam(1,2,3,4,5);
// Log would be as follows
// 5
// 4

// 5 is the number of arguments
// 4 is the 4th argument
```

- ```Rest Parameters``` is a real array and methods like ```forEach``` and ```sort``` can be applied. Even though the ```arguments``` object has the ```length``` method, it is not a real array and using array methods like ```sort``` would only bring us misery and sorrow.
- ```Rest Parameters``` contain only the arguments that have no corresponding parameter while ```arguments``` object contains all the arguments passed to the function. Code snippet could also be written as follows.

#### return statement
[link](https://codeburst.io/javascript-what-is-the-return-statement-97d8b11a1a0c)

## Value vs reference [(link)](https://www.educative.io/collection/page/5679346740101120/5707702298738688/5685265389584384/)

### Primitives
#### Arrays
[ES6 — Array.find & Array.findIndex](https://codeburst.io/learn-javascript-es6-array-find-array-findindex-7fe4f63c6974)
[ES6 — Learn Array.keys, Array.values, and Array.entries](https://codeburst.io/javascript-es6-learn-array-keys-array-values-and-array-entries-7e4c9995bb44)
[Finding max-min values in an Array of Objects](https://codeburst.io/javascript-finding-minimum-and-maximum-values-in-an-array-of-objects-329c5c7e22a2)

- Objects
- Assigning by Reference

Whenever a variable is not explicitly assigned with a value, which could be the case of an out-of-range array accessing or an ignored function argument, the variable is set as ```undefined``` by the runtime.

### == and ===

== does automatic type conversion and compare the “value”. So a string "1" equals to an integer 1 in ==.

=== does not do type conversion. So when comparing a string to an integer, === returns false regardless of the value.

```javascript
//comparing string with number
var res = "1" == 1;
alert(res); //=>true
res = "1" === 1;
alert(res); //=>false
```

- Passing Parameters through Functions

## [Scope and Context](https://scotch.io/tutorials/understanding-scope-in-javascript#toc-scope-in-javascript)

### Scope

The scope refers to the current context of code. A variable's scope is the context in which the variable exists.

**Global scope**

Any variable that you declare by default is been defined in global scope. A global variable is visible in all other scopes and can be modified by any scope.

If the sub-programs have one or more global variables that share the same name(s), then they will get involved with each other and likely


**Local scope**

Local Scope
JavaScript doesn’t have block-level scope aka the variables scoped to surrounding curly brackets instead, the language have a function-level scope. The variables declared in a function are simply local variables and is only accessible within that function or by functions inside that function.

**Block scopes**

ES6 introduces the ```let``` and ```const``` keywords to introduce traditional block scope. 

```
var structure = ‘HTML5 is the best!’;
let interactivity = ‘ES6 Rules’;
if (true) {
 var structure = ‘Long live Flash’; //=> scope is global
 let interactivity = ‘ES5 Sucks’; //=> scope is (local) block-level
 console.log(structure); //=> Print’s “Long live Flash”
 console.log(interactivity); //=> Print’s “ES5 Sucks”
}
console.log(structure); //=> Print’s “Long live Flash”
console.log(interactivity); //=> Print’s “ES6 Rules”
```

- Context
- .this
- Closures
- Immediately-Invoked Function Expression (IIFE)
- .call(), .apply() and .bind()

## [Hoisting](https://codeburst.io/hoisting-in-javascript-515c987336d3)

Variables' (```var```) and Functions' **declarations (different from initilization or definition)** are ‘lifted’ to the top of a function or a global scope even if they are declared after execution

*Note: ```let/const/class``` declarations behave differently.*

JavaScript engine does its job in two phases: the *memory creation phase* and the *execution phase*, and that our code won’t be executed until the second phase.

```
console.log(x)
var x

// undefined
```
```x``` is defined and available before its declaration — yes, this is a legitimate example of hoisting.

It’s important to note that, in JavaScript, ```undefined``` is an actual value. So this is basically JavaScript engine interpreting ```var x = undefined```, just like ```var x = 5```

But who sets the value of ```x``` to ```undefined```?

This is a job of the JavaScript engine. During the ```memory creation phase```

```
console.log(x)
var x = 10

// undefined
```

You might have guessed that it would print out 10... but **initialisations are not hoisted**.

#### What about functions?

```
sayHello()

function sayHello () {
  console.log('Hello!')
}

// Hello!
```

JavaScript engine made the ```function``` available by putting it into the memory, before moving on. That’s why I could access the ```sayHello function``` prior to its declaration in the ```execution phase```.

```
sayHello()

var sayHello = function () {
  console.log('Hello!')
}

//TypeError
```

```sayHello is not a function```. Hmm… wait, what!?

We need to to know the difference between ```function declaration``` and ```function expression```.

**Function Expressions are Not Hoisted**


- Global execution context and Function execution context
- Lexical environment (*something that keeps track of variables and functions within a block of code*)
- Phases of execution (*The first phase registers all the variables and function declarations within the current lexical environment - local and global -. After that is done, the second phase — Javascript execution begins!*)

[Hoisting2](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/)

## [.this](https://www.educative.io/collection/page/5679346740101120/5707702298738688/5676830073815040)
## [this](https://codeburst.io/javascript-this-and-its-binding-582945b06612)

5 rules to learn how JS engine is using to do it

## [new (Object-oriented Programming)](https://codeburst.io/javascripts-new-keyword-explained-as-simply-as-possible-fec0d87b2741)

## [Apply vs. Call vs. Bind](https://codeplanet.io/javascript-apply-vs-call-vs-bind/)

- Call invokes the function and allows you to pass in arguments one by one.
- Apply invokes the function and allows you to pass in arguments as an array.
- Bind returns a new function, allowing you to pass in a this array and any number of arguments.
