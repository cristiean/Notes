# Web Services - Notes

## Web Service
- A **FUNCTION** that can be used by **other programs over the web(http)**

- HTML - intended for human consumption
- XML, JSON - for other applications
- REST (Represetational State STransfer)

Example:
1) Use webserver to retrieve info about books on Amazon
2) Use webserver to submit an order to Amazon
3) Create webservices to allow outside application to find product information from within your company
4) Create webservices to allow outside applications to submit orders to your company

- REQUEST/RESPONSE mechanism 
- Allows remote client to ACCESS and MODIFY data

## URL (Uniform Resource Locator)
- (web address)
- A reference to a **web resource**
- A specific type of URI

| PROTOCOL |       | HOSTNAME        |    | FILE NAME  | 
|:--------:|:-----:|:---------------:|:--:|:----------:|
| http     | :\/\/ | www.example.com | \/ | index.html |

## URI (Uniform Resource Identifier)
- String of characters that unambiguously identifies a particular RESOURCE
- Syntax rules for UNIFORMITY
- Hierarchical naming scheme ("\/") providing EXTENSIBILITY

## Uniform Interface
- HTTP Requests (list of methods with fixed semantics):
    - POST
    - GET
    - PUT
    - DELETE
    - OPTIONS
    - HEAD
    - TRACE
- HTTP Requests are dissimilar to SOAP-based web services where semantics are application-specific

## Hypermedia and Application State
- User changes the application's state by clicking buttons and links in the (HTML) representation

## HTTP Visibility
- HTTP interactions are STATELESS (infering meaning regardless of past or future interactions)
- HTTP uses Uniform Interface (each operation operating on one and only one resource at a time and always having the same function regardless of application)
- HTTP uses a MIME-like envelope format with a BODY and a HEADER. Headers are visible and except the software that creates the message and the software that processes the message all software in between can treat the body as opaque

## Web resource
- Identifiable thing, wether digital, physical or abstract
- Anything that can be identified by a URI
- On a typical website, every page is a resource

## Representation
- HTML document that the server returns to the client
- An encapsulation of the information of the resource

## Distributed computing
- Distributed systems 
- System whose components are located on different **networked computers**
- These computers communicate their actions by **passing messages** to one another
    - Lack of global clock
    - Concurrency of components
    - Independent failure of components

## Web service
- Software system designed to support interoperable machine-to-machine interaction over a network

## Web server
- Store, process and deliver web pages to clients using HTTP

## Server framework (a.k.a. Web Application Framework)
- Help the development of web applications
- Examples:
    - URL routing to handlers
    - Interacting with databases
    - Supporting sessions
    - User authorisation

## Client-Server architecture model
- Distributed application, server await for client requests
- Servers share data with which the clients run

## HTTP (Hypertext Transfer Protocol)
- Application protocol

## Hypertext
- Text shown on a computer display or other electronic device wit references (hyperlinks) to other text that the user can immediately access

## HTML (Hypertext Markup Language)
- Web browsers receive HTML files from the server or local machine
- The browsers then render the documents into multimedia web pages

## REST (Representational State Transfer)
- Defines a set of constraints to be used for creating Web Services that are RESTful (RWS - RESTful Web Services)
- These provide interoperability between computers on the internet
- RWSs allow the requesting systems to ACCESS and MANIPULATE RESOURCES as TEXTUAL REPRESENTATIONS, using a UNIFORM and PREDEFINED set of STATELESS OPERATIONS

- **Metadata** and  **Headers** sent to enable payload delivery
### Payload
- **Intended message**
- Part of the transmitted data

SOAP services expose their own arbitrary set of operations

REQUEST MADE TO URI -> ELICITS RESPONSE with payload formatted in HTML, XML,...

## CRUD (Create, Read, Update, Delete)
- Four basic functions of persistent storage
### Persistent storage
- Persistence refers to the characteristic of state that OUTLIVES THE PROCESS THAT CREATED IT
