# Spring 
* Core Spring
* Sprng Boot
* Spring MVC

## what is Spring framework

Spring is the most broadly used framework for the development of Java Enterprise Edition applications. The core features of Spring can be used in developing any Java application.

* Spring framework is an open source Java platform. Spring makes use of Inversion of Control and Dependency Injection to promote good software coding practices and speed up development time.


## What Are the Benefits of Using Spring?

1. Spring comes with some of the existing technologies like ORM framework, logging framework, J2EE and JDK Timers etc, Hence we don’t need to integrate explicitly those technologies.
2. Spring WEB framework has a well-designed web MVC framework, which provides a great alternate to web framework.
3. Spring framework is both complete and modular, because spring framework has a layered architecture.
4. It gives good support for IoC and Dependency Injection results in loose coupling.

## What is IOC containter
* The container will create the objects, wire them together, configure them, and manage their complete life cycle
* The Spring container uses DI to manage the components that make up an application.

## What Is Dependency Injection?

* Dependency injection is a programming technique that makes a class independent of its dependencies. It achieves that by decoupling the usage of an object from its creation

* Dependency injection (DI) is the concept in which objects get other required objects from outside.

* It is a process whereby objects define their dependencies (that is, the other objects they work with) only through constructor arguments, arguments to a factory method, or properties that are set on the object instance after it is constructed or returned from a factory method.The container then injects those dependencies when it creates the bean

* It allows the creation of dependent objects outside of a class and provides those objects to a class through different ways. Using DI, we move the creation and binding of the dependent objects outside of the class that depends on them.

Dependency Injection, an aspect of Inversion of Control (IoC), is a general concept stating that you do not create your objects manually but instead describe how they should be created. An IoC container will instantiate required classes if needed.

## What is Tight Coupling?  What is Loose Coupling?

* When a class (ClassA) is dependent on another class’s object (ClassB), then we say ClassA is "tightly" Coupled with ClassB
* Loose Coupling removes the dependency of an object (ClassB) on a class (ClassA). Loose Coupling is approached by creating an interface and a setter & getter method, or by using a constructor which takes the interface object.

## What is bean in Spring and how to inject beans in Spring
* The Spring Beans are Java Objects that are initialized by the Spring IoC container.
1. Setter Injection
2. Constructor Injection
3. Field Injection

## Spring Bean Lifecycle
* Spring will take over the control of a bean life cycle using ApplicationContext or BeanFactory interfaces.

<img width="312" alt="Screen Shot 2020-07-30 at 10 42 58 AM" src="https://user-images.githubusercontent.com/27160394/88943713-70826880-d251-11ea-9b3b-7bc8e9b12824.png">

## What is a “Scope” in reference to Spring Beans?

1.Prototype:  it produces a new instance each and every time a bean is requested.
2.Request: Scopes a single bean definition to the lifecycle of a single HTTP request;
3. Singleton: Single bean object instance per spring IoC container of that bean. 
4. Session: Scopes a single bean definition to the lifecycle of a HTTP Session. 
5. Global-session: Scopes a single bean definition to the lifecycle of a global HTTP Session. 

---

# Spring Boot

## What is spring boot?
* Spring Boot is a project that provides a pre-configured set of frameworks to reduce boilerplate configuration so that you can have a Spring application up and running with the smallest amount of code.

* Spring-based applications have a lot of configuration (boiler-plate code). In Spring MVC, a lot of configuration is required (like component scan, dispatcher servlet, view resolver, etc). Whereas, in Spring Boot the boiler-plate code is not required.


## Benefits of Spring Boot?

1. Spring Boot provides auto-configuration: load a set of default configuration for a quick start of the application
2. Eases dependency management: Starter dependencies,Thereis is no No version conflict.
3. Embedded server:you don't need to setup a Tomcat server to run your web application. You can just write code and run it as Java application
4. The Spring Initializer provides a project generator to make you productive with the certain technology stack from the beginning
5. Spring Actuator: allows seeing inside a running application.

## Auto-configuration

the Spring Boot autoconfiguration represents a way to automatically configure a Spring application based on the dependencies that are present on the classpath. This can make development faster and easier by eliminating the need for defining certain beans that are included in the auto-configuration classes.

## What's the different type of autowire,what's the default type
* ByName
* ByType
* The default autowiring is "no". 


## What's unqile exception for same type autwoire injection

## How do you work with Java-based configuration

## How to you pass the configuration parameter in spring container


## What is componet scanning 
* Using component scan is one method of asking Spring to detect Spring managed components.
* @ComponentScan without arguments indicates Spring to scan the current package and all of its sub-packages.
* byName : Spring container looks for bean name same as property name of the class for autowiring. 
* byType : Spring container selects the bean by class type for autowiring. 
* constructor : Spring container uses constructor based autowiring. 


## @SpringBootapplication
1. @EnableAutoConfiguration : enables auto-configuration. It means that Spring Boot looks for auto-configuration beans on its classpath and automatically applies them.

2. @Configuration : It indicates that the class has @Bean definition methods by defining methods with the @Bean annotation. As a result, Spring container can process the class and produce Spring Beans to be used in the application

3. @ComponentScan : @ComponentScan without arguments indicates Spring to scan the current package and all of its sub-packages.


## Explain Spring Actuator and its advantages

Spring Actuator is a cool feature of Spring Boot with the help of which you can see what is happening inside a running application. So, whenever you want to debug your application, and need to analyze the logs you need to understand what is happening in the application right? In such a scenario, the Spring Actuator provides easy access to features such as identifying beans,


## Name Some of the Design Patterns Used in the Spring Framework?
```
Singleton Pattern: Singleton-scoped beans
Factory Pattern: Bean Factory classes
Prototype Pattern: Prototype-scoped beans
Adapter Pattern: Spring Web and Spring MVC
Proxy Pattern: Spring Aspect Oriented Programming support
Template Method Pattern: JdbcTemplate, HibernateTemplate, etc.
Front Controller: Spring MVC DispatcherServlet
Data Access Object: Spring DAO support
Model View Controller: Spring MVC
```

## Give you business logic and database], you are going to design a rest service to find all book name and insert book name and update book name

1. Create a database in MySQL
2. Then you have to create a table inside this database.
3. Add the JDBC, MySQL and web dependencies.
4.Once the project is created, you have to configure the database into application properties
5.you have to create a controller to handle the HTTP requests
6. Finally, execute this project as a Java application.
--- 


# Spring mvc

* What is DispatcherServlet?

1. is designed around a central Servlet that handles all the HTTP requests and responses

(i)  The browser sends a request to DispatcherServlet

(ii) DispatcherServlet knows the HanderMapping and can find the appropriate controllers

(iii) Controllers execute the request and put the data in the model and return back the view name to the DispatcherServlet.

(iv) DispatcherServlet uses the view name and ViewResolver to map to the view.

## What Is a Controller in Spring Mvc?
* Front Controller: provide a centralized request handling mechanism so that all requests will be handled by a single handler
* Each controller class maps one or more requests to methods that process and execute the requests with provided inputs.

## What do you mean by a “Bean” in the context of Spring framework?
Any class that is initialised by the IoC container is known as a bean in Spring. The lifecycle of a Spring Bean is managed by Spring IoC Container.

## What Is the Role of the @Autowired Annotation?
The @Autowired annotation can be used with fields or methods for injecting a bean by type. This annotation allows Spring to resolve and inject collaborating beans into your bean.

##  How Does the @Requestmapping Annotation Work?
* The @RequestMapping annotation is used to map web requests to Spring Controller methods

##  Explain a Model Attribute
It binds a method parameter or a method return value to a named model attribute and then exposes it to a web view.

## Explain the Difference Between @Controller and @RestController?
 the @ResponseBody annotation is automatically included in the @RestController. This means that we don't need to annotate our handler methods with the @ResponseBody. 
 
## `@PathVariable` and `@PathVariable`.
1. The @PathVariable annotation is used to extract the value of the URI template.
2.  @RequestParam is used to extract the data found in query parameters.

*  `@RequestBody` and the `@ResponseBody`?
`@RequestBody` and `@ResponseBody` annotations are used to bind the HTTP request/response body with a domain object in method parameter or return type.

## Explain Model, ModelMap and ModelAndView?
1. The Model interface defines a holder for model attributes. 
2. The ModelMap has a similar purpose, with the ability to pass a collection of values. 
3. ModelAndView is just a container for both a ModelMap and a view object. It allows a controller to return both as a single value..

## ViewResolver
The ViewResolver enables an application to render models in the browser, by mapping view names to actual views.

## validations in Spring MVC?
1. The validation is one of the most important features of Spring MVC, that is used to restrict the input provided by the user. To validate the user's input, it is required to use the Spring 4 or higher version and Bean Validation API. Spring validations can validate both server-side as well as client-side applications.
2. The @Valid annotation is used to apply validation rules on the provided object.
3. The Spring MVC Validation allows us to validate the user input in a particular sequence by using @Pattern annotation.

##  `@Qualifier`
Along with @Autowired to remove the confusion by specifying which exact bean will be wired.
 
 
## What is a “Scope” in reference to Spring Beans?

1.Prototype:  it produces a new instance each and every time a bean is requested.
2.Request: Scopes a single bean definition to the lifecycle of a single HTTP request;
3. Singleton: Single bean object instance per spring IoC container of that bean. 
4. Session: Scopes a single bean definition to the lifecycle of a HTTP Session. 
5. Global-session: Scopes a single bean definition to the lifecycle of a global HTTP Session. 
