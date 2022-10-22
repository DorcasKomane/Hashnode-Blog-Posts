# JavaScript Fundamentals: Objects

## Introduction

Objects are an important element in Javascript. Therefore, having a good grasp of the concept will be beneficial in your understanding of the language. 

In this post we will cover how to define objects, as well as how to initialize and manipulate their properties.

Let's dive in!

## Defining Objects

### What is an object?

- Objects are a data type in Javascript.

- An object can be thought of as an entity with a collection of properties associated with it.

- An object can be initialised with a set of properties, or the properties can be added after initialisation. The properties can also be altered or deleted.

- Properties are represented in a key:value format, where every property is represented in terms of the property name(key) and its corresponding value. Thus, an object is a mapping between keys and values.

- A key can either be a string or symbol value.

- A property value can be of any type, including an object type.

## Initialising Objects

- An object can be initialised using the initialiser notation.

- An [object initialiser](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer) is a list of zero or more pairs of property names and associated values of an object, separated by commas, and enclosed in curly braces ({}).

How to initialise an object without properties:


```
      let object = {}

``` 

How to initialise an object with *n* properties:


```
let object = {
          prop_1: value_1,
          prop_2: value_2,
                    .
                    .
                    .
         prop_n: value_n
}
``` 

Here's an example of a *book* object, initialised with properties. Notice how the *author* property is itself an object:


```
let book = {
 title : 'Little Suns',
 author : { firstName: 'Zakes',
             lastName: 'Mda' },
 publisher : 'Penguin Random House',
 isbn: '9781415209714',
 price : 'R280'
}
``` 
## Accessing Object Properties

Sometimes we need to access object properties in order to carry out some other processing. In that case, we could access an object's properties as follows, using either the dot or bracket notation:

```
object.property
object.['property']
``` 

Here's an example using our *book* object:

```
book.title  // will return 'Little Suns'                      
book.author.firstName  // will return 'Zakes'
book['price'] // will return 'R280'
book['author']['lastName'] // will return 'Mda'
``` 
## Updating Object Properties

We might need to add a new property to our object, or change the details of an existing property. We could accomplish that as follows:

```
book.title = 'The Whale Caller'
``` 
Evaluating our book object's *title* property will now reflect the change we made:

```
book.title  // will return 'The Whale Caller'
``` 

We can also add a new property to our *book* object using the instruction:

```
book.format = 'Paperback'
``` 

Let us inspect the details of our *book* object with the instruction:

```
console.log(book);
``` 

The output will be as follows:

```
{
  title: 'The Whale Caller ',
  author: { firstName: 'Zakes',
             lastName: 'Mda' },
  publisher: 'Penguin Random House',
  isbn: '9781415209714',
  price: 'R280'
  format: 'Paperpack'
}
``` 
## Deleting Objects Properties

To delete an object's property, we can use either one of the following instructions:

```
delete object.property
delete object['property']
``` 

## Conclusion

Object properties in Javascript can also be accessed through the [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) method or updated through the [setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set) method. These methods are beyond the scope of this blog post.

I hope this article was able to introduce the concept of objects in Javascript in a basic way.

See you in future posts!

