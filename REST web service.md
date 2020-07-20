Rest Web Service

* Do you know what's different http methods
* Do you know what's put and post methods
* What's the different http status code
* Have you design rest services
* Give you business logic and database, you are going to design a rest service to find all book name and insert book name and update book name

* In rest api ,have you authentication
* What's the different in http authentication services
* How to save the usename and password in http services
* What's the different authentication standard available
* In api design, what's the resource, we can map http and http api
* What's the noun to map http api.
* Rest api, database is down, how you can pass this exception to client side. 

* Post, put and batch different

* Model controller, if I have a request, why should I create multiple annotations on each layer, we can through this one annotation


Rest characteristics
1. It is stateless: This is the most important characteristic of a REST service. A REST HTTP request consists of all the data needed by the server to understand and give back the response. Once a request is served, the server doesn't remember if the request has arrived after a while. So the operation will be a stateless one.
2. It supports JSON and XML
3. It is simpler than SOAP
4. Client-server based architecture :Client/server architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection. This system shares computing resources.
5. Cacheable : Many developers think a technology stack is blocking their web application or API. But in reality, their architecture is the reason. The database can be a potential tuning piece in a web application. In order to scale an application well, we need to cache content and deliver it as a response. If the cache is not valid, it is our responsibility to bust it. REST services should be properly cached for scaling.
6. Multiple layered system : The REST API can be served from multiple servers. One server can request the other, and so forth. So when a request comes from the client, request and response can be passed between many servers to finally supply a response back to the client. This easily implementable multi-layered system is always a good strategy for keeping the web application loosely coupled.
7. Representation of resources : The REST API provides the uniform interface to talk to. It uses a Uniform Resource Identifier (URI) to map the resources (data). It also has the advantage of requesting a specific data format as the response. The Internet Media Type (MIME type) can tell the server that the requested resource is of that particular type.



The main strategy interface for authentication is AuthenticationManager which only has one method: Authentication authenticate(Authentication authentication);
An AuthenticationManager can do one of 3 things in its authenticate() method:
-return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.
-throw an AuthenticationException if it believes that the input represents an invalid principal.
-return null if it can’t decide.


REST API

* difference betweenn rest and soap
1.SOAP is a protocol. REST is an architectural style.
2. SOAP web services and client programs are bind with WSDL contract,REST doesn't have any contract defined between server and client
3. REST permits many different data formats including plain text, HTML, XML, and JSON, which is a great fit for data and yields more browser compatibility; SOAP only uses XML.
4. REST calls can be cached, SOAP-based calls cannot be cached.
5. SOAP web services are hard to maintain, any change in WSDL contract requires us to create client stubs again,REST web services are easy to maintain when compared to SOAP, a new method can be added without any change at client side for existing resources.
6. SOAP is more secure than REST as it uses WS-Security for transmission along with Secure Socket Layer.

* features of RESTful web services.

1. Based on the Client-Server representation.
2. Based on the concept of statelessness where every client request and the response is independent of the other with complete assurance of providing required information.
3. Uses the concept of caching.

* @pathvariable and @requestparam
1. @RequestParam used for accessing the values of the query parameters , @PathVariable used for accessing the values from the URI template.

* Statelessness
 a RESTful Web Service should not keep a client state on the server. This restriction is called Statelessness
1. Any previous communication with the client and server is not maintained and thus the whole process is very much simplified.
2. Every method required for communication is identified as an independent method i.e. there are no dependencies to other methods.

* whar is payload
 The request data which is present in the body part of every HTTP message is referred to as ‘Payload’. In Restful web service, the payload can only be passed to the recipient through the POST method.


* What is Caching?

 Caching is the process in which server response is stored so that a cached copy can be used when required and there is no need for generating the same response again

 *  What is a ‘Resource’?
 Just like the ‘Object’ instance, we have learned in Object Orient Programming Language, in the same way, ‘Resource’ is defined as an object of a type which can be an image, HTML file, text data, and any type of dynamic data.

* Is there any difference between PUT and POST operations? Explain it.
A PUT operation is idempotent while the POST operation can give a different result.
the same PUT request multiple times will always produce the same result(that is no side effect), while on the other hand, calling a POST request repeatedly may have (additional) side effects of creating the same resource multiple times.


*  What is URI? Explain its purpose in REST-based web services. What is its format?

URI stands for Uniform Resource Identifier. URI is the identifier for the resource in REST architecture.

The purpose of a URI is to locate a resource(s) on the server hosting the web service. A URI is of the following format-

<protocol>://<service-name>/<ResourceType>/<ResourceID>

* HTTP status code
1. Informational responses (100–199), 100 Continue,101 Switching Protocols
2. Successful responses (200–299),200 OK,201 Created
3. Redirects (300–399),300 Multiple Choices
4. Client errors (400–499), 400 Bad Request,404 Not Found,403 Forbidden,405 Method Not Allowed
5. Server errors (500–599).500 Internal Server Error,503 Service Unavailable,504 Gateway Timeout

