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


