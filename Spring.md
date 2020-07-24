Spring 

## Why do you use spring framework
* Dependency injection is a programming technique that makes a class independent of its dependencies. 
* It achieves that by decoupling the usage of an object from its creation. 
* you do not have to create your objects but have to describe how they should be created. You don’t connect your components and services together in the code directly, but describe which services are needed by which components in the configuration file. The IoC container will wire them up together.


# What's the different type of autowire,what's the default type
* ByName
* ByType
* The default autowiring is "no". 


# What's unqile exception for same type autwoire injection

* How do you work with Java-based configuration

## How to you pass the configuration parameter in spring container


## What is componet scanning 
* Using component scan is one method of asking Spring to detect Spring managed components.
* @ComponentScan without arguments indicates Spring to scan the current package and all of its sub-packages.
* byName : Spring container looks for bean name same as property name of the class for autowiring. 
* byType : Spring container selects the bean by class type for autowiring. 
* constructor : Spring container uses constructor based autowiring. 

# Spring Boot

## Spring Boot advantage
1. auto configuration: Convention over configuration 
2. Spring initializer:
3.starter : simplify the dependency management
4. embeded tmocat server
5. spring actuator: 

## @SpringBootapplication
1. @EnableAutoConfiguration : enables auto-configuration. It means that Spring Boot looks for auto-configuration beans on its classpath and automatically applies them.

2. @Configuration : It indicates that the class has @Bean definition methods by defining methods with the @Bean annotation. As a result, Spring container can process the class and produce Spring Beans to be used in the application

3. @ComponentScan : @ComponentScan without arguments indicates Spring to scan the current package and all of its sub-packages.



## Spring mvc

* What is DispatcherServlet?

1. is designed around a central Servlet that handles all the HTTP requests and responses

2. On receiving an HTTP request, the DispatcherServlet consults HandlerMapping (these are the configuration files) to call the appropriate Controller. Then, the controller calls appropriate service methods to set the Model data. It also returns the view name to DispatcherServlet. DispatcherServlet, with the help of ViewResolver, picks up the defined view for the request. Once the view is finalized, the DispatcherServlet passes the Model data to View – where it is finally rendered on the browser.


## What do you mean by a “Bean” in the context of Spring framework?
Any class that is initialised by the IoC container is known as a bean in Spring. The lifecycle of a Spring Bean is managed by Spring IoC Container.

## What Is the Role of the @Autowired Annotation?
The @Autowired annotation can be used with fields or methods for injecting a bean by type. This annotation allows Spring to resolve and inject collaborating beans into your bean.

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
