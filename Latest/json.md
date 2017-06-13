# Mention what is JSON?
JSON is a simple data exchange format.  JSON means JavaScript Object Notation; it is language and platform independent.

# Explain what is JSON objects?
An object can be defined as an unordered set of name/value pairs.  An object in JSON starts with {left brace} and finish 
or ends with {right brace}.  Every name is followed by: (colon) and the name/value pairs are parted by, (comma).

# Explain how to transform JSON text to a JavaScript object?
One of the common use of JSON is to collect JSON data from a web server as a file or HTTP request, 
and convert the JSON data to a JavaScript, ant then it avails the data in a web page.

# Mention what is the rule for JSON syntax rules? Give an example of JSON object?
JSON syntax is a set of the JavaScript object notation syntax.
•Data is in name/value pairs
•Data is separated by comma
•Curly brackets hold objects
•Square bracket holds arrays

# Why must one use JSON over XML?
•It is faster and lighter than XML as on the wire data format
•XML data is typeless while JSON objects are typed
•JSON types: Number, Array, Boolean, String
•XML data are all string
•Data is readily available as JSON object is in your JavaScript
•Fetching values is as simple as reading from an object property in your JavaScript code

# Mention what is JSON-RPC and JSON Parser?
•JSON RPC: It is a simple remote procedure call protocol same as XML-RPC although it uses 
the lightweight JSON format instead of XML
•JSON Parser: JSON parser is used to parse the JSON data into objects to use its value. 
It can be parsed by javaScript, PHP and jQuery

# Mention what is the file extension of JSON?
File extension of JSON is .json

# Mention which function is used to convert a JSON text into an object?
To convert JSON text into an object “eval” function is used.

# Mention what are the data types supported by JSON?
Data types supported by JSON includes
•Number
•String
•Boolean
•Array
•Object
•Null

# Mention what is the role of JSON.stringify?
JSON.stringify() converts an object into a JSON text and saves that JSON text in a string.

# Show how to parse JSON in JQuery?
To parse JSON in JQuery, we will see the example
```
var json = ‘{“name”: “Guru 99”, “Description “: “Learn PHP Interactively with PHP Beginner Tutorials}

obj = $.parseJSON(json);

//alert(obj.name);
```
# Mention what is the function used for encoding JSON in PHP?
For encoding JSON in PHP, json_encode () function is used.  
This function returns the JSON representation of a value on success or false on failure.

# Explain how you can convert a string into a JSON Array?
To convert a string into a JSON array, you need to create a JSONObject object for each of your objects, 
and add those to your JSON array.

# Mention what are the JSON files?
•JSON file type for JSON files is “.json”
•The MIME type for JSON text is “application/json”

# List out the uses of JSON?
Uses of JSON includes
•When writing application based on JavaScript it uses JSON, which includes browser extension and websites
•JSON is used for transmitting and serializing structured data over network connection
•JSON is mainly used to transfer data between server and web application
•Web service and API’s use JSON format to provide public data
•JSON can be used with modern programming language

# Mention what are the drawbacks of JSON?
Drawbacks of json are
•It does not contain type definition
•It lacks some sort of DTD

# Mention what is the MIME type of JSON?
MIME type for JSON text is “application/json”

# Mention what is JSONP?
JSONP stands for JSON with padding. It is a method used to bypass the cross-domain policies in web browsers. 
In other words, JSONP is the simple way to deal with browser restrictions when sending JSON responses 
from different domains from the client.

# Mention what is the difference between JSON and JSONP?
•JSON: JSON is a simple data format used for communication medium between different systems
•JSONP: It is a methodology for using that format with cross domain ajax requests while not being affected by same origin policy issue.
