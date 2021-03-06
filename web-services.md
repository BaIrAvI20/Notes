Web Services:

Software system designed to support interoperability (not platform dependent) machine to machine interaction over network.
Ex:  ICICI customers can withdraw money from SBI ATM.

If an application wants to use (send/get info) web service it needs to place request. After the request being placed response will be provided by ws.

Interoperability is achieved by service definition

Terminologies:

Request = input to ws
Response = output from ws
Message exchange format = XML/JSON
Service provider = ws
Service consumer = users of ws
Service definition = contract between service provider and consumer
Request/response format = (JSON/XML)
Response/request structure
End point = how to call? Where is it available?
Transport = how ws is called(queue/over Internet)?
HTTP/MQ 

Types/kinds/groups of Web services:

SOAP = possess restriction on the format of XML which is exchanged between service provider/consumer
REST = defines architectural approach

SOAP:

Simple Object Access Protocol
XML is used as exchange format

Format: Header is optional
Envelope


Header - meta info - ooptional
Body - main content

Transport: Either MQ or HTTP
Service Definition : WSDL - Web Service Definition Language
End point
All operations allowed
Request/response structure

REST:

Representational State Transfer.
Browser
Server
Response
Request


Found by Roy Fielding who is the finder of HTTP
Request and response in the format HTTP.
Request get method, and browser sends the response containing html.

Request method:

Get - get info
Post -publish info
Put - update

Response status code:

404 - page not found
200 - successful

Key Abstraction:
Resource = something to be shown or exposed to the outside world through the application.
Resource is assigned an URI- Unique Resource Identifier.
Resource representation = HTML, XML, JSON
Rest is not bothered about the resource representation

Data exchange format = no restriction
Transport = http
Service definition = no standard


Spring Framework:

It helps in creating loosely coupled applications

Group name = unique name of the group or company that created the project
Artifact id = unique name of the project

Tight coupling: when a group of classes are very closely dependent on each other

Ex: when sorting is to be done, it can either be bubble sort or quick sort algorithm so sorting is dependent on the algorithm.

Loosely coupled - interface can make it happen

Ex: Sorting also can be chosen dynamically while creating interface for deciding the also.

Bean = objects created
Using Spring:
Inputs required
What are the beans? = @Component
What are the dependencies of the beans? = @Autowired
	Autowiring takes place through the constructor = constructor injection, setter injection is 		also possible, no setter or constructor is also possible.
	Earlier suggestion: 
		optional = setter
		mandatory = constructor
Where to search for beans? = @ComponentScan (search for the package)

Application context manages the beans created and from there we can get the bean to access
Ex:  If more than one also has @Component we can use @Primary to decide on what is to be given importance with
Spring Modules:

![image](https://user-images.githubusercontent.com/69461724/158818056-f4d5af18-644c-4f86-b2a3-f0ce9687c0b1.png)





Spring is not an entire big framework
Spring is built with high modularity(modules are independent of each other)









A??Concern??is a term that refers to a part of the system divided on the basis of the functionality.

The concerns representing single and specific functionality for primary requirements are known as??core concerns.The concerns representing functionalities for secondary requirements are referred to as??crosscutting concerns or system-wide concerns.

Spring Projects:
Helps solving problems regarding enterprise applications.
Spring Boot
Spring cloud
Spring data
Spring integration

Why spring is popular?
Enables writing testable code
No plumbing code
Plumbing Code:The technical term for the code that manages data structures, persistence, inter-computer communications, database access etc. ??? all the technical details that are very necessary for an application to work, but are not application specific. By analogy, just as plumbing and electrical wiring is normally hidden from view behind the walls of a house, so ideally should such plumbing be hidden away in library classes so it does not clutter up application-specific code.
Flexible architecture - one module can be used without using other(many options available, other frameworks can also be used)
Staying updated

Spring Boot:

Very useful in building micro services
Boot enables production ready apps quickly
Provides common non functional features.
Auto Configuration - Ex:no web.xml
Embedded servers- package the server also as jar when using in linux from window
Externalized configuration - using property file

code generation is the process by which a compiler's code generator converts some intermediate representation of source code into a form that can be readily executed by a machine.

Spring boot is not providing code generation, it???s not a web or app server, it only had integration with embedded servers like tomcat

@SpringBoot Application = spring context
				Autoconfiguration
				componentscan

Spring.run() = runs spring context and returns a application context

To log the autoconfig process
logging.level.org.springframework=DEBUG


Spring vs Springboot vs Spring MVC:
 
Spring cares of dependency injection (DI) and Inversion of Control.It helps building loosely coupled apps which can be unit tested easily.

In the Spring framework, the??interface Application Context??represents the IoC container. The Spring container is responsible for instantiating, configuring and assembling objects known as beans, as well as managing their life cycles.

Spring MVC assists in developing web applications.

SpringBoot - auto configuration

Actuator:

Monitoring 
Can read metadata - how many beans created, how many times an app is called

REST services are using a service called HAL. Its in spring data.

JSON Hypertext Application Language, or HAL,??is a simple format that??gives a consistent and easy way to hyperlink between resources in our API. Including HAL within our REST API makes it much more explorable to users as well as being essentially self-documenting.
It works by returning data in JSON format which outlines relevant information about the API.
URL : localhost:8080/actuator , localhost:8080(opens Hal browser)
Gives many more info with actuator: management.endpoints.web.exposure.include = *
Spring tools eclipse plugin gives suggestion (cmmd+space / cntrl+space)
Spring boot dev tools helps to load automatically if any java change is made. It reloads only beans related to app beans and not the once related to depends because it remains the same.

RESTFUL WEB SERVICES:
org.springframework.web.HttpMediaTypeNotAcceptableException: Could not find acceptable representation = getter is missing

@RestCotroller has @ResponseBody which is mapped by message convertor to some other format, message convertor = Jaxson
@RequestBody when used as a parameter maps the posted ones with its respective fields

Status code 200= successful

To send post request rest client is required and that is postman.

Response entity is a framework of  http entity , it can return status code.

ServletUriComponentsBuilder.fromCurrentRequest() = gives the uri of the current request

To append a resource to the above one .path()
.buildAndExpand() used to replace the value within the path variable

201= status code of created

Java persistence API:

Java-objects
Database-tables

Object related impedance mismatch:
List - one table
Fields -column

@Repository in the repo class and  @Transactional in the service class is not required while using simpleJpaRepository

@Autowired is not required because if one one constructor is found by the bean it automatically autowires

@RestController = @Controller+@ResponseBody

