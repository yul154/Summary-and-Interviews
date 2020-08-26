# Core Java 
* Basic Java Knowledge
* Java Collection framework
* Object Oriented Programming
* Multithreading 
* String Class
* EXCEPTION HANDLING

---
## Can you explain what JVM is? Can you use this on any platform that you choose?
* JVM stands for Java Virtual Machine. You need the JVM to run any Java application. Without it, the application fails and the user is unable to access it.

## Just In Time compiler 
* Java uses Just In Time compiler to enable high performance. It is used to convert the instructions into bytecodes.
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

* HashMap in Java works on hashing principles. 
* It is a data structure which allows us to store object and retrieve it in constant time O(1) provided we know the key. 
* In hashing, hash functions are used to link key and value in HashMap. Objects are stored by calling put(key, value) method of HashMap and retrieved by calling get(key) method. When we call put method, the hashcode() method of the key object is called so that the hash function of the map can find a bucket location to store value object.
* Hashing in its simplest form, is a way to assigning a unique code for any variable/object after applying any formula/algorithm on its properties.
* Hash function should return the same hash code each and every time when the function is applied on same or equal objects


## How does HashSet is implemented in Java, How does it use Hashing?

* HashSet is built on top of HashMap. If you look at source code of java.util.HashSet class, you will find that that it uses a HashMap with same values for all keys, 

* HashSet uses HashMap internally to store it’s objects. Whenever you create a HashSet object, one HashMap object associated with it is also created. This HashMap object is used to store the elements you enter in the HashSet. The elements you add into HashSet are stored as keys of this HashMap object. The value associated with those keys will be a constant.

## what's hash function
* a function which when given a key, generates an address of given value.
* Hash function should return the same hash code each and every time when the function is applied on same or equal objects

## Different key with hash function produce same value. How to solve the solutions. 
* at some point in time hash function will return the same bucket location for two different keys, this is called collision in HashMap
* In this case, a linked list is formed at that bucket location and a new entry is stored as the next node.
*  If we try to retrieve an object from this linked list, we need an extra check to search the correct value, this is done by equals() method
* HashMap keeps comparing entry's key object with the passed key using equals() and when it returns true, Map returns the corresponding value.
* If two keys of HashMap return the same hash code, then they will end up in the same bucket; hence collision will occur. They will be stored in a linked list together.
* handles the collision resolution by using the concept of chaining
* equals() will be used to distinguish them. Each bucket can contain a list of objects with the same hash code.

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

## How do you Sort objects on the collection?

Sorting is implemented using Comparable and Comparator in Java and when you call Collections.sort() it gets sorted based on the natural order specified in compareTo() method while Collections.sort(Comparator) will sort objects based on compare() method of Comparator. 

# Strinng

## Difference between String, String Builder, and String Buffer.
* The String class is an immutable class 
*  whereas StringBuffer and StringBuilder classes are mutable
* StringBuffer is synchronized i.e. thread safe. It means two threads can't call the methods of StringBuffer simultaneously.
* StringBuilder is non-synchronized i.e. not thread safe.


## String Pool
* The Java string constant pool is an area in heap memory where Java stores literal string values
* When we use double quotes to create a String, it first looks for String with the same value in the String pool, if found it just returns the reference else it creates a new String in the pool and then returns the reference.

##  How many Strings are getting Created in the String Pool?
`String str = new String("Cat");`

* If there is already a string literal “Cat” in the pool, then only one string “str” will be created in the pool. 
* If there is no string literal “Cat” in the pool, then it will be first created in the pool and then in the heap space, so a total of 2 string objects will be created.

## Difference between String literal and New String object in Java
* When you create String object using new() operator, it always create a new object in heap memory.
* if you create object using String literal syntax. it may return an existing object from String pool,if it's already exists. Otherwise it will create a new string object and put in string pool for future reuse.

```
String a = "xyz"// When we use double quotes to create a String, it first looks for String with the same value in the String pool, if found it just returns the reference else it creates a new String in the pool and then returns the reference.

String b = new String("xyz")// force JVM to create a new String reference, even if "xyz" is in its pool.

System.out.println(a == b); false //different objects are created and they have different references:
```

<img width="367" alt="Screen Shot 2020-07-29 at 10 46 40 AM" src="https://user-images.githubusercontent.com/27160394/88821903-d1923980-d188-11ea-8fbf-f888e825093c.png">

---
# Object Oriented Programming

## What Are OOP Concepts in Java?

* Object-oriented programming System(OOPs) is a programming paradigm based on the concept of “objects” that contain data and methods.
* Object oriented programming brings together data and its behaviour(methods) in a single location(object) makes it easier to understand how a program works.
* There are four main OOP concepts in Java
1. Abstraction: Abstraction is a process where you show only “relevant” data and “hide” unnecessary details of an object from the user. In java, abstraction is achieved by interfaces and abstract classes
2. Encapsulation: keeping fields within a class private, then providing access to them via public methods. It’s a protective barrier that keeps the data and code safe within the class itself.
3. Inheritance:  It lets programmers create new classes that share some of the attributes of existing classes. 
4. Polymorphism:  lets programmers use the same word to mean different things in different contexts. Two form of polymorphism, method overloading,method overriding

## 	What is polymorphism mean ? How to implement it in code
* Polymorphism is Subclasses of a class can define their own unique behaviors and yet share some of the same functionality of the parent class.
* Polymorphism in Java has two types: Compile time polymorphism (static binding, overloading) and Runtime polymorphism (dynamic binding, overriding)
* Covariant return type: You can override a method with the same signature but returns a subclass of the object returned.

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
* Classes that implement the interface should provide the implementation for all the methods.
* Interface has only static and final variables. Abstract class can have final, non-final, static and non-static variables.
* Abstract class can provide the implementation of method. Interface can't provide the implementation of abstract class.
* An interface can extend another Java interface only. An abstract class can extend another Java class and implement multiple Java interfaces.
* Abstract class can have abstract and non-abstract methods.Interface can have only abstract methods. Since Java 8, it can have default and static methods also.

## What is meant by Abstract class?
* We can create the Abstract class by using the “Abstract” keyword before the class name. An abstract class can have both “Abstract” methods and “Non-abstract” methods that are a concrete class.

## What is meant by Interface?
* Multiple inheritances cannot be achieved in java. To overcome this problem Interface concept is introduced.
* An interface is a template which has only method declarations and not the method implementation.

## What is the difference between Polymorphism and Inheritance?

* Inheritance encourages code reusability by allowing child class to inherit behavior from the parent class. On the other hand Polymorphism allows child to redefine already defined behaviour inside the parent class.
*  Java doesn't allow multiple inheritance of classes, but allows multiple inheritance of Interface, which is actually required to implement Polymorphism
* Inheritance is basically implemented on classes.Polymorphism is basically implemented on function/methods

## What is an Object?
* An instance of a class is called an object. The object has state and behavior.

Whenever the JVM reads the “new()” keyword then it will create an instance of that class.


## Difference between Default and Protected access specifiers.
* The protected data members,protected methods of a class will be visible to the other Classes if they resides in same package
* Default restricts the access only to package level , even after extending the class having default data members ,we won't be able to access.

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

## What is a Thread?
* In Java, the flow of execution is called Thread
* Every java program has at least one thread called the main thread, the main thread is created by JVM. Th
*  The user can define their own threads by extending the Thread class (or) by implementing the Runnable interface. 
* Threads are executed concurrently.
## Java Thread status
* NEW - A thread that has not yet started is in this state.
* RUNNABLE - A thread executing in the Java virtual machine is in this state.
* BLOCKED - A thread that is blocked waiting for a monitor lock is in this state.
* WAITING - A thread that is waiting indefinitely for another thread to perform a particular action is in this state.
* TIMED_WAITING - A thread that is waiting for another thread to perform an action for up to a specified waiting time is in this state.
* TERMINATED - A thread that has exited is in this state.

## Thread Life-cycle
* New:  A Thread instance has been created but start () method is not yet invoked
* Runnable: The Thread is in the runnable state after the invocation of the start () method, but before the run () method is invoked
* Running: The thread is in running state after it calls the run () method. Now the thread begins the execution.
* Non-Runnable (Blocked): The thread is alive but it is not eligible to run
* Terminated:Once the run method is completed then it is terminated.

## How to create a thread
1. implement Runnable interface
2. extends Thread class

## Explain about join () method.
* Join () method is used to join one thread with the end of the currently running thread.

## What does the yield method of the Thread class do?
*  A yield () method moves the currently running thread to a  runnable state and allows the other threads for execution

## Explain about wait () method.
* wait () method is used to make the thread to wait in the waiting pool.
* When the wait () method is executed during a thread execution then immediately the thread gives up the lock on the object and goes to the waiting pool.
* Wait () method tells the thread to wait for a given amount of time.
* the thread will wake up after notify () (or) notify all () method is called.

## Difference between notify() method and notifyAll() method in Java.
* `notify()`: used to send a signal to wake up a single thread in the waiting pool.
* `norifyAll()`: This method sends the signal to wake up all the threads in a waiting pool.

## The difference between the Runnable and Callable interfaces in Java
* Callable(): represents a task that is intended to be executed concurrently by a separate thread.
* A Callable can return a value but a Runnable cannot.
* A Callable can throw checked exception but a Runnable cannot.

## Difference between start() and run() method of thread class.

* `Start()` method creates a new thread and the code inside the run () method is executed in the new thread. 
* If we directly called the `run()` method then a new thread is not created and the currently executing thread will continue to execute the run() method.

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

---
# Exception Handling 

##  What is meant by Exception?
* An Exception is a problem that can occur during the normal flow of execution.

## What's the check exception and uncheck exception.

* checked exceptions: These exceptions are checked by the compiler at the time of compilation.Checked Exceptions must either declare the exception using throws keyword (or) surrounded by appropriate try/catch.

* unchecked exceptions are occurred during runtime and used to indicate programming errors 


## How to handle exception?
* Try-Catch-Finally：
1. a try block that encloses the code section which might throw an exception,
2. one or more catch blocks that handle the exceptions
3. The finally block gets executed after the successful execution of the try block or after one of the catch blocks handled an exception

* By declaring throws keyword:At the end of the method, we can declare the exception using throws keyword.
## if return in catch block, finally block will execute ？ 
If try/catch blocks have a return statement, even then the finally block executes!
* If finally block has a return statement, then the return statements from try/catch blocks will be overridden.

```
howdy from catch block
howdy from Finally block
returning from catch block
```

## 	Any scenario, the final will not execute
1. if you call System.exit()
2. if the JVM crashes first
3. if there is an infinite loop in the try block


## Different Error and Exception

* The error indicates a problem that mainly occurs due to the lack of system resources and our application should not catch these types of problems
* Exceptions are the problems which can occur at runtime and compile time. It mainly occurs in the code written by the developers

* Common errors: `java.lang.StackOverflowError`, `java.lang.OutOfMemoryError`
* Common Excepetions: Unchecked- `ArrayIndexOutOfBoundException`,`NullPointerException`, `ArithmeticException`.Checked - `IOException`,`FileNotFoundException`


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


## What's design patterns you used

```
In my project I had used MVC, Singleton, Factory, Iterator and Template pattern.
The project divided into 3 section UI, Business, Data Access layer.
MVC Pattern: I had used at the presentation so model separated by controller.
Singleton Pattern: To share common data access throughout the application.
Factory Pattern: Between each layer for decoupling and centralizing object creation to avoid code complication.
Iterator Pattern: For Providing tight encapsulation through middle tier object.
Observer Pattern: For Sending notification to subscribed users.
Facade Pattern: For delegating client requests to appropriate subsystem objects eg. The consumer calls one number and speaks with a customer service representative. The customer service representative acts as a Facade, providing an interface to the order fulfillment department, the billing department, and the shipping department.
Template Pattern: For consistence vocabulary and naming convention for business objects.
```
* Singleton: used to limit creation of a class to only one object. when one (and only one) object is needed to coordinate actions across the system.
* Factory Pattern: it does so without specifying the exact class of the object to be created. To accomplish this, objects are created by calling a factory method instead of calling a constructor. without necessarily knowing what kind of object it creates or how to create it.
* Observer: one-to-many dependency between objects so that when one object changes state, all its dependents are notified.It is used when there is one to many relationship between objects such as if one object is modified, its dependent objects are to be notified automatically and corresponding changes are done to all dependent objects.
* An Adapter pattern:  acts as a connector between two incompatible interfaces that otherwise cannot be connected directly


### decorative design pattern
* Decorator pattern allows a user to add new functionality to an existing object without altering its structure.
* This pattern creates a decorator class which wraps the original class and provides additional functionality keeping class methods signature intact.
* Decorator design patterns create decorator classes, which wrap the original class and provide additional functionality by keeping the class methods' signature unchanged.
* Decorator design pattern uses abstract classes or interfaces with the composition to implement the wrapper.
