# JavaScript Fundamentals: Arrays

# Introduction

In this article we will take a look at arrays: what they are, how to create them, and some of the methods that can be called on them to copy and remove items.

Let's dive in!

# What is an array?


- An **array** is a variable used to store a list of items that can be accessed by their index. 

- An **index** is a number that specifies the position of an element in an array. The first item in an array is stored at position zero.

- In JavaScript, items stored in an array can be of any data type. This means that an array in JavaScript can store strings, numbers, booleans, etc, at the same time. This is different from some programming languages where the contents of an array are required to be of the same data type.

# How to create an array


- An empty array can be created as follows:

```
//syntax
const arrayName = [];

//Example
const students = [];
``` 

- Arrays can be one-dimensional or multi-dimensional. A **one-dimensional** array contains no nested arrays. A **multi-dimensional** array on the other hand, contains one or more arrays as its elements; hence, it is called an *array of arrays*.


```
//one-dimensional array
const arrayName = [ item_1, item_2,..., item_n ];

//multi-dimensional array
const arrayName = [ 
     [ item_1, item_2,..., item_n ], 
     [ anotherItem_1, anotherItem_2,..., anotherItem_n ] 
];
``` 

- Let us look at some examples:

```
const students = ['Lee', 'Ryan', 'Mandisa'];

const studentAges = [ ['Lee', 23], ['Ryan', 21], ['Mandisa', 20] ];

const studentData = [ 
     [ 'Lee', 23, [ 'English', 'Geography' ] ], 
     [ 'Ryan', 21, [ 'Biology', 'Chemistry' ] ], 
     [ 'Mandisa', 20, [ 'Physics', 'Chemistry' ] ] 
];
``` 


# How to access array elements


### One-Dimensional Arrays

- We can access array elements using indexes. Remember that array elements are numbered starting at zero.

- To access the names in our *students* array above, we can use bracket notation as follows:

```
students[0];  // Lee
students[1];  // Ryan
students[2];  // Mandisa
``` 

### Multi-Dimensional Arrays

- If we wanted to access the age of the first student, Lee, we would use the following instruction:

```
studentAges[0][1];  //23
``` 


- Lee is the first student in our array, and her name and age are stored in the first element of the *studentAges *array. This element is itself an array. So, in the instruction above the first index [0] refers to the first element of the *studentAges* array, and the second index [1] refers to the second element stored in the first sub-array that contains Lee's information.


![Diagram 1 showing how to access elements in a multi-dimensional array](https://cdn.hashnode.com/res/hashnode/image/upload/v1653976162218/EOErOApIP.png align="center")


- Say for instance, we were interested in the second subject Lee is majoring in. We would access that subject with the following instruction:


![Diagram 2 showing how to access elements in a multi-dimensional array](https://cdn.hashnode.com/res/hashnode/image/upload/v1653976290661/-2GZd8kpL.png align="center")


- If we inspect the result of the above instruction in the console, the output would be 'Geography'.

```
console.log(studentData[0][2][1]); // Geography
``` 


# How to add items to an array using unshift() and push() methods


- We use the unshift() method to add items to the beginning of an array, and the push() method to add items to the end of an array.

- To add two more names to our *students* array, we will use the following instructions which implement unshift() and pop():


```
//adds 'Zoe' to the front of the array
students.unshift('Zoe');

console.log(students); // [ 'Zoe', 'Lee', 'Ryan', 'Mandisa' ]

//adds 'Thandi' to the end of the array
students.push('Thandi');

console.log(students); // [ 'Zoe', 'Lee', 'Ryan', 'Mandisa', 'Thandi' ]
``` 

- The *students* array is now updated with two other names - one in the beginning of the array, and the other at the end.


# How to remove items from an array using shift() and pop() methods

- We use the shift() method to remove items from the beginning of an array, and the pop() method to remove items from the end of an array. These methods do not take arguments.

- Let us remove the student names we added in the previous example:


```
//removes 'Zoe' from the array
students.shift();

console.log(students); // [ 'Lee', 'Ryan', 'Mandisa', 'Thandi' ]

//removes 'Thandi' from the end of the array
students.pop();

console.log(students); // [ 'Lee', 'Ryan', 'Mandisa' ]
``` 

# How to remove items from an array using splice() method

- Unlike shift() and pop() methods, the splice() method is not restricted to a certain position in the array. With the splice() method, we can remove one or more items from any position in the array.

- The splice() method mutates an array; that is, it modifies the array it is called upon.

- Here is the syntax to remove items from an array using the splice() method:


![Diagram showing how to remove items from an array using the splice() method](https://cdn.hashnode.com/res/hashnode/image/upload/v1653931893184/5vAj573tJ.png align="center")


- Let us remove some of the names from our *students* array using splice():


```
// will remove 'Lee' and 'Ryan' from the array
students.splice(0, 2); 

console.log(students); // ['Mandisa']
``` 

- Items removed from the list can be assigned to a new variable to form another array. In the example below, we use splice() to create an array of new students. We then inspect the contents of the new array, which contains the names 'Ryan' and 'Mandisa'.


```
const newStudents = students.splice(1, 2);

console.log(newStudents); // ['Ryan', 'Mandisa']
``` 

# How to add items to an array using the splice() method

- We can add items to an array by including a third parameter in the splice() method. This parameter specifies the items to be added. We can specify one or more items we wish to add. 



![Diagram showing syntax used to add items to an array with splice() method](https://cdn.hashnode.com/res/hashnode/image/upload/v1653933297730/0s-14JazO.png align="left")

- Let us look at an example by adding names to our *students* array:


```
students.splice(1, 0, 'Zeb', 'Musa');

console.log(students); // [ 'Lee',  'Zeb', 'Musa', 'Ryan', 'Mandisa' ]
``` 

- Our *students* array now has the names 'Zeb' and 'Musa' added, starting at index 1.


# How to copy array items using the slice() method

- Unlike the splice() method, the slice() method does not modify the array it is called upon. Instead, it extracts the specified number of items into a new array, without altering the original array.

- Let us take a look at the syntax:


![Diagram showing syntax used to copy array elements with the slice() method](https://cdn.hashnode.com/res/hashnode/image/upload/v1653934925809/VP8lSiKB2.png align="center")


- The slice() method takes two arguments: the first being the index in the array from which to start extracting elements, and the second being the index at which to stop extracting elements. Note that array elements will be extracted up to, but not including the element at the second index.

- The slice() method returns an array with the selected items.

- Going back to our *students* array, we will use the slice() method to copy the names 'Ryan', 'Zeb', and 'Musa' into a new array.


```
const newArray = students.slice(1, 4);

console.log(newArray); // [ 'Zeb', 'Musa', 'Ryan']

console.log(students); // [ 'Lee',  'Zeb', 'Musa', 'Ryan', 'Mandisa' ]
``` 

- As expected, the *students* array remains unchanged, and we have a new array with the elements 'Zeb', 'Musa', and 'Ryan'.

# The Spread Operator

- The spread operator allows us to copy all elements in an array in the order in which they are stored. Here is what the syntax looks like:

```
const arr = [ item_1, item_2, item_3];

//copies all the elements of arr into arrCopy
const arrCopy = [...arr];
``` 

- Let us copy our *students* array into another array using the spread operator: 


```
const students = [ 'Lee', 'Zeb', 'Musa', 'Ryan', 'Mandisa' ];

//copies all elements of students array into newStudents
const newStudents = [...students];

console.log(newStudents); // [ 'Lee', 'Zeb', 'Musa', 'Ryan', 'Mandisa' ];

console.log(students); // [ 'Lee', 'Zeb', 'Musa', 'Ryan', 'Mandisa' ];

``` 

- The spread operator does not mutate the original array, but copies all its elements, in order, into another array.

- We can also use the spread operator to combine arrays. This can be achieved as in the following example:


```
const students = [ 'Lee', 'Ryan', 'Mandisa' ];

//copies all elements of the students array into allStudents
const allStudents = [ 'Zeb', 'Musa', ...students ];

console.log(allStudents); // [ 'Zeb', 'Musa', 'Lee', 'Ryan', 'Mandisa' ]
``` 


- Here is another example where we combine arrays using the spread operator:


```
const students = [ 'Lee', 'Ryan', 'Mandisa' ];

const newStudents = [ 'Zeb', 'Musa' ]; 

//combines elements of the students array and newStudents into allStudents
const allStudents = [ ...students, ...newStudents ];

console.log(allStudents); // [ 'Lee', 'Ryan', 'Mandisa', 'Zeb', 'Musa' ]
``` 


# Conclusion

There are many other interesting methods that can be used with arrays. You can learn more [here](https://www.w3schools.com/jsref/jsref_obj_array.asp).

I hope this article was helpful to you.

See you in future posts!

# References

- [www.w3schools.com](https://www.w3schools.com/js/js_arrays.asp)
- [www.freecodecamp.org](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/#basic-data-structures)



