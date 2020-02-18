# Week 3: JavaScript Object Creation

![](.gitbook/assets/image%20%287%29.png)

Classes

* In JavaScript, classes work on a delegation framework instead of inheritance: if a property can’t be found in an object, JS looks for that property in a delegate object
* Delegation can be chained

Prototypes

* Objects that are used by other objects to add delegate properties
* Are not super classes - no instances are created
  * An object will just have a reference to its prototype
  * Multiple objects can have the same prototype object reference
  * No copies are made
* Main purpose: fast object creation

Object Creation Using Functions

* Similar to constructors in java
* Functions have their own prototype property used for object creation

Method 1:

“new” Keyword

4 things that “new” does:

1. Creates an empty object
2. Adds the constructor prototype to that object
3. Call the constructor function with “this” set to the new object
4. Return the object

**\_\_proto\_\_** is the property of an _object_ that points to the object's prototype vs. **prototype** is the property of a _function_ that is used as the prototype to add the new object when that function is called as a constructor 

The difference between prototype and \_\_proto\_\_ is that the former is a property of a class constructor, while the latter is a property of a class instance

Method 2: Object.create\(o\)

* Creates an object with o as the prototype
* Can create multiple objects with the same reference

“class” Keyword

* Not really creating a class
* E.g. typeof\(\) = “function”

