Java 8 

## What is lambda expression. Why use lambad expression, 
* A lambda expression is an anonymous function. A function that doesn’t have a name and doesn’t belong to any class
* A lambda expression is a function that can be referenced and passed around as an object.
* it is a more easy way to write instance anonymous inner class or single class which implement functional interface
* it define inline implementations of functional interfaces.

## What's the stream api, what the different between stream api and collection api
* manipulate collections of data in a declarative way
* Streams bring functional programming to java
* it provides a functional approach to efficient processing collections of objects. 
* A stream pipeline consists of a source, followed by intermediate opertaions and a terminal operations
* Streams don’t change the original data structure, they only provide the result as per the pipelined methods.

|Collection|Stream|
|----------|------|
|A collection is an in-memory data structure that holds all the values the data structure currently has|a stream is a conceptually fixed data structure (you can’t add or remove elements from it) whose elements are computed on demand.|
|Collections are mainly used to store and group the data.| Streams are mainly used to perform operations on data.
|You can add to or remove elements from collections|Stream consumes a source, performs operations on it and returns a result. They don’t modify even the source|
|Collections have to be iterated externally.|Streams are internally iterated.|
|Collections can be traversed multiple times.|Streams are traversable only once.To traverse it again, you have to get new stream from the source again|
|Collections are eagerly constructed i.e all the elements are computed at the beginning itself.| streams are lazily constructed i.e intermediate operations are not evaluated until terminal operation is invoked.|

## What's the intermediate operation and terminal operations
* Lazy load
* multiple inter
* return type

## What's the flatmap()
* first maps each element using a mapping function, then flattens the result into a new array.
* is used to flatten a stream of collections to a stream of elements combined from all collections.

## How to convert list to set()
* Using HashSet or TreeSet Constructor
* Using addAll method
* Using stream in Java

##  How to remove duplicat of list()
1. Using LinkedHashSet (`addall()`)
2. Using Java 8 Stream.distinct()

---
# What's the functional interface, why do we need 

1. An interface that contains only one abstract method. 
 -  The java.util.function package in Java 8 contains many builtin functional interfaces  like Suppliers,consumers, function, prediction

2. Functional Interfaces are mainly used in Lambda expressions, Method reference and constructor references.
 - In functional programming, code can be treated as data. For this purpose Lambda expressions are introduced. They can be used to pass a block of code to another method or object.
 - Functional Interface serves as a data type for Lambda expressions. Since a Functional interface contains only one abstract method, the implementation of that method becomes the code that gets passed as an argument to another method
 
---
# default method
* Before Java 8, interfaces could have only abstract methods. The implementation of these methods has to be provided in a separate class. So, if a new method is to be added in an interface, then its implementation code has to be provided in the class implementing the same interface. 
* Allows the developer to add new methods to the interfaces without breaking their existing implementation.
---
# # Sorted method in java8 and java 6

* Java 8 provides new ways of defining Comparators by using lambda expressions and the comparing() static factory method.
```
listDevs.sort((Developer o1, Developer o2)->o1.getAge()-o2.getAge());
listDevs.sort((o1, o2)->o1.getName().compareTo(o2.getName()));		
```
```
humans.sort(Comparator.comparing(Human::getName).thenComparing(Human::getAge));
```
* Comparable is an interface defining a strategy of comparing an object with other objects of the same type.The sorting order is decided by the return value of the compareTo() method.
* Comparator is external to the element type we are comparing
