# Explain what is REST and RESTFUL?
REST represents REpresentational  State Transfer; it is a relatively new aspect of writing web API.

RESTFUL is referred for web services written by applying REST architectural concept are called RESTful services, 
it focuses on system resources and how state of resource should be transported over HTTP protocol to a 
different clients written in different language.  
In RESTFUL web service http methods like GET, POST, PUT and DELETE can be used to perform CRUD operations.

# Explain the architectural style for creating web api?
The architectural style for creating web api are
•HTTP for client server communication
•XML/JSON as formatting language
•Simple URI as the address for the services
•Stateless communication

# Mention what tools are required to test your web api?
SOAPUI tool for SOAP WS and Firefox “poster” plugin for RESTFUL services.

# Mention what are the HTTP methods supported by REST?
HTTP methods supported by REST are:
•GET: It requests a resource at the request URL. It should not contain a request body as it will be discarded. 
May be it can be cached locally or on the server.
•POST: It submits information to the service for processing; it should typically return the modified or new resource
•PUT: At the request URL it update the resource
•DELETE: At the request URL it removes the resource
•OPTIONS: It indicates which techniques are supported
•HEAD: About the request URL it returns meta information

# Mention whether you can use GET request instead of PUT to create a resource?
No, you are not supposed to use POST or GET.  GET operations should only have view rights

# Mention what are resources in a REST architecture?
Resources are identified by logical URLs; it is the key element of a RESTful design.  Unlike, SOAP web services in REST,
you view the product data as a resource and this resource should contain all the required information.

# Mention what is the difference between AJAX and REST?
    AJAX
In Ajax, the request are sent to the server by using XMLHttpRequest objects. 
The response is used by the JavaScript code to dynamically alter the current page
Ajax is a set of technology; it is a technique of dynamically updating parts of UI without having to reload the page
Ajax eliminates the interaction between the customer and server asynchronously
REST requires the interaction between the customer and server

    REST
REST have a URL structure and a request/response pattern the revolve around the use of resources
REST is a type of software architecture and a method for users to request data or information from servers
REST requires the interaction between the customer and server

# Mention some key characteristics of REST?
Some key characteristics of REST includes

•REST is stateless, therefore the SERVER has no state (or session data)
•With a well applied REST API, the server could be restarted between two calls as every data is passed to the server
•Web service mostly uses POST method to make operations, whereas REST uses GET to access resources

# Mention what are the different application integration styles?
The different integration styles includes
•Shared database
•Batch file transfer
•Invoking remote procedure (RPC)
•Swapping asynchronous messages over a message oriented middle-ware (MOM)

