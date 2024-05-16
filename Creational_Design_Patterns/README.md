# Creational Design Patterns:

Creational patterns deal with the process of creation of objects of classes.

### Why do we need creational design patterns?

A good example where we can use creational DPs are when our object needs multiple other objects before it can be created.
There may be multiple steps that are needed before we can create an object. Eg:
* read some data from a file
* query a URL to get some data and from that we have to create our final object
* requirement to have only one object of a class in the entire app - that class may be representing something like a configuration.