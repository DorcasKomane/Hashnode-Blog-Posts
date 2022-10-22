# JavaScript Fundamentals: Prototypes

### Introduction

Every object in JavaScript inherits properties and methods from a prototype. In this article we will take a look at prototypes and how to use them.

Let's dive in!

### What are JavaScript Prototypes?

- Prototypes allow us to add new properties and methods to [object constructors](https://theoverageddev.com/javascript-fundamentals-constructors). 

- An object receives its prototype from the constructor function that was used to create it.

- **Note:** You cannot add properties directly to a constructor; you need to add them inside the constructor function.

### The Prototype Chain

- Every object in JavaScript has a built-in property which is called its **prototype**. The prototype is itself an object and will therefore have its own prototype too, resulting in a **prototype chain**. The chain ends when we reach a prototype that has **null** for its own prototype. (source: [MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)).

- To illustrate the prototype chain, let us first define a [constructor function](https://theoverageddev.com/javascript-fundamentals-constructors) called **Vehicle**:


```
    function Vehicle(manufacturer, make, colour, model){
      this.manufacturer = manufacturer;
      this.make = make;
      this.colour = colour;
      this.model = model;
}
``` 

- Now, let us crate an object instance of this constructor and call it **myVehicle**:


```
 let myVehicle = new Vehicle('BMW', 'sedan', 'red', 2021);
``` 
- **myVehicle**'s prototype is from the **Vehicle** constructor function, and **Vehicle** inherits its prototype from **Object**. Object.prototype is right at the end of the prototype  chain, therefore its prototype is null.


![prototypes.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665105237381/kkCkXnPny.png align="center")

```
  Vehicle.prototype;   //Object
  myVehicle.prototype:    //undefined
``` 

### Using the prototype to add a new property to an object constructor

- Let us look at another example of a constructor:

```
  function Supplier(name, product, contact) {
    this.name = name;
    this.product = product;
    this.contact = contact;
}
``` 

- Say we wanted to add a property to specify the supplier's location. We could use the prototype to achieve that as follows:


```
  Supplier.prototype.location = 'South Africa';
``` 

### Using the prototype to add a new method to an object constructor

- Let us look at how we could add a method to our constructor function:

```
    function Supplier(name, product, contact){
      this.name = name;
      this.product = product;
      this.contact = contact;
}

Supplier.prototype.details = function(){
  return this.name + ' is a supplier of ' + product + '.';
}
``` 

### isPrototypeOf() method

- We can use the **isPrototypeOf() **method to verify an object's prototype:

```
    Vehicle.prototype.isPrototypeOf(myVehicle);    //returns true
    Object.prototype.isPrototypeOf(Vehicle);    //returns true
``` 

- The two lines of code above return true because **myVehicle** object inherited its prototype from the Vehicle constructor function, which in turn inherited its prototype from **Object.prototype**.

### Conclusion

That will be all for this article. I hope it was helpful to you in some way.

See you in the next one!

### Resources

- [w3schools.com](https://www.w3schools.com/js/js_object_prototypes.asp)
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object_prototypes)