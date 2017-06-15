# What Is Angular 2?
Angular 2 is the most advanced framework for the web. Angular has rebuilt the entire framework in TypeScript, 
so it is entirely new for a programmer to start using.
The primary objective of Angular 2 is to give developers an easy, detailed framework to develop an 
effective way of doing code, without any code complexity or delays.
Angular 2 has improved many things from previous versions such as making components simpler syntactically 
and semantically than they were in Angular 1.

# How Angular Interprets Code

The custom component of Angular makes Angular more efficient and responsive. The backend mechanism of 
Angular is grabbed by the ideas from Backbone.JS, Knockout, and many other web frameworks.
The overall architecture of Angular 2 consists of Module, Component, Template, Metadata, Data Binding, 
Service, Directive, and the Dependency Injection.


# Angular project different files (Watchers are of each component) and their usage.

•package.json identifies npm package dependencies for the project.
•tsconfig.json defines how the TypeScript compiler generates JavaScript from the project’s files.
•typings.json provides additional definition files for libraries that the Typecript compiler doesn’t natively recognize.
•systemjs.config.js provides information to a module loader about where to find application modules, and registers all 
the necessary packages. 
It also contains other packages that will be needed by later documentation examples.

# What Makes Angular 2 Unique?
Many things make Angular 2 more unique and different in its context. Now, we have a safer and more simplified code approach in Angular 2.

Angular 2 is not only a compelling alternative for React but all of the front-end libraries and frameworks. Reason being:

1.Typescript
 One of the distinct updates in Angular 2 is TypeScript. TypeScript ensures safer code. Most programmers don't understand 
 the core objective of TypeScript; they confuse it with lesser code. But, TypeScript ensures you to make more reliable code.

 TypeScript is developed by Microsoft and is the type superset of JavaScript that compiles your code into plain JavaScript. 
 TypeScript can easily track the bugs in your code. Now, you don’t need to worry about the program correctness.

 The code correctness has been done previously by other ways too but by using TDD or Code Reviews. 
 Most of the bugs have to do with typing issues (syntax), so TypeScript offers you a complete set of features for 
 advanced IntelliSense experience for programmers.

2.Dependency Injection
 Dependency Injection works when you need to import any dependency in your application. 
 It is the way to give a new object of a class with the required dependency. Mostly, dependencies are services. 
 To provide the new component with services, Angular uses DI (Dependency Injection).

 It automatically tells about the services by looking into constructor parameters. And when it creates the component 
 then it will ask an Injector for the service. If requested service is not in the container, Angular inject will auto-create 
 and inject into your component.

3.Jasmine
 Jasmine in Angular 2 provides an API that poorly attempts to read sentences. Moreover, it provides a bunch of 
 assertion bells and whistle. So, Angular 2 gives you less-boilerplate.
