# Full Stack Programming Terms Definitions
<ref: https://www.linkedin.com/pulse/tech-recruiting-frontend-backend-middleware-server-side-pandey/>

---

## Front End 
Software’s presentation layer, essentially the user interface (UI) and User Experience (UX). 
This is basically what elements of the software are visible by the end user and what their interactions with the system will be. 
Typically we want this to look good and user friendly so front end developers often have web design skills and can find their way around design tools like Photoshop. 
Typically code used here will include HTML, Javascript and CSS along with framework tools like Jquery and Bootstrap. 
This enables the developer to build the screen layouts, menus, folders, buttons and all the other bits that the user will see on their screen when using the software.

## Back End
Software’s data tier or persistence layer. Typically this is the database(s) that the software is built on which is not directly presented to the user. 
So once a user requests data, clicks on an option or issues a command of some sort through the UI, this is where the data is stored, found by the software, retrieved and then displayed back to the user. 
It basically serves up the requested information. Typically code used here will include PHP, C, C++, C#, Python and .Net along with a tool that communicates with the database such as MySQL. 
This enables the developers to build applications that can efficiently and quickly search, locate and present data.

## Middleware
Essentially Middleware links the front and back end of the system together acting as a bridge between the front and back end. 
It is often referred to as the glue between the data and the UI. The Middleware is therefore often where the business logic resides. 
Typically code used here will include Java and C# and frameworks like SOAP and JSON are used to communicate throughout the breadth of the software.

---

## What are the clients? 
The clients are anything that send requests to the back-end. They are often browsers that make requests for the HTML and JavaScript code that they will execute to display websites to the end user.  
However, there many different kinds of clients: they might be a mobile application, an application running on another server, or even a web enabled smart appliance.

## What is a Backend? 
The back-end is all of the technology required to process the incoming request and generate and send the response to the client.  
This typically includes three major parts (there can be other parts as well depending on architectural design): 
* The server – this is the computer that receives requests.  
* The app – this is the application running on the server that listens for requests, retrieves information from the database, and sends a response. 
* The database – databases are used to organize and persist data.

## What is a server? 
A server is simply a computer that listens for incoming requests. Though there are machines made and optimized for this particular purpose, any computer that is connected to a network can act as a server.  
In fact, you will often use your very own computer as server when developing apps.

## What are the core functions of the app? 
The server runs an app that contains logic about how to respond to various requests based on the HTTP verb and the Uniform Resource Identifier (URI).  
HTTP defines a set of request methods to indicate the desired action to be performed for a given resource. 
Although they can also be nouns, these request methods are sometimes referred to as HTTP verbs.  
A URI (Uniform Resource Identifier) is a string that refers to a resource. The most common are URLs, which identify the resource by giving its location on the Web. 
The pair of an HTTP verb and a URI is called a route and matching them based on a request is called routing.

Some of these handler functions will be middleware. In this context, middleware is any code that executes between the server receiving a request and sending a response. 
These middleware functions might modify the request object, query the database, or otherwise process the incoming request. 
Middleware functions typically end by passing control to the next middleware function, rather than by sending a response. 
Eventually, a middleware function will be called that ends the request-response cycle by sending an HTTP response back to the client.  
Often, programmers will use a framework like Express or Ruby on Rails to simplify the logic of routing. 
For now, just think that each route can have one or many handler functions that are executed whenever a request to that route (HTTP verb and URI) is matched.

## What kind of responses can a server send? 
The data that the server sends back can come in different forms. For example, a server might serve up an HTML file, send data as JSON, or it might send back only an HTTP status code. 
You’ve probably seen the status code “404 – Not Found” whenever you’ve tried navigating to a URI that doesn’t exist, but there are many more status codes that indicate what happened when the server received the request.

## What is a database and why do we need to use them? 
Databases are commonly used on the back-end of web applications. These databases provide an interface to save data in a persistent way to memory. 
Storing the data in a database both reduces the load on the main memory of the server CPU and allows the data to be retrieved if the server crashes or loses power. 
Many requests sent to the server might require a database query. A client might request information that is stored in the database, or a client might submit data with their request to be added to the database.

## What is a Web API? 
An API is a collection of clearly defined methods of communication between different software components. 
More specifically, a Web API is the interface created by the back-end: the collection of endpoints and the resources these endpoints expose.