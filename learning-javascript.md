# Learning Javascript

## [10 javascript concept you need to know](https://codeburst.io/10-javascript-concepts-you-need-to-know-for-interviews-136df65ecce)

## Basic concepts

### Variables

Before ES6, ```var``` was the only keyword used to declare variables in JavaScript. 

With ES6 JavaScript introduced two other variable declaration keywords ```let``` and ```const```

```const``` is just like any other variable with some exceptions:
- Need to initialize the value when declared
- A new value can’t be assigned afterward (Not very variable, is it?) 

```var``` ignores the blocks and is defined to the closest function or global scope. ```let``` and ```const``` on the other hand are block scoped variables.

![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*0YTEqYUeagQ34e31n4D6Fw.png)
![]({{site.baseurl}}/https://cdn-images-1.medium.com/max/800/1*C3JNKH2fVZLllE9MSiU1zg.png)

### Functions

Javascript is a functional language meaning that functions are the primary modular units of execution.

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
- Scope
- Context
- .this
- Closures
- Immediately-Invoked Function Expression (IIFE)
- .call(), .apply() and .bind()

## [Hoisting](https://codeburst.io/hoisting-in-javascript-515c987336d3)

*how Variables and Function **declarations (different from initilization or definition)** are ‘lifted’ to the top of a function or a global scope even if they are declared after execution*

- Global execution context and Function execution context
- Lexical environment (*something that keeps track of variables and functions within a block of code*)
- Phases of execution (*The first phase registers all the variables and function declarations within the current lexical environment - local and global -. After that is done, the second phase — Javascript execution begins!*)

[Hoisting2](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/)

## [.this](https://www.educative.io/collection/page/5679346740101120/5707702298738688/5676830073815040)

5 rules to learn how JS engine is using to do it

## [new (Object-oriented Programming)](https://codeburst.io/javascripts-new-keyword-explained-as-simply-as-possible-fec0d87b2741)

## [Apply vs. Call vs. Bind](https://codeplanet.io/javascript-apply-vs-call-vs-bind/)

- Call invokes the function and allows you to pass in arguments one by one.
- Apply invokes the function and allows you to pass in arguments as an array.
- Bind returns a new function, allowing you to pass in a this array and any number of arguments.
