Spring 

## Why do you use spring framework
* Dependency injection is a programming technique that makes a class independent of its dependencies. 
* It achieves that by decoupling the usage of an object from its creation. That principle improves the reusability of your code and limits the ripple effect if you need to change lower level classes. But even if you implement it perfectly, you still keep a dependency on the lower level class. The interface only decouples the usage of the lower level class but not its instantiation. At some place in your code, you need to instantiate the implementation of the interface. That prevents you from replacing the implementation of the interface with a different one.The goal of the dependency injection technique is to remove this dependency by separating the usage from the creation of the object. This reduces the amount of required boilerplate code and improves flexibility.


# What's the different type of autowire,what's the default type
* ByName
* ByType


* What's unqile exception for same type autwoire injection

* How do you work with Java-based configuration
* How to you pass the configuration parameter in spring container
* What is componet scanning 

# Spring Boot

* Spring Boot advantage
1. auto configuration: Convention over configuration 
2. Spring initializer:
3.starter : simplify the dependency management
4. embeded tmocat server
5. spring actuator: 

* @SpringBootapplication
1. @EnableAutoConfiguration : enables auto-configuration. It means that Spring Boot looks for auto-configuration beans on its classpath and automatically applies them.

2. @Configuration : It indicates that the class has @Bean definition methods by defining methods with the @Bean annotation. As a result, Spring container can process the class and produce Spring Beans to be used in the application

3. @ComponentScan : @ComponentScan without arguments indicates Spring to scan the current package and all of its sub-packages.



# Spring mvc

* What is DispatcherServlet?

1. is designed around a central Servlet that handles all the HTTP requests and responses
On receiving an HTTP request, the DispatcherServlet consults HandlerMapping (these are the configuration files) to call the appropriate Controller. Then, the controller calls appropriate service methods to set the Model data. It also returns the view name to DispatcherServlet. DispatcherServlet, with the help of ViewResolver, picks up the defined view for the request. Once the view is finalized, the DispatcherServlet passes the Model data to View – where it is finally rendered on the browser.


* What do you mean by a “Bean” in the context of Spring framework?
Any class that is initialised by the IoC container is known as a bean in Spring. The lifecycle of a Spring Bean is managed by Spring IoC Container.

* What Is the Role of the @Autowired Annotation?
The @Autowired annotation can be used with fields or methods for injecting a bean by type. This annotation allows Spring to resolve and inject collaborating beans into your bean.

*  Explain a Model Attribute
It binds a method parameter or a method return value to a named model attribute and then exposes it to a web view.

* Explain the Difference Between @Controller and @RestController?
 the @ResponseBody annotation is automatically included in the @RestController. This means that we don't need to annotate our handler methods with the @ResponseBody. 
 
 
* `@PathVariable`
1. The @PathVariable annotation is used to extract the value of the URI template.
2. 

*  `@RequestBody` and the `@ResponseBody`?
`@RequestBody` and `@ResponseBody` annotations are used to bind the HTTP request/response body with a domain object in method parameter or return type.

*  Explain Model, ModelMap and ModelAndView?
1. The Model interface defines a holder for model attributes. 
2. The ModelMap has a similar purpose, with the ability to pass a collection of values. 
3. ModelAndView is just a container for both a ModelMap and a view object. It allows a controller to return both as a single value..

* ViewResolver
The ViewResolver enables an application to render models in the browser, by mapping view names to actual views.

* validations in Spring MVC?
1. The validation is one of the most important features of Spring MVC, that is used to restrict the input provided by the user. To validate the user's input, it is required to use the Spring 4 or higher version and Bean Validation API. Spring validations can validate both server-side as well as client-side applications.
2. The @Valid annotation is used to apply validation rules on the provided object.
3. The Spring MVC Validation allows us to validate the user input in a particular sequence by using @Pattern annotation.

* `@Qualifier`
Along with @Autowired to remove the confusion by specifying which exact bean will be wired.
 
 
* What is a “Scope” in reference to Spring Beans?

1.Prototype:  it produces a new instance each and every time a bean is requested.
2.Request: Scopes a single bean definition to the lifecycle of a single HTTP request;
3. Singleton: Single bean object instance per spring IoC container of that bean. 
4. Session: Scopes a single bean definition to the lifecycle of a HTTP Session. 
5. Global-session: Scopes a single bean definition to the lifecycle of a global HTTP Session. 
