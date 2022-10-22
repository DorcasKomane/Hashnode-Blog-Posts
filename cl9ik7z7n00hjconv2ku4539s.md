# JavaScript Fundamentals: Classes

### Introduction

JavaScript is not a class-based language, but rather, a prototype-based language where objects inherit from other objects. This concept is explained in detail in this stackoverflow [post](https://stackoverflow.com/questions/186244/what-does-it-mean-that-javascript-is-a-prototype-based-language).

In this article we will look at how to define a class in JavaScript and how to create objects based on that class.

Let's dive in!

### What is a JavaScript class?
  - It is a template for JavaScript objects.
  - It is not an object itself, but it is instead used to create objects that share the same characteristics.
  
### How to create a JavaScript class
  - We create a class with the keyword **class**, and we always add a **constructor()** method with parameters that are the **member variables** of the class. Member variables refer to the properties that will be common among the objects of the class. If you do not add a constructor method, JavaScript will add an empty one for you.  That is, a constructor method with no parameters. (I wrote about constructors in this other [article](https://theoverageddev.com/javascript-fundamentals-constructors)).

- The constructor() method is used to initialise object properties. It is executed automatically when a new object is created.

- Every time we create a new object (instance) of a class, it is the responsibility of the constructor method to make (instantiate) the object.

- A class must be defined before we refer to it in our code.

- Let us look at an example of a class:

```
  class Book {
    constructor(title, author, price){
      this.title = title;
      this.author = author;
      this.price = price;
    }
}
``` 
- Note that the name of the class always starts with a capital letter.

### How to create an object using a class
- Using our previous **Book** class example, we can create an object as follows:

```
  let book = new Book('When Rain Clouds Gather', 'Bessie Head', 'R95');
``` 
- **book** is an instance of our **Book** class, and is initialised with values corresponding to title, author and price.

### How to create a class method

- We can add methods to our class definition as follows:

```
  class Book {
      constructor(title, author, price){
         this.title = title;
         this.author = author;
         this.price = price;
      }
      details() {
          console.log(`${this.title} was written by ${this.author}`);
      }
}
``` 
- The **details()** method is added outside the constructor, with no separating comma between the two.

### Setter and Getter methods in classes
- A **Setter Method** is used to set the value of a class member variable. The method receives the set value as an argument.
- A **Getter Method** is used to retrieve the value of a class member variable.

Working with our **Book** class, we could implement these two methods as follows:

```
class Book {
      constructor(title, author, price){
         this.title = title;
         this.author = author;
         this.price = price;
      }
      details() {
          console.log(`${this.title} was written by ${this.author}`);
      }

    //Setter method
    set bookTitle(title){
      this.title = title;
    }

  //Getter method
  get bookTitle(){
    return this.title;
  }
}

let book = new Book('When Rain Clouds Gather', 'Bessie Head', 'R95');

//calling the getter method on our book object
console.log(book.bookTitle);  //When Rain Clouds Gather
``` 

- Note that the getter method is called on the object in a property-like format, without adding the brackets '()'. 

### Conclusion
A class provides a template which we can use to create multiple objects that share the same characteristics. By so doing, we do not need to rewrite the same code every time we create a similar object. Instead, we can create such objects with a single line of code.


### Resources
  - [w3schools.com](https://www.w3schools.com/js/js_classes.asp)
  - [The Net Ninja](https://www.youtube.com/watch?v=Ug4ChzopcE4)
  - [javascript.io](https://javascript.info/class)
  - [Stackoverflow](https://stackoverflow.com/questions/186244/what-does-it-mean-that-javascript-is-a-prototype-based-language)
