# Rest Web Service

## What are RESTful webservices? 
REST is a stateless client-server architecture where web services are resources and can be identified by their URIs. Client applications can use HTTP GET/POST methods to invoke Restful web services.

## What is REST API?

 * Representational State Transfer a.k.a REST is an architectural style as well as an approach for communications purpose that is often used in various web services development.
 * It defines a set of principles that a system must comply with in order to get some benefits such as loose coupling between the client and the server, scalability, reliability, and better performance.
 * In REST architecture, a REST Server simply provides access to resources and REST client accesses and modifies the resources. Here each resource is identified by URIs/ global IDs. 
 * REST uses various representation to represent a resource like text, JSON, XML. JSON is the most popular one.
 
In most cases, the design of a so-called RESTful API consists of:
 * defining the resources accessible via HTTP
 * identifying such resources with URLs
 * mapping the CRUD (Create, Retrieve, Update, Delete) operations on these resources to the standard HTTP methods (POST, GET, PUT, DELETE)

##  Difference betweenn rest and soap

1. SOAP is a protocol. REST is an architectural style.
2. SOAP web services and client programs are bind with WSDL contract,REST doesn't have any contract defined between server and client
3. REST permits many different data formats including plain text, HTML, XML, and JSON, which is a great fit for data and yields more browser compatibility; SOAP only uses XML.
4. REST calls can be cached, SOAP-based calls cannot be cached.
5. SOAP web services are hard to maintain, any change in WSDL contract requires us to create client stubs again,REST web services are easy to maintain when compared to SOAP, a new method can be added without any change at client side for existing resources.
6. SOAP is more secure than REST as it uses WS-Security for transmission along with Secure Socket Layer.


# Rest characteristics

1. It is stateless: In REST applications, each request must contain all of the information necessary to be understood by the server, rather than be dependent on the server remembering prior requests.The server does not store any state about the client session on the server-side. Statelessness enables greater scalability since the server does not have to maintain, update or communicate that session state

2.Uniform Interface: constraint defines the interface between clients and servers. It simplifies and decouples the architecture, which enables each part to evolve independently. 


4. Client-server based architecture :Client/server architecture is a computing model in which the server hosts, delivers and manages most of the resources and services to be consumed by the client. This type of architecture has one or more client computers connected to a central server over a network or internet connection. This system shares computing resources.

5. Cacheable : As the clients can cache responses, they need to be implicitly or explicitly defined as cacheable or not to prevent clients from reusing state or inappropriate data in response to further requests. 

6. Multiple layered system : The REST API can be served from multiple servers. One server can request the other, and so forth. So when a request comes from the client, request and response can be passed between many servers to finally supply a response back to the client. This easily implementable multi-layered system is always a good strategy for keeping the web application loosely coupled.
7. Representation of resources : The REST API provides the uniform interface to talk to. It uses a Uniform Resource Identifier (URI) to map the resources (data). It also has the advantage of requesting a specific data format as the response. The Internet Media Type (MIME type) can tell the server that the requested resource is of that particular type.

##  features of RESTful web services.

1. Stateless

2. Uniform Interface

3. Client-Server

4. Cacheable

5. Layered System


## 	What is query parameters
* You can use query parameters to control what data is returned in endpoint responses.

## @pathvariable and @requestparam
1. @RequestParam used for accessing the values of the query parameters , @PathVariable used for accessing the values from the URI template.

##  Statelessness
 a RESTful Web Service should not keep a client state on the server. This restriction is called Statelessness
1. Any previous communication with the client and server is not maintained and thus the whole process is very much simplified.
2. Every method required for communication is identified as an independent method i.e. there are no dependencies to other methods.

##  whar is payload
 The request data which is present in the body part of every HTTP message is referred to as ‘Payload’. In Restful web service, the payload can only be passed to the recipient through the POST method.


## What is Caching?
* Caching refers to storing server response in client itself so that a client needs not to make server request for same resource again and again

##  What is a ‘Resource’?
Just like the ‘Object’ instance, we have learned in Object Orient Programming Language, in the same way, ‘Resource’ is defined as an object of a type which can be an image, HTML file, text data, and any type of dynamic data.


# What is URI? Explain its purpose in REST-based web services. What is its format?

URI stands for Uniform Resource Identifier. URI is the identifier for the resource in REST architecture.

The purpose of a URI is to locate a resource(s) on the server hosting the web service. A URI is of the following format-

<protocol>://<service-name>/<ResourceType>/<ResourceID>

## What is messaging in RESTful webservices?
Messaging: A client sends a message in form of a HTTP Request and the server responds in the form of an HTTP Response

# Security in REST

## Give you business logic and database, you are going to design a rest service to find all book name and insert book name and update book name

##  What's the different in http authentication services

The main strategy interface for authentication is AuthenticationManager which only has one method: Authentication authenticate(Authentication authentication);
An AuthenticationManager can do one of 3 things in its authenticate() method:
-return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.
-throw an AuthenticationException if it believes that the input represents an invalid principal.
-return null if it can’t decide.


##  How to save the usename and password in http services

##  What's the different authentication standard available


# HTTP METHODS

## Post, put and batch different
The word "idempotent" means that any number of repeated, identical requests will leave the resource in the same state.
* POST is always for creating a resource ( does not matter if it was duplicated )
* PUT is for checking if resource is exists then update , else create new resource
* PATCH is always for update a resource
*  POST is NOT idempotent. GET , PUT , DELETE , HEAD , OPTIONS and TRACE are idempotent.A PATCH is not necessarily idempotent


##  Do you know what's different http methods


## What are the core components of a HTTP Request?

1. Verb − Indicates the HTTP methods such as GET, POST, DELETE, PUT, etc.
2. URI − Uniform Resource Identifier (URI) to identify the resource on the server.
3. HTTP Version − Indicates the HTTP version.
4. Request Header − Contains metadata for the HTTP Request message as key-value pairs.
5. Request Body − Message content or Resource representation.

## What are the core components of a HTTP response?

1. Status/Response Code − Indicate Server status for the requested resource. For example 404 means resource not found and 200 means response is ok.
2. HTTP Version − Indicate HTTP version, for example HTTP v1.1 .
3. Response Header − Contains metadata for the HTTP Response message as key-value pairs. For example, content length, content type, response date, server type etc.
4. Response Body − Response message content or Resource representation.


##  HTTP status code
1. Informational responses (100–199), 100 Continue,101 Switching Protocols
2. Successful responses (200–299),200 OK,201 Created
3. Redirects (300–399),300 Multiple Choices
4. Client errors (400–499), 400 Bad Request,404 Not Found,403 Forbidden,405 Method Not Allowed
5. Server errors (500–599).500 Internal Server Error,503 Service Unavailable,504 Gateway Timeout

##  Is there any difference between PUT and POST operations? Explain it.
A PUT operation is idempotent while the POST operation can give a different result.
the same PUT request multiple times will always produce the same result(that is no side effect), while on the other hand, calling a POST request repeatedly may have (additional) side effects of creating the same resource multiple times.

## In api design, what's the resource, we can map http and http api

## What's the noun to map http api.

##  Rest api, database is down, how you can pass this exception to client side. 
