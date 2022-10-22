# JavaScript Fundamentals: Constructors

## Introduction
Constructors provide an alternative way to create objects. They make it easier to create multiple objects of the same type, with varying property values.

In this article we will look at what constructors are, and how to use them to create objects.

Let's dive in! 

## What are constructors?
- Constructors are functions that create new objects.
- They define properties and behaviours that will belong to the new object.
- Constructors are a blueprint for the creation of multiple objects of the same type.
- Unlike other functions, constructors do not return a value.
- They use the keyword **this** to refer to the object being created. They also use the keyword to set properties of the said object.
- Constructors are defined with a capitalised name to distinguish them from other functions that are not constructors.
        

## How to define a constructor
Let us look at an example of a constructor:

```
function Vehicle(){
    this.manufacturer = 'Toyota';
    this.make = 'sedan';
    this.colour = 'red';
    this.model = 2020;
}
``` 
- Our *Vehicle* constructor defines an object with *manufacturer*, *make*, and *model* as its properties.

- Note that the constructor name starts with a capital letter to differentiate it from other functions that are not constructors.

- The keyword **this** inside the constructor always refers to the object being created.

## How to use a constructor to create an object
Let us use our *Vehicle* constructor to create a new vehicle object:

```
function Vehicle(){
  this.manufacturer = 'Toyota';
  this.make = 'sedan';
  this.colour = 'red';
  this.model = 2020;
}

//using the Vehicle constructor to create myVehicle object
let myVehicle = new Vehicle();
``` 
- The **new** operator is used when calling a constructor, to tell JavaScript to create a new instance of *Vehicle*.

- *myVehicle*, an instance of *Vehicle*, has all the default properties defined in the constructor:

```
console.log(myVehicle.manufacturer); // Toyota
console.log(myVehicle.make); // sedan
console.log(myVehicle.colour); // red
console.log(myVehicle.model); // 2020

``` 
- We can access and change properties of *myVehicle* object like we would for any other object. For instance, we could change the new object's colour as follows:

```
myVehicle.colour = 'silver grey';

console.log(myVehicle.colour); // silver grey 
``` 
 
## Constructors with arguments
- Although object values can be edited after object creation, it would be too tedious to do that for each object, particularly when dealing with multiple objects. 

- We can ensure that every object we create with a constructor has different property values by specifying them as arguments when calling the constructor during object creation. Let us look at an example:

```
function Vehicle(manufacturer, make, colour, model) {
  this.manufacturer = manufacturer;
  this.make = make;
  this.colour = colour;
  this.model = model;
}

//create an instance of Vehicle
let jonesVehicle = new Vehicle('Mercedes', 'SUV', 'charcoal grey', 2022);

console.log(jonesVehicle.manufacturer); // Mercedes
console.log(jonesVehicle.make); // SUV
console.log(jonesVehicle.colour); // charcoal grey
console.log(jonesVehicle.model); // 2022
``` 
- Here we passed specific property values to the constructor, instead of using default values inside the constructor function.

## The *instanceof* operator
An object created with a constructor function is said to be an *instance* of that constructor. The **instanceof** operator is therefore used to verify which constructor was called to create a particular object. It returns *true* or *false* depending on whether or not an object was created with the specified constructor. 

Let us look at the syntax:

```
jonesVehicle instanceof Vehicle; // returns true
``` 
The instruction above returns *true* since the *jonesVehicle* is indeed an instance of the *Vehicle* constructor.

## Conclusion
That will be all for this article. I hope it was helpful to you in some way.

See you in the next one!


## References
- [freeCodeCamp.org](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/object-oriented-programming/define-a-constructor-function)
- [w3schools.com](https://www.w3schools.com/js/js_object_constructors.asp)