Java 8 

* What's the functional interface, why do we need 


* Any JDK provider functional interface

## what is Lamda expressionn
* The Lambda expression is used to provide the implementation of an interface which has functional interface.
* it is a more easy way to write instance anonymous inner class or single class which implement functional interface

## What's the stream api, what the different between stream api and collection api
* manipulate collections of data in a declarative way
* A stream pipeline consists of a source, followed by intermediate opertaions and a terminal operations

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

