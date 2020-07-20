# Core Java 

* What's the immutable class, why would we use immutable class

* How hash map work internally ? What's hash algorithm what's the output of hash function, what's the hash function. 

* Different key with hash function produce same value. How to solve the solutions. 

* Do you known contract between equal() and hash() methods, what's the default implementation of equal()


* Different overloading and overriding,which is compile time binding and other is run time binding

* Different between abstract class and interface
* multiple inheritance and interface
* What is Serilazation and desrilization
* What's the check exception and uncheck exception.
* Collection list and set different
* Hashmap and hashtable different
*  Why use hashmap
*  Have you use multithread
* How to keep your thread safe


Java classloader
BootStrap ClassLoader: A Bootstrap Classloader is a Machine code which kickstarts the operation when the JVM calls it. It is not a java class. Its job is to load the first pure Java ClassLoader. Bootstrap ClassLoader loads classes from the location rt.jar. Bootstrap ClassLoader doesn’t have any parent ClassLoaders. It is also called as the Primodial ClassLoader.
Extension ClassLoader: The Extension ClassLoader is a child of Bootstrap ClassLoader and loads the extensions of core java classes from the respective JDK Extension library. It loads files from jre/lib/ext directory or any other directory pointed by the system property java.ext.dirs.
System ClassLoader: An Application ClassLoader is also known as a System ClassLoader. It loads the Application type classes found in the environment variable CLASSPATH, -classpath or -cp command line option. The Application ClassLoader is a child class of Extension ClassLoader.
Class loader method
loadClass(String name, boolean resolve): This method is used to load the classes which are referenced by the JVM. It takes the name of the class as a parameter. This is of type loadClass(String, boolean).


# Different between hashmap and hashtable
* Hashtable is synchronized, whereas HashMap is not. This makes HashMap better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones.

* Hashtable does not allow null keys or values.  HashMap allows one null key and any number of null values.

* One of HashMap's subclasses is LinkedHashMap, so in the event that you'd want predictable iteration order (which is insertion order by default), you could easily swap out the HashMap for a LinkedHashMap. This wouldn't be as easy if you were using Hashtable.

# Aggregation, Association and Composition

Dependency from A to B means that A uses B but indirectly (say by receiving instances of it and forwarding them to other objects).

Association from A to B means that A uses B directly, (for example by calling methods)

Aggregation from A to B means that B is part of A (semantically) but B can be shared and if A is deleted, B is not deleted. Note that this says nothing about how the "is part" is implemented.

Composition from A to B is like Aggregation, where B cannot be shared and if A is deleted, all of its aggregates (Bs) are deleted also.

# What is the difference between polymorphism and inheritance?

* Inheritance encourages code reusability by allowing child class to inherit behavior from the parent class. On the other hand Polymorphism allows child to redefine already defined behaviour inside the parent class.
*  Java doesn't allow multiple inheritance of classes, but allows multiple inheritance of Interface, which is actually required to implement Polymorphism
