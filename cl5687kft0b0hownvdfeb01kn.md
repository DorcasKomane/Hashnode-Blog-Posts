# JavaScript Fundamentals: Destructuring

## Introduction
The **destructuring assignment** allows us to unpack values from arrays, or properties from objects, into distinct variables. It makes it possible to extract only the values we need at a particular time.

The destructuring assignment uses syntax similar to that used in arrays, on the left-hand side of the assignment, to specify the values to be extracted.

In this article, we will look at how to use destructuring to extract the values we are interested in.

Let's dive in! 

## Destructuring Arrays
Destructuring allows us to assign variables from arrays, and makes it possible to choose specific elements of an array.

Let us look at an example:

```
const days = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'];

const [firstDay, secondDay, thirdDay] = days;

console.log(firstDay);  // Monday
console.log(secondDay); // Tuesday
console.log(thirdDay); // Wednesday
``` 

The first element is assigned to the variable *firstDay*, the second element is assigned to the variable *secondDay*, and the third element is assigned to the variable *thirdDay*.

We can also assign values to a variable in the following manner:

```
[firstDay, secondDay] = ['Monday', 'Tuesday'];

console.log(firstDay); // Monday
console.log(secondDay); // Tuesday
``` 

In the case where the number of variables specified on the left-hand side of the assignment is greater than the length of the array on the right, that is, the available values that can be assigned, the extra variables will be undefined. For example:


```
[firstDay, secondDay, thirdDay] = ['Monday', 'Tuesday'];

console.log(firstDay); // Monday
console.log(secondDay); // Tuesday
console.log(thirdDay); // undefined
``` 

To access the value at any index in an array with destructuring, we can use commas to get to the target element. This can be achieved as follows:

```
const [a, b,,,c] = [1, 2, 3, 4, 5];

console.log(a); // 1
console.log(b); // 2
console.log(c); // 5
``` 
The first array element is assigned to the variable *a*, the second element is assigned to the variable *b*, and the fifth element is assigned to the variable *c*.


## Destructuring Objects
We can use destructuring to extract values from objects. First, let us define a *book* object which we will refer to in subsequent examples.

```
let book = {
      title: 'Little Suns',
      author: { firstName: 'Zakes',
                 lastName: 'Mda' },
      publisher: 'Penguin Random House'
}
``` 
We can then use the following instruction to extract specific values from the *book* object:


```
const { title, author } = book;

console.log(title); // Little Suns
console.log(author); // {firstName: 'Zakes', lastName: 'Mda'}
``` 

Destructuring also makes it possible to extract an object value and assign it to a new variable. Let us look at an example:

```
const { title: bookTitle, author: bookAuthor } = book;

console.log(bookTitle); // Little Suns
console.log(bookAuthor); // {firstName: 'Zakes', lastName: 'Mda'}
``` 
 
The new variables *bookTitle* and *bookAuthor* are assigned the values of the properties *title* and *author*, respectively.


## Destructuring Nested Objects
We can also use destructuring to assign variables from nested objects.

The following code snippets show how to access the values of the *book* property called *author*. The *author* property is itself an object within an object, hence, a nested object. 

First, we will assign the values to variables with the same names as the object properties using the following instruction:

```
const { author: { firstName, lastName } } = book;

console.log(firstName); // Zakes
console.log(lastName); // Mda
``` 
We can also assign values to variables with different names from the object properties as follows:


```
const { author: { firstName: writerFirstName, lastName: writerLastName } } = book;

console.log(writerFirstName); // Zakes
console.log(writerLastName); // Mda
``` 

The variables *writerFirstName* and *writerLastName* are assigned values from the nested object *author*, using destructuring.


## Using Destructuring to Swap Variables
The destructuring assignment can also be used to swap variables, without the need for a temporary variable. Let us look at an example:


```
let a = 5;
let b = 9;

//swap the variables
[a, b] = [b, a];

console.log(a) // 9
console.log(b) // 5
``` 
Similarly, we can also swap elements of an array using the destructuring assignment.

```
const colorArray = ['red', 'green', 'yellow'];
[ colorArray[1], colorArray[0] ] = [ colorArray[0], colorArray[1] ];

console.log(colorArray[0]); // green
console.log(colorArray[1]); // red
``` 

## Conclusion
That's it for this article. See you in future posts!

