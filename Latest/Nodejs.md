# What is Node?
Node.js is javascript runtime that uses v8 Javascript engine.
It uses an event-driven, non-blocking I/O model that makes it lightweght and efficient.

# What is V8 Javascript engine?
Its open source javascript engine written in C++ that takes javascript code complile into machine code. 
It used inside nodejs and inside the chrome browser.

# How to run the nodejs on command prompt and in chrome.
In both cases we are runing v8 javascript engine. we already know that, these two are different. 
Node has feature like files system manipulation, 
Browser has the feature like manipulation what shown inside the window.

Command Prompt
```
> node -- press enter
> console.log('Hello world.')

-- inside node we have something global which is same as window
> global
-- Inside node we have somthing process similar to document in browser.
> process.exit(0) -- it will bring back to command prompt.
-- 

```
Running in chrome >Developer tools>console tab

```
>console.log('Hello world.')

-- inside of the browser we have window is the global object, it store everything to which you have access.
> window

-- Inside browser we have access to document , its store the reference to dom and above.
> document
```
# Why I should use Nodejs? Blocking vs Non-blocking

Nodejs is single threaded model which means that our application run on single thread 
    thats the reason it uses non blocking mechanism.
Where as asp.net webserver is multi threaded. 
Blocking context we could handle two request on two different threads but it doesnt scale well 
    because each request we have to beef it up the cpu and ram resources for the application to run 
    but this sucks because those thread still sitting idle to complete the I/O operation, which still wasting each
    resources.

Blocking call waits for the I/O operation to complete before returning. Its results are returned synchronously. 
Nothing else in that process takes place during the waiting. 
A blocking call causes results to be returned synchronously.

In contrast, non-blocking call returns immediately without results and uses alternate means to check for completion. 
Other processing can be done while waiting and the results are returned asynchronously.
A non-blocking call causes results to be returned asynchronously.This means any activity taking a long time to finish, 
such as file access, network communication, and database operations, 
are requested and put aside until the results are ready and returned via a callback function. 
Instead of asking to read a file and waiting for the operating system to come back with a file handler or buffer, 
the a callback function is invoked when the operation is completed, freeing the server to handle additional requests.

Other advantages is nodejs ecosystem is open source , it has large community so you no need to build you application from 
scrach.

# What is an error-first callback?

Error-first callbacks are used to pass errors and data. The first argument is always an error object that the programmer has to check if something went wrong. Additional arguments are used to pass data.
```
fs.readFile(filePath, function(err, data) {  
  if (err) {
    //handle the error
  }
  // use the data object
});

```
# How can you avoid callback hells?

To do so you have more options:
•modularization: break callbacks into independent functions
•use Promises
•use yield with Generators and/or Promises

# How can you listen on port 80 with Node?

Trick question! You should not try to listen with Node on port 80 (in Unix-like systems) - to do so you would need superuser rights, but it is not a good idea to run your application with it.

Still, if you want to have your Node.js application listen on port 80, here is what you can do. Run the application on any port above 1024, then put a reverse proxy like nginx in front of it.

# What's the event loop?

TL;DR:


It is a magical place filled with unicorns and rainbows - Trevor Norris

Node.js runs using a single thread, at least from a Node.js developer's point of view. Under the hood Node.js uses many threads through libuv.

Every I/O requires a callback - once they are done they are pushed onto the event loop for execution. If you need a more detailed explanation, I suggest viewing this video:

# What tools can be used to assure consistent style?

You have plenty of options to do so:
•JSLint by Douglas Crockford
•JSHint
•ESLint
•JSCS

These tools are really helpful when developing code in teams, to enforce a given style guide and to catch common errors using static analysis.

# What's the difference between operational and programmer errors?

Operation errors are not bugs, but problems with the system, like request timeout or hardware failure.

On the other hand programmer errors are actual bugs.

# Why npm shrinkwrap is useful?

This command locks down the versions of a package's dependencies so that you can control exactly which versions of each dependency will be used when your package is installed. - npmjs.com

It is useful when you are deploying your Node.js applications - with it you can be sure which versions of your dependencies are going to be deployed.

# What's a stub? Name a use case.

Stubs are functions/programs that simulate the behaviours of components/modules. Stubs provide canned answers to function calls made during test cases. Also, you can assert on with what these stubs were called.
```
A use-case can be a file read, when you do not want to read an actual file:
var fs = require('fs');

var readFileStub = sinon.stub(fs, 'readFile', function (path, cb) {  
  return cb(null, 'filecontent');
});

expect(readFileStub).to.be.called;  
readFileStub.restore();  

```
# What's a test pyramid? How can you implement it when talking about HTTP APIs?

A test pyramid describes that when writings test cases there should be a lot more low-level unit tests than high level end-to-end tests.

When talking about HTTP APIs, it may come down to this:
•a lot of low-level unit tests for your models

•less integration tests, where your test how your models interact with each other

•a lot less acceptance tests, where you test the actual HTTP endpoints

# What's your favourite HTTP framework and why?

There is no right answer for this. The goal here is to understand how deeply one knows the framework she/he uses, if can reason about it, knows the pros, cons.

Things that work better than these questions

As you may already guessed, we are not huge fans of these type of questions. Instead we do believe in small, real-life problems, solved together. During these you will get a very good understanding of how one thinks. But not just that. You will know if she/he is a good fit for your team, as you have to solve something together. 

When we are hiring (and we are always hiring) we usually look for a combination of the following:
•cultural fit ◦transparency
◦self-improvement
◦bias towards clarity
◦do things smarter than harder

•skill and expertise

Spending as little as half a day with your possible next co-worker is worth more than a thousand questions.

UPDATE: A follow up of this article called Node.js Interview Questions and Answers (2017 Edition) just got published on the RisingStack blog. The majority of the questions are different from what you read in this article, so I recommend to check it out as well!

Do you have an interesting hiring story with Node.js? Please share your story in the comments below! 

# What's a test pyramid? Give an example!

A test pyramid describes the ratio of how many unit tests, integration tests and end-to-end test you should write.

![pyramid](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/pyramid.png) 

An example for an HTTP API may look like this:
•lots of low-level unit tests for models (dependencies are stubbed),
•fewer integration tests, where you check how your models interact with each other (dependencies are not stubbed),
•less end-to-end tests, where you call your actual endpoints (dependencies are not stubbed).

# When are background/worker processes useful? How can you handle worker tasks?

Worker processes are extremely useful if you'd like to do data processing in the background, like sending out emails or processing images.

There are lots of options for this like RabbitMQ or Kafka.

How can you secure your HTTP cookies against XSS attacks?

XSS occurs when the attacker injects executable JavaScript code into the HTML response.

To mitigate these attacks, you have to set flags on the set-cookie HTTP header:
•HttpOnly - this attribute is used to help prevent attacks such as cross-site scripting since it does not allow the cookie to be accessed via JavaScript.
•secure - this attribute tells the browser to only send the cookie if the request is being sent over HTTPS.

So it would look something like this: Set-Cookie: 
```
sid=<cookie-value>;
```
 HttpOnly. If you are using Express, with express-cookie session, it is working by default.

How can you make sure your dependencies are safe?

When writing Node.js applications, ending up with hundreds or even thousands of dependencies can easily happen. 
 For example, if you depend on Express, you depend on 27 other modules directly, and of course on those dependencies' as well, so manually checking all of them is not an option!

The only option is to automate the update / security audit of your dependencies. For that there are free and paid options:
•npm outdated
•Trace by RisingStack
•NSP
•GreenKeeper
•Snyk

# What's wrong with the code snippet?
```
new Promise((resolve, reject) => {  
  throw new Error('error')
}).then(console.log)
```

> The Solution

As there is no catch after the then. This way the error will be a silent one, there will be no indication of an error thrown.

To fix it, you can do the following:
```
new Promise((resolve, reject) => {  
  throw new Error('error')
}).then(console.log).catch(console.error)
```

If you have to debug a huge codebase, and you don't know which Promise can potentially hide an issue, you can use the unhandledRejection hook. It will print out all unhandled Promise rejections.
```
process.on('unhandledRejection', (err) => {  
  console.log(err)
})
```
# What's wrong with the following code snippet?
```
function checkApiKey (apiKeyFromDb, apiKeyReceived) {  
  if (apiKeyFromDb === apiKeyReceived) {
    return true
  }
  return false
}
```

> The Solution

When you compare security credentials it is crucial that you don't leak any information, so you have to make sure that you compare them in fixed time. If you fail to do so, your application will be vulnerable to timing attacks.

But why does it work like that? 

V8, the JavaScript engine used by Node.js, tries to optimize the code you run from a performance point of view. It starts comparing the strings character by character, and once a mismatch is found, it stops the comparison operation. So the longer the attacker has right from the password, the more time it takes.

To solve this issue, you can use the npm module called cryptiles.
```
function checkApiKey (apiKeyFromDb, apiKeyReceived) {  
  return cryptiles.fixedTimeComparison(apiKeyFromDb, apiKeyReceived)
}
```
# What's the output of following code snippet?
```
Promise.resolve(1)  
  .then((x) => x + 1)
  .then((x) => { throw new Error('My Error') })
  .catch(() => 1)
  .then((x) => x + 1)
  .then((x) => console.log(x))
  .catch(console.error)
```

> The Answer

The short answer is 2 - however with this question I'd recommend asking the candidates to explain what will happen line-by-line to understand how they think. It should be something like this:
1.A new Promise is created, that will resolve to 1. 
2.The resolved value is incremented with 1 (so it is 2 now), and returned instantly. 
3.The resolved value is discarded, and an error is thrown. 
4.The error is discarded, and a new value (1) is returned. 
5.The execution did not stop after the catch, but before the exception was handled, it continued, and a new, incremented value (2) is returned. 
6.The value is printed to the standard output. 
7.This line won't run, as there was no exception.

# What do you mean by the term I/O ?

I/O is the shorthand for input and output, and it will access anything outside of your application. It will be loaded into the machine memory to run the program, once the application is started.


NodeJS

# What does event-driven programming mean?

In computer programming, event driven programming is a programming paradigm in which the flow of the program is determined by events like messages from other programs or threads. It is an application architecture technique divided into two sections 1) Event Selection 2) Event Handling

#  Where can we use node.js?

Node.js can be used for the following purposes

a)      Web applications ( especially real-time web apps )

b)      Network applications

c)       Distributed systems

d)      General purpose applications

  

 

#  What is the advantage of using node.js?

a)      It provides an easy way to build scalable network programs

b)      Generally fast

c)       Great concurrency

d)      Asynchronous everything

e)      Almost never blocks

# What are the two types of API functions in Node.js ?

The two types of API functions in Node.js are

a)      Asynchronous, non-blocking functions

b)      Synchronous, blocking functions

# What is control flow function?

A generic piece of code which runs in between several asynchronous function calls is known as control flow function.

9)      Explain the steps how “Control Flow” controls the functions calls? 

a)      Control the order of execution

b)      Collect data

c)       Limit concurrency

d)      Call the next step in program

# Why Node.js is single threaded?

For async processing, Node.js was created explicitly as an experiment. It is believed that more performance and scalability can be achieved by doing async processing on a single thread under typical web loads than the typical thread based implementation.

# Does node run on windows?

Yes – it does. Download the MSI installer from http://nodejs.org/download/

# Can you access DOM in node?

No, you cannot access DOM in node.

# Using the event loop what are the tasks that should be done asynchronously?

a)      I/O operations

b)      Heavy computation

c)       Anything requiring blocking

# Why node.js is quickly gaining attention from JAVA programmers? 

Node.js is quickly gaining attention as it is a loop based server for JavaScript. Node.js gives user the ability to write the JavaScript on the server, which has access to things like HTTP stack, file I/O, TCP and databases.

# What are the two arguments that async.queue takes?

The two arguments that async.queue takes

a)      Task function

b)      Concurrency value

# What is an event loop in Node.js ?

To process and handle external events and to convert them into callback invocations an event loop is used. So, at I/O calls, node.js can switch from one request to another .

# Mention the steps by which you can async in Node.js?

By following steps you can async Node.js

a)      First class functions

b)      Function composition

c)       Callback Counters

d)      Event loops

  

 

# What are the pros and cons of Node.js?

Pros:

a)      If your application does not have any CPU intensive computation, you can build it in Javascript top to bottom, even down to the database level if you use JSON storage object DB like MongoDB.

b)      Crawlers receive a full-rendered HTML response, which is far more SEO friendly rather than a single page application or a websockets app run on top of Node.js.

Cons:

a)       Any intensive CPU computation will block node.js responsiveness, so a threaded platform is a better approach.
 b)      Using relational database with Node.js is considered less favourable

# How Node.js overcomes the problem of blocking of I/O operations?

Node.js solves this problem by putting the event based model at its core, using an event loop instead of threads.

# What is the difference between Node.js vs Ajax?

The difference between Node.js and Ajax is that, Ajax (short for Asynchronous Javascript and XML) is a client side technology, often used for updating the contents of the page without refreshing it. While,Node.js is Server Side Javascript, used for developing server software. Node.js does not execute in the browser but by the server.

# What are the Challenges with Node.js ?

Emphasizing on the technical side, it’s a bit of challenge in Node.js to have one process with one thread to scale up on multi core server.

# What does it mean “non-blocking” in node.js?

In node.js “non-blocking” means that its IO is non-blocking.  Node uses “libuv” to handle its IO in a platform-agnostic way. On windows, it uses completion ports for unix it uses epoll or kqueue etc. So, it makes a non-blocking request and upon a request, it queues it within the event loop which call the JavaScript ‘callback’ on the main JavaScript thread.

# What is the command that is used in node.js to import external libraries?

Command “require” is used for importing external libraries, for example, “var http=require (“http”)”.  This will load the http library and the single exported object through the http variable.

# Mention the framework most commonly used in node.js?

“Express” is the most common framework used in node.js

# What is ‘Callback’ in node.js?

Callback function is used in node.js to deal with multiple requests made to the server. Like if you have a large file which is going to take a long time for a server to read and if you don’t want a server to get engage in reading that large file while dealing with other requests, call back function is used. Call back function allows the server to deal with pending request first and call a function when it is finished.

# What are the features of Node.js?

Below are the features of Node.js –
Very Fast
Event driven and Asynchronous 
Single Threaded but highly Scalable

# Explain REPL in Node.js?

REPL stands for Read Eval Print Loop. Node.js comes with bundled REPL environment which performs the following desired tasks –
Eval
Print
Loop
Read

# Explain variables in Node.js?

Variables are used to store values and print later like any conventional scripts. If “var” keyword is used then value is stored in variable. You can print the value in the variable using - console.log().
```
Eg:
$ node
> a = 30
30
> var b = 50
undefined
> a + b
80
> console.log("Hi")
Hi
undefined
```
# What is the latest version of Node.js available?

Latest version of Node.js is - v0.10.36.

# List out some REPL commands in Node.js?
```
Below are the list of REPL commands –
Ctrl + c - For terminating the current command.
Ctrl + c twice – For terminating REPL.
Ctrl + d - For terminating REPL.
Tab Keys - list of all the current commands.
.break - exit from multiline expression.
.save with filename - save REPL session to a file.
```
# Mention the command to stop REPL in Node.js?

Command - ctrl + c twice is used to stop REPL.

# Explain NPM in Node.js?

NPM stands for Node Package Manager (npm) and there are two functionalities which NPM takes care of mainly and they are –
Online repositories for node.js modules or packages, which can be searched on search.nodejs.org
Dependency Management, Version Management and command line utility for installing Node.js packages.

# Mention command to verify the NPM version in Node.js?

Below command can be used to verify the NPM version –

$ npm --version

# How you can update NPM to new version in Node.js?

Below commands can be used for updating NPM to new version –
```
$ sudo npm install npm -g
/usr/bin/npm -> /usr/lib/node_modules/npm/bin/npm-cli.js
npm@2.7.1 /usr/lib/node_modules/npm
```
# Explain callback in Node.js?

Callback is called once the asynchronous operation has been completed. Node.js heavily uses callbacks and all API’s of Node.js are written to support callbacks.

# How Node.js can be made more scalable?

Node.js works good for I/O bound and not CPU bound work. For instance if there is a function to read a file, file reading will be started during that instruction and then it moves onto next instruction and once the I/O is done or completed it will call the callback function. So there will not be any blocking.

# Explain global installation of dependencies?

Globally installed dependencies or packages are stored in user-directory/npm directory and these dependencies can be used in Command Line Interface function of any node.js.

# Explain local installation of dependencies?

By default npm will install the dependency in the local mode. Here local mode refers to the package installation in node_modules directory lying in the folder where Node application is present. “require ()” is used to access the locally deployed packages.

# Explain Package.JSON?

This will be present in the root directory of any Node module/application and will be used to define the properties of a package.

# Explain “Callback hell”?

“Callback hell” will be referred to heavily nested callbacks which has become unreadable or unwieldly.

# What are “Streams” in Node.JS?

“Streams” are objects which will let you read the data from source and write data to destination as a continuous process.

# What you mean by chaining in Node.JS?

It’s a mechanism in which output of one stream will be connected to another stream and thus creating a chain of multiple stream operations.

# Explain Child process module?

Child process module has following three major ways to create child processes –
spawn  - child_process.spawn launches a new process with a given command.
exec  - child_process.exec method runs a command in a shell/console and buffers the output.
fork - The child_process.fork method is a special case of the spawn() to create child processes.

# Why to use exec method for Child process module?

“exec” method runs a command in a shell and buffers the output. Below is the command –

child_process.exec(command[, options], callback)

# List out the parameters passed for Child process module?

Below are the list of parameters passed for Child Process Module –

child_process.exec(command[, options], callback)
command - This is the command to run with space-separated arguments.
options – This is an object array which comprises one or more following options –
cwd 
uid 
gid 
killSignal 
maxBuffer 
encoding 
env 
shell 
timeout 

callback – This is the function which is gets 2 arguments – stdout, stderr and error.

# What is the use of method – “spawn()”?

This method is used to launch a new process with the given commands. Below is the method signature –

child_process.spawn(command[, args][, options])

# What is the use of method – “fork()”?

This method is a special case for method- “spawn()” for creating node processes. The method signature –

child_process.fork(modulePath[, args][, options])

# Explain Piping Stream?

This is a mechanism of connecting one stream to other and this is basically used for getting the data from one stream and pass the output of this to other stream.

# What would be the limit for Piping Stream?

There will not be any limit for piping stream.

# Explain FS module ?

Here FS stands for “File System” and fs module is used for File I/O. FS module can be imported in the following way –

var test = require("fs")

# Explain “Console” in Node.JS?

“Console” is a global object and will be used for printing to stderr and stdout and this will be used in synchronous manner in case of destination is either file or terminal or else it is used in asynchronous manner when it is a pipe.

# Explain – “console.log([data][, ...])” statement in Node.JS?

This statement is used for printing to “stdout” with newline and this function takes multiple arguments as “printf()”.

# What you mean by “process”?

“process” is a global object and will be used to represent a node process.

# Explain exit codes in Node.JS? List out some exit codes?

Exit code will be used when the process needs to be ended with specified code. Below are the list of exit codes in Node.JS –
Fatal Error
Non-function Internal Exception Handler
Internal JavaScript Parse Error
Uncaught Fatal Exception
Unused
Internal JavaScript Evaluation Failure
Internal Exception Handler Run-Time Failure

# List out the properties of process?

Below are the useful properties of process –
Platform
Stdin
Stdout
Stderr
execPath
mainModule
execArgv
config
arch
title
version
argv
env
exitCode

# Define OS module?

OS module is used for some basic operating system related utility functions. Below is the syntax for importing OS module –

var MyopSystem = require("os")

# What is the property of OS module?

os.EOL – Constant for defining appropriate end of line marker for OS.

# Explain “Path” module in Node.JS?

“Path” module will be used for transforming and handling file paths. Below is the syntax of path module –

var mypath = require("path")

# Explain “Net” module in Node.JS?

“Net” module is being used for creating both clients and servers. It will provide asynchronous network wrapper. Below is the syntax of Net module –

var mynet = require("net")

# List out the differences between AngularJS and NodeJS?

AngularJS is a web application development framework. It’s a JavaScript and it is different from other web app frameworks written in JavaScript like jQuery. NodeJS is a runtime environment used for building server-side applications while AngularJS is a JavaScript framework mainly useful in building/developing client-side part of applications which run inside a web browser.

# NodeJS is client side server side language?

NodeJS is a runtime system, which is used for creating server-side applications.

# What are the advantages of NodeJS?

Below are the list of advantages of NodeJS –
Javascript – It’s a javascript which can be used on frontend and backend.
Community Driven - NodeJS has great open source community which has developed many excellent modules for NodeJS to add additional capabilities to NodeJS applications.

# In which scenarios NodeJS works well?

NodeJS is not appropriate to use in scenarios where single-threaded calculations are going to be the holdup.

42) What you mean by JSON?

JavaScript Object Notation (JSON) is a practical, compound, widely popular data exchange format. This will enable JavaScript developers to quickly construct APIs.

# Explain “Stub”?

Stub is a small program, which substitutes for a longer program, possibly to be loaded later and that is located remotely. Stubs are functions/programs that simulate the behaviors of components/modules.

# List out all Node.JS versions available?

Below are the list of all NodsJS versions supported in operating systems –


OperatingSystem

Node.js version

Windows node-v0.12.0-x64.msi 
Linux node-v0.12.0-linux-x86.tar.gz 
Mac node-v0.12.0-darwin-x86.tar.gz 
SunOS node-v0.12.0-sunos-x86.tar.gz 

# Explain “Buffer class” in Node.JS?

It is a global class which can be accessed in an application without importing buffer modules.

# How we can convert Buffer to JSON?

The syntax to convert Buffer to JSON is as shown beow

buffer.toJSON()

# How to concatenate buffers in NodeJS?

The syntax to concatenate buffers in NodeJS is

var MyConctBuffer = Buffer.concat([myBuffer1, myBuffer2]);

# How to compare buffers in NodeJS?

To compare buffers in NodeJS, use following code –

Mybuffer1.compare(Mybuffer2);

# How to copy buffers in NodeJS?

Below is the syntax to copy buffers in NodeJS –

buffer.copy(targetBuffer[, targetStart][, sourceStart][, sourceEnd])

# What are the differences between “readUIntBE” and “writeIntBE” in Node.JS?
readUIntBE - It’s a generalized version of all numeric read methods, which supports up to 48 bits accuracy. Setting noAssert to “true” to skip the validation.
writeIntBE - This will write the value to the buffer at the specified byteLength and offset and it supports upto 48 bits of accuracy.

# Why to use “__filename” in Node.JS?

“__filename” is used to represent the filename of the code which is being executed. It used to resolve the absolute path of file. Below is the sample code for the same –

Console.log(__filename);

# Why to use “SetTimeout” in Node.JS?

This is the global function and it is used to run the callback after some milliseconds.

Syntax of this method –

setTimeout(callbackmethod, millisecs)

# Why to use “ClearTimeout” in Node.JS?

This is the global function and it is used to stop a timer which was created during “settimeout()”.

# Explain Web Server?

It is a software app which will handle the HTTP requests by client (eg: browser) and will return web pages to client as a response. Most of web server supports – server side scripts using scripting languages. Example of web server is Apache, which is mostly used webserver.

# List out the layers involved in Web App Architechure?

Below are the layers used in Web Apps –
Client - Which makes HTTP request to the server. Eg: Browsers.
Server – This layer is used to intercept the requests from client.
Business – It will have application server utilized by web servers for processing.
Data – This layer will have databases mainly or any source of data.

# Explain “Event Emitter” in Node.JS?

It is a part of Events module. When instance of EventEmitter faces any error, it will emit an 'error' event. “Event Emitters” provides multiple properties like – “emit” and “on”.
“on” property is used for binding the function with event.
“emit” property is used for firing an event.

# Explain “NewListener” in Node.JS?

This event is being emitted whenever any listener is added. So when event is triggered the listener may not have been removed from listener array for the event.

# Why to use Net.socket in Node.JS?

This object is an abstraction of a local socket or TCP. net.Socket instances implement a duplex Stream interface. These can be created by the user and used as a client (with connect() function) or they can be created by Node and can be passed to the user through the 'connection' event of a server.

# Which events are emitted by Net.socket?

Below are the list of events emitted by Net.socket –
```
Connect
Lookup
End
Data
Close
Drain
Timeout
Error
```
# Explain “DNS module” in Node.JS?

This module is used for DNS lookup and to use underlying OS name resolution. This used to provide asynchronous network wrapper. DNS module can be imported like –

var mydns = require("dns")

# Explain binding in domain module in Node.JS?

Below are the bindings in domain modules –
External Binding 
Internal Binding 

# Explain RESTful Web Service?

Web services which uses REST architecture will be known as RESTful Web Services. These web services uses HTTP protocol and HTTP methods.

# How to truncate the file in Node.JS?

Below command can be used for truncating the file –

fs.ftruncate(fd, len, callback)

# What is Node.js?

Node.js is a server-side JavaScript platform which is built on Google Chrome’s JavaScript V8 engine. It is an open source and cross platform application to develop server side and networking applications. Anyone can develop the Node.js application by writing code in JavaScript and it can be run on Microsoft Windows, Linux, or OS X.

 Node.js is not a new language and also it is not just a framework built on JavaScript. It is built on Chrome's JavaScript Runtime, so the code is written and executed very similarly to the browser. 
>
 Features of Node.js

 Following are some important features of Node.js.
•Fast in Code execution
It is very fast in code execution. 


•Highly scalable
Node.js uses a single thread model for event looping. Events respond to the server without blocking other operations. This makes Node.js highly scalable. Traditional servers create limited threads to handle requests and Node.js creates a single thread that provides service to much larger numbers of requests.


•Event Driven and Asynchronous
All API of Node.js are asynchronous. It means that the server is moving the next API call without waiting for returning data of previous requests.


•No Buffering
Node.js never buffers any data.

Many of us are confused about Node.js. It is not a web server like Apache. Node.js provides a new way to execute our code. It is JavaScript runtime. Node.js provides the facility to create an HTTP server and we can host our application on the same.

 For more visit the following link,
• Introduction To Node.js

 

# What are the key features of Node.js?

Here are the following key features of Node.js:
•Real time Data intensive.
Example - Multiplayer Games, Stock Trading, Chat App etc.


•Highly scalable servers for Web Applications. 
Example - E-Commerce, Social Media, REST API etc.


•Builds fast and scalable network Applications.
Example - Proxy Server, Backend web services, HTTP Web Server etc.

Node.js main features
•Node.js version 6 focuses on performance improvements, increased reliability and better security for its 3.5 million users.

•Event driven and Asynchronous.
•Node.js is emerging as a universal platform used for Web Applications, IoT, mobile, Enterprise Application development and micro service architectures.
•Full stack JavaScript developers can use it for front end, back end, mobile and IoT projects.
•Node.js v6 comes equipped with v8 JavaScript engine 5.0, which has improved ECMAScript 2015 (ES6) support. Ninety-three percent of ES6 features are also now supported in the Node.js v6 release.
•Very Fast.
•Single Threaded but highly Scalable.

For more visit the following link.
• Jump Start Node.js

 

# What are the advantages of Node.js?


Node.js is an open source, cross-platform runtime environment for server-side and networking applications. Node.js applications are written in JavaScript and can be run within the Node.jsruntime on OS X, Microsoft Windows, Linux, FreeBSD, NonStop and IBM.

> Advantages
1.Web development is done in a dynamic language (JavaScript) on a VM that is incredibly fast (V8). It is much faster than Ruby, Python, or Perl.
2.Ability to handle thousands of concurrent connections with minimal overhead on a single process.
3.JavaScript is perfect for event loops with first class function objects and closures. People already know how to use it this way having used it in the browser to respond to user-initiated events.
4.Many people already know JavaScript, even people who do not claim to be programmers. It is arguably the most popular programming language.
5.Using JavaScript on a web server as well as the browser reduces the impedance mismatch between the two programming environments that can communicate data structures via JSON that work the same on both sides of the equation. Duplicate form validation code can be shared between server and client and so on.

For more visit the following link.
•  Node.js And AngularJS With SQL Server

 

# Explain REPL in Node.js.

The REPL stands for Read Eval Print Loop, which is a simple program that accepts the commands, evaluates the commands, and prints their results. It represents a computer environment like Unix/Linux shell or a window console in which we can enter the command and the system responds with output. REPL performs the following tasks:
•READ
Read the input from user, parse it into JavaScript data structure and store it in memory.


•EVAL
Execute the data structure.


•RINT
Print the result


•LOOP
Loop the command until user presses Ctrl+C two time.

For more visit the following link,
• Introduction To Node.js

 

# What is Closure?

Closure is a function defined within another scope that has access to all the variables within the outer scope. A Closure allows us a free environment for the outer function to access the inner functions and inner variables without any scope restrictions.

Closure is the local variable for a function, kept alive after the function has returned; or it's a stack-frame that is not deallocated when the function returns. A Closure is an inner function that has access to the outer function variable's scope chain. The Closure has 3 scope chains; the first one is to access to its own scope (variables defined within the curly brackets) and the second one is to access the outer function's variables and the third one is to access the global variables.

 Points to remember about Closures,
•Whenever you use a function inside another function, a Closure is used.
•Closure in JavaScript is like keeping a copy of all the local variables.
•A Closure is created just on entry to a function and the local variables are added to that Closure.
•A new set of local variables are kept every time a function with a Closure is called.
•Closure is the term for both the functions along with the variables that are captured.

For more visit the following link,
• Working With Closures in NodeJS

 

# What is NPM? What is the need of NPM in Node.js?


 NPM stands for Node.js Package Management. It comes with Node.js platform and allows us to install various packages for Node.js. This package manages and supports various commands to install and remove the modules. Here one important note is we require either package.json file or the node_modules folder to install modules locally.

 One of the best things about npm is that it locally stores all dependencies. For example, if module X uses module A version 1.0, and module Y uses module A version 1.5, then both X and Y will have their own local copies of module A.

> Need of npm package

 While I was working on a real node.js application I encountered many instances where I needed to write a few libraries. Recently, I thought these libraries could be useful for others. Afterward, I discovered the npm package.

 For more visit the following link,
•  How to Create Nodejs Module and Publish Over to Npm

 

# Explain event loop architecture of NodeJS.

1.When a request arrives, it is queued up into the EventLoop with a JavaScript Closure that includes the event (request, response) and corresponding callback.
2.The event is then given to the one worker thread if the job seems to take a long time to complete, that is from a C++ Thread Pool, handled by the libuv library.
3.Once the job is done, the corresponding callback is fired to return back the response to the Main thread.
4.The Event Loop returns the response to the client.

![architecture](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/architecture.png) 
For example:

```
var fs = require('fs');   
fs.readFile('avator.png', function(avator) {   
  console.log(‘image is loaded…’);   
});   
fs.writeFile('log.txt', 'Done', function() {   
  console.log(‘Done !..’);   
});  

``` 
The execution flow goes as follows:  1.Our code tells the node to do the two tasks, read() and write(), and then takes a rest.

2.The read() and write() operations are then queued into the Event Loop and distributed to the worker thread.

3.Once the worker threads are done with the job, it will fire the callbacks to return the response to the Event Loop.

4.Then the Event Loop returns the response to the client.

The callbacks of read() and write() will be executed in the order of which one completes first. But note that only one of the callbacks will be executed at a time so that the Node environment ensures that there won't be a deadlock or race condition. So it makes sure that the NodeJS provides Non-blocking IO.

 We could consider the Post Office environment for the NodeJS.

 When we post (request) something, the Post Master (Node) asks the Postmen to deliver (get the job done) the post to the corresponding address.

 Once the postmen deliver the posts, they report, one-by-one, to the Post Master that it's completed.

 The Post Master may even assign some work to the postman at the time of reporting that he is free.
# Explain Process Object in Node.js.

The process object is the global object in Node. It can be accessed from anywhere; it is an instance of EventEmitter. Each Node.js has a set of built-in functionalities, accessible through the global process object. The process object provides the standard input/output (stdio) streams stdin, stdout and stderr (as in C/C++) as in the following:
•stdin
A readable stream for reading input from the user.


•stdout
A writable stream, either synchronously or asynchronously.


•stderr
A blocking synchronous writable stream intended for error messages.

The stdout or non-blocking functions are: console.log, console.info, util.puts, util.print and Stderr. The blocking functons are: console.warn, console.error, util.debug and process.stdin (a readable stream for getting user input).

 Properties of Process Object
•process.title

By default a process title is NODE but you can change it.

#  Explain some concepts in Node.js.


Node.js uses some of the following concepts,
1.Debugger
Statement inserting debugger; in the code of java script  it will help to enable break point.


2.Modules
Node.js supports simple module loading system.


3.Console
Console module provides debugging feature that is similar in Java script console by browser.


4.Streaming
By various objects in node js it is abstract interface implemented.


5.Cluster
It allows us to create child process easily that shares server port.


6.DNS
DNS module contains functions.


7.Add-ons
It is a dynamically linked shared object.


8.Domain
It provides a way to handle multiple different IO operations as a single group.


9.Buffer
It is similar to array of integers but corresponds to fixed-sized.


10.Global
It is available for all modules.


11.Net
It provides asynchronous network wrapper.


12.Call backs
It is called when given task will be completed.


13.Error handling
It supports various types of categories error.


14.Crypto
It provides cryptographic functionality that includes a set of wrappers for Open SSL’s hash.

![conceptnodejs](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/conceptnodejs.png) 

# Why do we use Node.js and how does Node.js work?

Node.js is specially designed for building fast, efficient, scalable network applications and uses an event-driven, non-blocking I/O model to maximize efficiency. The callback function is what Node calls a listener function and it is called by the server whenever a new request comes in.

> How it works

 The following describes how Node.js works,
•You use your web browser to make a request for "about.html" on a Node.js web server.
•The Node server accepts your request and calls a function to retrieve that file from disk.
•While the Node server is waiting for the file to be retrieved, it services the next web request.
•When the file is retrieved, there is a callback function inserted into the Node server's queue.
•The Node server executes that function that in this case would render the HTML page and send it back to your browser.

Platforms for Node.js
•Runs on OSX, Linux, and Windows.

•Clickable installer for Windows and MacOSX.

# Explain Process.nextTick() function in Node.js.

 The Process.nextTick() function typically runs before any other I/O events fire. As we know, every node application runs on a single thread, in other words only one task or event is processed by Node's event loop. In an event loop, a queue of callbacks are processed by Node on every Tick of the event loop. On the next loop around the event loop calls these callbacks.

 The Process.nextTick() function defers the function until a completely new stack. You can call as many functions as you want to in the current stack. When the event loop is looking for a new event to execute the nextTick function will be in the queue and will execute an entire new stack. The Process.nextTick() function defers the execution of an action until the next pass around the event loop.

 # Explain Colors Module in Node.js.
The color module uses the popular color.js. Since the color module is not a built-in module of node.js, we need to install it using the node package manager.
```
npm install colors
```
 Once the command has executed successfully, you will find the following screen. In my case it's showing that the colors module was successfully installed in the application and is ready for use.
```
npm install colors
```
 The beauty of the colors module is that we can beautify the output with various colors. Here is the link to the colors module in NPM.

Color

 Let's implement a few small examples to understand how the colors module works with node.js. Have a look at the following example.

```
var http = require('http');  
var colors = require('colors');  
var server = http.createServer(function (req,res) {  
  console.log('This String Will Display RED'.red);  
});  
server.listen(9090);  
```
In the second line we are loading the colors module into our application. After loading the colors module, we can use it in our application. Have a look at the body of the createServer() function. The module will provide freedom to use a color associated with the (.) property of the object.

 Like, “sring”.colorname

 In this example we are using the red color by giving (.) after the object. Here is the sample output.

sample output

 Not only red, we can provide many colors in the same way. Here is the use of the colors module.

Usage

 This package extends the global String prototype with additional getters that apply terminal colors to your texts. The available styles are,  •Emphasis 
bold, italic, underline, inverse

•Colors
yellow, cyan, white, magenta, green, red, grey, blue


•Sequencers
rainbow, zebra, random

So, let's try another example. Here is some sample code.

```
var http = require('http');  
var colors = require('colors');  
var server = http.createServer(function (req,res) {   
  console.log('hello'.green); // outputs green text  
  console.log('i like cake and pies'.underline.red) // outputs red underlined text  
  console.log('inverse the color'.inverse); // inverses the color  
  console.log('OMG Rainbows!'.rainbow); //   
});  
server.listen(9090);  
```
The output of this example is:

output of this example

#  What Is NodeJS Module?

 A module encapsulates related code into a single unit of code. When creating a module, this can be interpreted as moving all related functions into a file. Node modules run in their own scope so that they do not conflict with other modules. Node relatedly provides global  access to to help facilitate module interoperability. The primary 2 items that we are concerned with here are require and exports. You require other modules that you wish to use in your code and your module exports anything that should be exposed publicly. Let's see an example: save the below code as test.js,

```
exports.name = function() {   
   console.log('My name is Sourav Lahoti');   
};   
```
# What is Cluster Worker Object in Node.js?

A Worker Object is a script that runs in a background process and does not block the other code processes attached to the page. A Worker Object contains all the public information and methods about a worker. The master can use "cluster.workers." If a worker throws an exception and does not handle the exception itself, the exception will create an event that you can listen for as an onerror event.

> Worker.id
 A unique id is provided to each worker. This unique id resides in the "id". While a worker is alive, on the basis of the unique id we can get the indexes from the cluster.workers.

> Worker.process

 Workers are created using "child_process.fork()", the returned object from this function is stored as ".process". Child nodes are entire new instances of V8. Allow at least 30ms startup and 10mb for each new node. A ChildProcess class is not intended to be used directly; use the "spawn()" or "fork()"methods to create child process instances.

> Methods of Worker Class
•Worker
send(message,[sendHandle])

•Worker.kill()
This function kills the workers.


•Worker
Disconnect()

# What are the main components of Node.js?

The main components of NodeJs are APIs, a V8 Engine and Libuv.

>Libuv Library

 Libuv is a multi-platform support library for asynchronous I/O. It was developed for Node.js using C and C++. But it's also used by Mozilla's Rust language, Luvit, Julia, pyuv and others.

 This libuv library is the main part for I/O related operations like reading files and interacting with the OS.

 You can check it out on GitHub for more information about the libuv library.

>V8 Engine

 From Google: “V8 is Google's open-source high-performance JavaScript engine, written in C++ and used in Google Chrome, the open source browser from Google. It implements ECMAScript as specified in ECMA-262, 3rd edition and runs on Windows XP and Vista, Mac OS X 10.5+, and Linux systems that use IA-32, ARM or MIPS processors. V8 can run standalone, or can be embedded into any C++ application.”

If you are interested in learning more about the V8 engine, please visit here. 

>APIs (NodeJS Core Libs)

 The NodeJs APIs are nothing but functions to do something upon your request. By default the NodeJSapis are asynchronous in nature but still you can use NodeJS APIs synchronously.

 For example, the http module could be used either synchronously or asynchronously.


```
var fs = require('fs');   
fs.readFile(‘/files/help.txt’, function(err, buf)   
{   
   // use fs.readFileSync() for sync operation. console.log(buf.toString());   
}   
);   
```
# Explain EventEmitter Object in NodeJS.

To access the EventEmitter class, use,
```
require('events').EventEmitter
```
API methods are accessed through an instance of the EventEmitter class. For this you need to create an object of the EventEmitter class, then you can access the method. For example,
```
varobj=new EventEmitter(); 
``` 
Using that you can access the API method via an EventEmitter instance. Let's see how in the following:

```
obj.emitEvent(); 
``` 
In Node we do not have the DOM so we use the EventEmitter class. This class has mainly two methods, "on" and "emit". I have given the example and sample use of these methods in the NodeJS environment.

> EventEmitter Class

 The event module contains the EventEmitter class. The Util package provides the way to inherit from one class to another class. The "EventEmitter" class allows us to listen for events and assign actions to run when those events occur. The EventEmitter class is based on a publish/subscribe model because we can subscribe to events and then publish them.

> When we use theEventEmitter class we need to require an events module in the program, for example,

```
varev=require("events");  
```
The ev object will then have a single property, which is the EventEmitter class itself.

 Objecs that emit events are instances of "events.EventEmitter." You can access them using,
```
require("events")
```  
Functions can be attached to objects, to be executed when an event is emitted; these function are listeners. Inside a listener function, "this" refers to the "EventEmitter" that the listener was attached to.

 Features of EventEmitter class,  •This class is for managing events.
•Can be extended to provide event functionality in other classes.
•It emits events.
•It listens to and handles those events.
•Something that drives the two, causing events to be emitted.

EventEmitter Methods
```
•emitobj.on(event, listener)
•emitobj.emit(event,[arg1],[arg2],..[argN])
•emitobj.once(event, listener)
•emitobj.removeListener(event, listener)
```
# Explain Event-Driven Programming in Node.js.

Event-Driven Programming is the term where the flow of the code is determined by events (click, load and so on). It's one of the basic milestones of today's popular programming languages, such as C#, Java and many more; I won't dwell on all of them here. In Node.js and moreover in any kind of JavaScript project, you'll be using or have used event-driven processes. Whether it's a page on load or a button click event, this is something you have done, whether you knew it or not.

 Let's make an example to the classic event-driven process and how it's done in NodeJS,
```
result = getJSONfromDestination();   
binddata(result); 
```  
The operation above requires a blocking I/O process (single-threaded operation that waits for the previously working synchronous code).

 Now let's have a look at how we do the asynchronous way (a non-blocking I/O process).
```
json_finished = function(result){   
   binddata(result);   
}   
  
getJSONfromDestination(jsonfinished); 
``` 
As you can see, this is a non-blocking sample, because json_finished does not work at first as you can imagine.
 It starts working when you call the getJSONfromDestination method and send param as the function to json_finished.

# What are Request and Cheerio in Node.js NPM?

Request and Cheerio are our npm packages. Cheerio doesn’t try to emulate a full implementation of the DOM. It specifically focuses on the scenario where you want to manipulate an HTML document using jQuery-like syntax. As such, it compares to jsdom favorably in some cases, but not in every situation.

 Cheerio itself doesn’t include a mechanism for making HTTP requests, and that’s something that can be tedious to handle manually. It’s a bit easier to use a module called request to facilitate requesting remote HTML documents. Request handles common tasks like caching cookies between multiple requests, setting the content length on POSTs, and generally makes life easier.

# Explain Karma And Jasmine in Node.js.
 

> Karma

 Karma is a tool made on top of NodeJS to run JavaScript test cases. This is not a testing framework like Jasmine or Mocha or Chai etc. It only allows us to run JavaScript test cases written using testing frameworks like Jasmine.

Karma runs JavaScript test cases against real browsers through Command Line Interface (CLI) rather than virtual browser and DOM. Since DOM rendering across browsers vary, for correctness of the test report it uses real browsers. It can configure what browsers need to be used while running Karma.

> Jasmine

 Jasmine is a BDD (Behavior Driven Development) Javascript testing framework which provides building blocks to write JavaScript unit test cases. It does not require any other JavaScript Framework. As stated in official documentation of Jasmine 2.0.0,

“Jasmine is a behavior-driven development framework for testing JavaScript code. It does not depend on any other JavaScript frameworks. It does not require a DOM. And it has a clean, obvious syntax so that you can easily write tests.”

Here is a code snippet which describes the basic structure of Jasmine Unit Test Spec,
```
describe("simple test", function()   
{   
   beforeEach(function(){   
});  
afterEach(function(){   
  
});   
   it("a is a string", function(){   
  
})   
})  
``` 
In the above sample code, there are four key keywords, “describe”, “it”, “beforeEach” and “afterEach”. “describe” and “it” functions accept two parameters.  
•A string
This parameter is used to define a string value which explains the purpose of suite.

•A function
This is a block of code that implements the suite

# What is Grunt in Node.js?

Grunt is a JavaScript Task Runner and this is a command line tool which runs on NodeJS. It helps us to do all the above tasks very easily with a minimum effort. Grunt ecosystem and its huge list of plugins help us get all front-end code production ready. 

> Install Grunt

 To install grunt in your project folder, run the below command in command line:
```
npm install grunt --save-dev
```
# How can you perform Testing in Node JS?

To check whether our Node JS is working, we can create a “Hello World” program in either of the following two ways,
•Directly type a message into the command window.
```
> node
> console.log('Test')
```
•Type the message in a JavaScript file and execute it in node.

Create a JavaScript file manually. (To do so, open Notepad, type some content into it and save it with a .js extension. That is all.)

Create a JavaScript file

 I typed the content as “console.log(‘Sibeesh passion welcomes you to the world of Node’);”.

```
>node myfile.js
```

# How can you create HTTPS Server WithNodeJS?

We use HTTPS when we need secure sessions. A secure session implies that the web browser will encrypt everything you do with a digitally signed certificate. So obviously before you do HTTPS, you need to create certificates. Let's therefore spend some time to see how to create certificates for SSL.

Creating HTTPS server

 Just like we do for HTTP, an import to node's HTTP module, for HTTPS we import the HTTPS module. Also, since we need to pass in the certificate and key file, we also need to import the filestream (fs) module to enable Node to read the files. The following is the code to create the HTTPS server.
```
var https = require('https');   
var fs = require('fs'); 

var options = {   
  key: fs.readFileSync('hostkey.pem'),   
  cert: fs.readFileSync('hostcert.pem')   
};   
  
https.createServer(options, function (req, res) {   
   res.writeHead(200);   
   res.end("hello world\n");   
}).listen(8000);  
```

# How can you achieve Scale and Concurrency in Node.js?

This feature is inherited in NODE.js through these functionalities:
•Single thread and multiple process

•Asynchronous functioning/programming

•Size the thread pool correctly

•Node applications are built

> Single Threaded Environment

 So what do these terms mean?
•In the simplest of words we can say that it takes requests from many clients but responds back in one operation or a thread.

thread

We can explain these feature as,

•Client requests for something

•Server processes the request

•Server forwards a response to the client

•Server is again ready to process a new request
 
 # Explain “request” module in node.js.

The “request” module is not a core module of node.js, so we need to install it on our own.

 This command will install the request module in the current node.js application. Here is the screen to demonstrate the installation.
```
> npm install request
```
 Once we start the installation, we will find that it's downloading many files and installing in the current node.js application. You will see the following screen after finishing the installation.
 Now, we are sure that the “request” module is installed in the application and it's ready to use. Now, let's discuss it. What is the purpose of the request module? 

 The beauty of node.js is, not only can we build a server but we can also build a client tool using node.js. A client in the sense that we can call some other server from a node.js application and get data from there, and to get data from another server, we can use the “request” module in node.js. 

 Here is a simple implementation of the “request” module. In this module we are making a HTTP request to the Google server and then we are logging the response in the console. Have a look at the following example.
```
var http = require('http');  
var request = require("request");  
var server = http.createServer(function (req, res) {  
   request("http://www.google.com", function (error, response, body) {  
      console.log(body);  
   });  
});  
server.listen(9090);   

```
# What is Express project and how can you create Express project?
Express is a framework that allows the creation of the MVC web architecture in a Node JS application. There are many ways to create an Express project but in this article I will use Intellij IDEA to create a node Express project.

# What is Asynchronous Programming?

Every function in node.js is asynchronous which means that everything that would normally block the thread is instead executed in the background, in other words it continues running in the background and the flow of control moves to the next line and executes them; the moment the operation is completed it executes a callback that will then be executed. For example if you are reading a file on the file system then you need to specify a callback function that is executed when the read operation has completed.

# What is middleware?

Middleware is actually a very simple concept to understand, it is very similar to middleman. What middleman does is he takes the request from one party and gets in touch with the other party, he does what needs to be done and then provides a response back to the party which placed the request in the first place. So middleware are just simple functions with three arguments; request, response and next, they act as a middleman; when express receives a request, express passes this request to each middleware in the chain until it receives a response. In general, there are two kinds of middleware, first one being a normal middleware, and the second one an error handling middleware.

 Middleware concept is at the core of express.js and very important to understand, almost everything in express.js is a middleware, from body parsers to loggers, from routes to error handlers. So it is very important to understand what are middlewares and how they work.

 A middleware has the following signature,
```
function aMiddleware(req, res, next){   
  //req: an express request object   
   //res: express response object, res.send, res.json,   
   //res.render etc can be used to generate response   
     
   /* the voodoo */   
}   
```
# What is Web Scraping in Node.js?


Web Scraping is the software technique of extracting the information from server side web applications. In this article we will see how things work by simply creating a web scraper using the DOM Parsing technique, and the tool which I am using is Node.js.

crapeDataFromHtml is our function and we create variables in the function for every item that we want to scrape from the website and then the data is serialized from our website in JSON format and then we have it once deserialization is done. In this case the circular red region gives me its relative node in the inspect window.
•First we reached url.

•Then we traversed DOM.

•Select our Nodes, the desired data we want to scrape

•Create your function, for instance scrapeDataFromHtml

•In this function, store all the data you want to scrape from website in variables .

•Write your logic and for multiple values you can use an array.

•Span and image are two things we want to scrape .

# What are the popular modules of NPM in Node.js?

Node Package Manager is an online module repository (kind of like Play Store for Node module) that allows you to use publicly available and reusable modules with version and dependency management.
```
 Popular modules are,
•Express.js
•Connect
•Socket.io
•Jade
•Mongodb
•Redis
•Coffee-script
•Underscore
```
