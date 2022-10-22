# JavaScript Fundamentals: Functions

## Introduction
In this post we tackle the topic of functions. Functions are a programming concept that is not only applicable in JavaScript, but also in many other programming languages. We will look at what functions are, and how to use them in JavaScript.

Let's dive in! 

## What are functions?
A **function** is a block of code which contains instructions to perform a specific task. We declare a function once and then execute it as many times as we need to, with a simple line of code. This helps us avoid rewriting the same sequence of instructions multiple times through code reuse.

## How to declare a function
 A function can be declared as follows:

```
//without parameters
function functionName() {
     //do something
}

//with a parameter
function functionName(par_1) {
   //do something
}

//with n parameters
function functionName(par_1, par_2,..., par_n) {
   //do something
}
``` 
We can also assign a function to a variable to form a **function expression**:

```
const variable = function() {
   //do something
}
``` 
## Example of a function
Function declaration:

```
function saySomething() {
   console.log('Hello World!');
}
``` 
Function Expression:

```
const greeting = function() {
  console.log('Hello World!');
}
``` 

## Local Scope vs Global Scope

- Variables defined within a function cannot be accessed outside that function. We say these variables have a **local scope** since they can only be accessed locally.

- On the other hand, variables declared outside a function can still be accessed from within the function. We say these variables have a global scope since they can be accessed throughout the program.

## Functions that receive a value

- These are functions that are defined with one or more parameters. The function receives a value corresponding to the parameter at the point of invocation, and uses the value when executing the code in the body of the function.

- In the case of functions with multiple parameters, the values must be passed in the same order as specified in the function declaration.

- In the example below, the function is defined with two parameters (*customerName* and *customerNumber*) and receives the corresponding values (*Lynda* and *78689*) in the right order when the function is called.

```
//function declaration
function customer(customerName, customerNumber) {
   console.log(customerName + ' is customer number ' + customerNumber);
}

//calling the function
customer('Lynda', 78689);

//output
Lynda is customer number 78689
``` 

- We could also provide **default values** for function parameters, in case a value is not provided at the time the function is called. This can be done as follows:

```
//function declaration
function customer(customerName, customerNumber = 78689) {
  console.log(customerName + ' is customer Number ' + customerNumber);
}

//calling the function with only one argument instead of two
customer('Lynda');

//output
Lynda is customer number 78689
``` 
## Functions that return a value

- These functions are declared with the word **return**, which helps us capture some output from a function and then use it outside the function. By using **return**, we are able to access the output after the function has finished executing.

```
function saySomething() {
    return 'Hello World!';
}
``` 
- In order to use the result of the function, we could assign a variable as follows:

```
//function declaration
function saySomething() {
   return 'Hello World';
}

//assign function result to a variable
const greeting = saySomething();

//display variable in the console
console.log(greeting);
``` 
- Let us look at an example that uses mathematical operations:

```
const sum = function(a, b) {
   return a + b;
}

//call the function and assign the output to the variable 'result'
let result = sum(3, 7);

//use function output for further computation
let total = result + 2;

//display variable in the console
console.log(total);

//final output
12
``` 
## Arrow functions

Arrow functions allow us to write shorter versions of functions. Let us demonstrate the syntax of such a function with an example:

```
//function declaration
const sum = function(a, b) {
   return a + b;
}

//converted into arrow function
const sum = (a, b) => a + b;
``` 
Here is how to achieve the above conversion to arrow function:

- first remove the word *function*

```
const sum = (a, b) {
  return a + b;
}
``` 

- add => (equal sign '=' followed by '>') after the parenthesis containing parameters. In the case where the function does not take any parameters, the parenthesis will be left empty. If the function only takes one parameter, we need not use parenthesis.

```
const sum = (a, b) => {
   return a + b;
}
``` 

- if the function contains a simple return statement, we can simplify the function further by removing the curly brackets and moving the return statement immediately after the =>. Also remove *return* from the statement.

```
const sum = (a, b) => a + b;
``` 
## Conclusion
 
I hope this post provided enough information to introduce you to functions in JavaScript. You can read further on the topic [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions).

See you in future posts!
















