# Core Java 
* Java Collection framework
* Object Oriented Programming
* Multithreading 
* String Class
* EXCEPTION HANDLING
* 
---
# Collection Framework

## briefly Collection framework
Collection framework implements various interfaces, Collection interface and Map interface (java.util.Map) are the mainly used interfaces of Java Collection Framework.

* Collection Interface: Is root interface,every collection must implement this interface.
* List Interface: List interface extends the Collection interface, and it is an ordered collection of objects. It contains duplicate elements. It also allows random access of elements.
* Set interface: is a collection which cannot contain duplicate elements.
* Queue Interface: which stores the elements in the form FIFO 
* Map Interface:  A Map represents a key, value pair storage of elements. Map interface does not implement the Collection interface. I


## Different between List and set
* Duplicate elements
* Ordered

## Differennt between arrayList and linkedList
* ArrayList uses a dynamic array, LinkedList uses a doubly linked list.
* ArrayList is better to store and fetch data.LinkedList is better to manipulate data.
* ArrayList provides random access.LinkedList does not provide random access.
* ArrayList takes less memory overhead as it stores only object,LinkedList takes more memory overhead, as it stores the object and the address of that object.
* the insert and remove operations give good performance (O(1)) in LinkedList compared to ArrayList(O(n)). Hence if there is a requirement of frequent addition and deletion in application then LinkedList is a best choice.
* Search (get method) operations are fast in Arraylist (O(1)) but not in LinkedList (O(n)) 

## What is the difference between HashSet and TreeSet?
* HashSet maintains no order whereas TreeSet maintains ascending order.
* HashSet impended by hash table whereas TreeSet implemented by a Tree structure.
* HashSet performs faster than TreeSet.
* HashSet is backed by HashMap whereas TreeSet is backed by TreeMap.

##  What is the difference between HashSet and HashMap?
* HashSet contains only values whereas HashMap includes the entry (key, value). HashSet can be iterated, but HashMap needs to convert into Set to be iterated.
* HashSet cannot have any duplicate value whereas HashMap can contain duplicate values with unique keys.

## What is the difference between HashMap and TreeMap?
* HashMap is implemented by hash table whereas TreeMap is implemented by a Tree structure.
* HashMap may contain a null key with multiple null values whereas TreeMap cannot hold a null key but can have multiple null values.
* HashMap maintains no order, but TreeMap maintains in natural order
* HashMap is faster than TreeMap because it provides constant-time performance that is O(1),T reeMap is slow in comparison to HashMap because it provides the performance of O(log(n))

## Hashmap and Hashtable different
* HashMap is not synchronized.Hashtable is synchronized.
* HashMap can contain one null key and multiple null values.Hashtable cannot contain any null key or null value.
* HashMap is not ?thread-safe,? so it is useful for non-threaded applications.Hashtable is thread-safe, and it can be shared between various threads.


## How hash map work internally ? What's hash algorithm what's the output of hash function, what's the hash function. 

* HashMap in Java works on hashing principles. It is a data structure which allows us to store object and retrieve it in constant time O(1) 
* In hashing, hash functions are used to link key and value in HashMap.

## what's hash function
* a function which when given a key, generates an address of given value.

## Different key with hash function produce same value. How to solve the solutions. 
* two different objects will be stored in the same array location called a bucket.
* handles the collision resolution by using the concept of chaining
* When multiple keys end up in same hash code which is present in same bucket. it stores the values in a linked list

## Do you know contract between equal() and hash() methods, what's the default implementation of equal()
* If two objects are equal, then they must have the same hash code.
* If two objects have the same hash code, they may or may not be equal
* The default implementation of hashCode() in Object class returns distinct integers for distinct objects.
* The default implementation of equal(): Object class which simply checks if two Object references (say x and y) refer to the same Object.

##  Why use hashmap
* HashMap are efficient for locating a value based on a key and inserting and deleting values based on a key

## What is the difference between Comparable and Comparator?
* Comparable provides only one sort of sequence.The Comparator provides multiple sorts of sequences.
* It provides one method named compareTo().It provides one method named compare().
* The logic of sorting must be in the same class whose object you are going to sort.The logic of sorting should be in separate class to write different sorting based on different attributes of objects.

---
# Object Oriented Programming

##  What's the immutable class, why would we use immutable class
* Immutable class means that once an object is created, we cannot change its content. 
* Declare the class as final so it can't be extended.

* Simplicity - The class is in one state only
* Thread Safe - because the state cannot be changed, no synchronization is required

## Different overloading and overriding,which is compile time binding and other is run time binding
* Overloading happens at compile-time while Overriding happens at runtime: 
* overloading is being done in the same class while for overriding base and child classes are required.
* private and final methods can be overloaded but they cannot be overridden
* Static methods can be overloaded which means a class can have more than one static method of same name. Static methods cannot be overridden, 
* Parameter list should be different while doing method overloading.  should be same in method Overriding.

##  Different between abstract class and interface
* Interface supports multiple inheritance. Abstract class doesn't support multiple inheritance.
* Interface has only static and final variables. Abstract class can have final, non-final, static and non-static variables.
* Abstract class can provide the implementation of interface.Interface can't provide the implementation of abstract class.
* An interface can extend another Java interface only. An abstract class can extend another Java class and implement multiple Java interfaces.
* Abstract class can have abstract and non-abstract methods.Interface can have only abstract methods. Since Java 8, it can have default and static methods also.


## What is the difference between Polymorphism and Inheritance?

* Inheritance encourages code reusability by allowing child class to inherit behavior from the parent class. On the other hand Polymorphism allows child to redefine already defined behaviour inside the parent class.
*  Java doesn't allow multiple inheritance of classes, but allows multiple inheritance of Interface, which is actually required to implement Polymorphism
* Inheritance is basically implemented on classes.Polymorphism is basically implemented on function/methods


## Aggregation, Association and Composition

* Association: refers to how objects are related to each other and how they are using each other's functionality. 
* Composition is an Object owns another object and another object cannot exist without the owner object
* Aggregation is a weak association. An association is said to be aggregation if both Objects can exist independently.


## What is Serilazation and desrilization
* Serialization is a mechanism of converting the state of an object into a byte stream. 
* Deserialization is the reverse process where the byte stream is used to recreate the actual Java object in memory. 


---
# Multithreading 
* Have you use multithread
## What is multithreading?
* two or more threads run concurrently

## Java Thread status
* NEW - A thread that has not yet started is in this state.
* RUNNABLE - A thread executing in the Java virtual machine is in this state.
* BLOCKED - A thread that is blocked waiting for a monitor lock is in this state.
* WAITING - A thread that is waiting indefinitely for another thread to perform a particular action is in this state.
* TIMED_WAITING - A thread that is waiting for another thread to perform an action for up to a specified waiting time is in this state.
* TERMINATED - A thread that has exited is in this state.

## Thread Life-cycle
* New
* Runnable
* Running
* Non-Runnable (Blocked)
* Terminated

## How to create a thread
1. implement Runnable interface
2. extends Thread class

## The difference between the Runnable and Callable interfaces in Java
* Callable(): represents a task that is intended to be executed concurrently by a separate thread.
* A Callable can return a value but a Runnable cannot.
* A Callable can throw checked exception but a Runnable cannot.

## synchronized vs unsynchronized java

* Synchronized: only one thread can operate at same time
* Threadsafe: a method or class instance can be used by multiple threads at the same time without any problems occurring


## Differentiate between process and thread?
* threads (of the same process) run in a shared memory space, while processes run in separate memory spaces.
* Process means any program is in execution
* Thread is the segment of a process means a process can have multiple threads and these multiple threads are contained within a process.

## How to keep your thread safe
* Adding synchronized to this method
* synchronized blocks： By putting a lock inside a synchronized block, you make sure that only one thread at a time can execute this section
* Immutable class: we can create thread-safe classes by making them immutable.
* Volatile keyword in Java can also be used to instruct thread not to cache variables 
* Read-only or final variables in Java are also thread-safe in Java.

## What are differences between wait and sleep method in Java?
* Wait() releases the lock on an object , sleep() does not release lock on an object 
* Wait() is used for inter-thread communication while sleep() is used to introduce pause on execution.

## What is a volatile keyword in Java? How to use it? How is it different from the synchronized method in Java?
* Volatile in java is a keyword which is used in variable declaration only and cannot be used with method. 
* synchronization keyword is used in method declaration or can be used to create synchronization blocks.
* Volatile variables are lock free which means that it does require any lock on variable or object whereas synchronized requires lock on method or block .
* 

## Join
* Thread class provides the join() method which allows one thread to wait until another thread completes its execution.
---
# Exception Handling 

## Different Erro and Exception

* The error indicates a problem that mainly occurs due to the lack of system resources and our application should not catch these types of problems
* Exceptions are the problems which can occur at runtime and compile time. It mainly occurs in the code written by the developers

* Common errors: `java.lang.StackOverflowError`, `java.lang.OutOfMemoryError`
* Common Excepetions: Unchecked- `ArrayIndexOutOfBoundException`,`NullPointerException`, `ArithmeticException`.Checked - `IOException`,`FileNotFoundException`

## What's the check exception and uncheck exception.

* checked exceptions are forced by compiler and used to indicate exceptional conditions that are out of the control of the program (for example, I/O errors), 
* unchecked exceptions are occurred during runtime and used to indicate programming errors 

## The differences between throw and throws 
* throws clause is used to declare an exception, throw keyword is used to throw an exception explicitly.
* throw is followed by an instance variable and throws is followed by exception class names.
* Throws is used with the method signature.Throw is used within the method.
* throw keyword can throw only one exception at a time.throws keyword can be used to declare multiple exceptions,
* throw keyword we can propagate only unchecked exception, Checked exception can be propagated with throws.

## How Can We Write a Custom Exception in Java?
* Make the class extends one of the exceptions 
* Create a constructor with a String parameter, which is the detail message of the exception

---

## Java classloader
* BootStrap ClassLoader: A Bootstrap Classloader is a Machine code which kickstarts the operation when the JVM calls it. It is not a java class. Its job is to load the first pure Java ClassLoader. Bootstrap ClassLoader loads classes from the location rt.jar. Bootstrap ClassLoader doesn’t have any parent ClassLoaders. It is also called as the Primodial ClassLoader.
* Extension ClassLoader: The Extension ClassLoader is a child of Bootstrap ClassLoader and loads the extensions of core java classes from the respective JDK Extension library. It loads files from jre/lib/ext directory or any other directory pointed by the system property java.ext.dirs.
* System ClassLoader: An Application ClassLoader is also known as a System ClassLoader. It loads the Application type classes found in the environment variable CLASSPATH, -classpath or -cp command line option. The Application ClassLoader is a child class of Extension ClassLoader.
Class loader method
* loadClass(String name, boolean resolve): This method is used to load the classes which are referenced by the JVM. It takes the name of the class as a parameter. This is of type loadClass(String, boolean).


