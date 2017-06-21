# Different kind of web application and their use?
There are two kinds of web application:
1) round-trip model: The browser requests an initial HTML document from the server. User interactions—such as clicking a link or submitting a form—led the browser to request and receive a completely new HTML document. In this kind of application, the browser is essentially a rending engine for HTML content, and all of the application logic and data resides on the server. The browser makes a series of stateless HTTP requests that the server handles by generating HTML documents dynamically
2) single-page model: It takes a different approach. An initial HTML document is sent to the browser, but user interactions lead to Ajax requests for small fragments of HTML or data inserted into the existing set of elements being displayed to the user. The initial HTML document is never reloaded or replaced, and the user can continue to interact with the existing HTML while the Ajax requests are being performed asynchronously, even if that just means seeing a “data loading” message.

# Explain the MVC Pattern.

server-side implementation of the MVC pattern. You can see that the expectation is that the model is obtained from a database and that the goal of the application is to service HTTP requests from the browser. This is the basis for round-trip web apps.
![server-side](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/mvc-server-side.PNG)

The client-side implementation of the MVC pattern gets its data from server-side components, usually  via a RESTful web service.
![client-side](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/mvc-client-side.PNG)

 Angular uses slightly different terminology for its building blocks, which means that the MVC model implementation

![angular-client-side](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/mvc-angular-client-side.PNG)

> Models:

M in MVC —contain the data that users work with. There are two broad types of model:
1) view models, which represent just data passed from the component to the template, and
2) domain models, which contain the data in a business domain, along with the operations, transformations, and rules for creating, storing, and manipulating that data, collectively referred to as the model logic.

The model in an  application built using the MVC pattern should 

• Contain the domain data

• Contain the logic for creating, managing, and modifying the domain data (even if that means executing remote logic via web services)

• Provide a clean API that exposes the model data and operations on it

 * The model should not 

• Expose details of how the model data is obtained or managed (in other words, details of the data storage mechanism or the remote web service should not be exposed to controllers and views)

• Contain logic that transforms the model based on user interaction (because this is the component’s job)

• Contain logic for displaying data to the user (this is the template’s job)

> Controllers/Components

Its the connective tissue in an Angular web app, acting as conduits between the data model and views. Components add business domain logic required to present some aspect of the model and perform operations on it. A component that follows the MVC pattern should

• Contain the logic required to set up the initial state of the template

• Contain the logic/behaviors required by the template to present data from the model

• Contain the logic/behaviors required to update the model based on user interaction 

* A component should not

• Contain logic that manipulates the DOM (that is the job of the template)

• Contain logic that manages the persistence of data (that is the job of the model)

> View Data

The domain model isn’t the only data in an Angular application. Components can create view data (also known as view model data or view models) to simplify templates and their interactions with the component.

> Views/Templates

 Views, which are known as templates in Angular, are defined using HTML elements that are enhanced by data bindings. It is the data bindings that make Angular so flexible, and they transform HTML elements into the foundation for dynamic web applications.

• Contain the logic and markup required to present data to the user

* Templates should not 

• Contain complex logic (this is better placed in a component or one of the other  Angular building blocks, such as directives, services, or pipes)

• Contain logic that creates, stores, or manipulates the domain modelTemplates can contain logic, but it should be simple and used sparingly. Putting anything but the simplest method calls or expressions in a template makes the overall application harder to test and maintain.

# Common Design Pitfalls :
These are not coding errors but rather problems with the overall shape of the web app that prevent the project team from getting the benefits that Angular and the MVC pattern can provide.The most common problem is logic put into the wrong component such that it undermines the MVC separation of concerns.

• Putting business logic in templates, rather than in components

• Putting domain logic in components, rather than in the model

• Putting data store logic in the client model when using a RESTful service

The application still runs, but it will become harder to enhance and maintain over time.

> Here are the three rules for where to put logic.

•   Template logic should prepare data only for display and never modify the model.

•   Component logic should never directly create, update, or delete data from the model.

•   The templates and components should never directly access the data store.

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

1. Typescript
 One of the distinct updates in Angular 2 is TypeScript. TypeScript ensures safer code. Most programmers don't understand 
 the core objective of TypeScript; they confuse it with lesser code. But, TypeScript ensures you to make more reliable code.

 TypeScript is developed by Microsoft and is the type superset of JavaScript that compiles your code into plain JavaScript. 
 TypeScript can easily track the bugs in your code. Now, you don’t need to worry about the program correctness.

 The code correctness has been done previously by other ways too but by using TDD or Code Reviews. 
 Most of the bugs have to do with typing issues (syntax), so TypeScript offers you a complete set of features for 
 advanced IntelliSense experience for programmers.

2. Dependency Injection
 Dependency Injection works when you need to import any dependency in your application. 
 It is the way to give a new object of a class with the required dependency. Mostly, dependencies are services. 
 To provide the new component with services, Angular uses DI (Dependency Injection).

 It automatically tells about the services by looking into constructor parameters. And when it creates the component 
 then it will ask an Injector for the service. If requested service is not in the container, Angular inject will auto-create 
 and inject into your component.

3. Jasmine
 Jasmine in Angular 2 provides an API that poorly attempts to read sentences. Moreover, it provides a bunch of 
 assertion bells and whistle. So, Angular 2 gives you less-boilerplate.


# Explain the life cycle hooks of Angular 2 application

Angular 2 component/directive has lifecycle events, managed by @angular/core. It creates the component, renders it, 
creates and renders its children, processes changes when its data-bound properties change, and then destroys 
it before removing its template from the DOM. Angular provides a set of lifecycle hooks(special events) 
which can be tapped into this lifecycle and perform operations when required. The constructor executes 
prior to all lifecycle events. Each interface has a single hook method prefixed with ng. For example, 
ngOnint interface has Oninit method that must be implemented in the component. 

Some of the events are applicable for both component/directives while few are specific to components.
•ngOnChanges: Responds when angular sets its data-bound property which receives the current and previous object values.

•ngOnInit: Initializes the component/directive after first ngOnChange triggers. This is most frequently used method 
to retrieve the data for the template from a back-end service.

•ngDoCheck: Detect and act upon changes occuring outside Angular context. It is called when every change detection run.

•ngOnDestroy: Cleanup just before Angular destroys the directive/component. Unsubscribe observables and detach event 
handlers to avoid memory leaks.

Component-specific hooks:
•ngAfterContentInit: Component content has been initialized

•ngAfterContentChecked: After Angular checks the bindings of the external content that it projected into its view.

•ngAfterViewInit: After Angular creates the component’s view.

•ngAfterViewChecked: After Angular checks the bindings of the component’s view.

# What are the advantages of using Angular 2 over Angular 1?
1.  Angular 2 is a platform not only a language:
2.  Better Speed and Performance: No $Scope in Angular 2, AOT
3.  Simpler Dependency Injection
4.  Modular, cross platform
5.  Benefits of ES6 and Typescript.
6.  Flexible Routing with Lazy Loading Features
7.  Easier to Learn

# How routing works in Angular 2.

Routing is a mechanism which enables user to navigate between views/components. Angular 2 simplifies the routing 
and provide flexibility to configure and define at module level (Lazy loading). 

The angular application has single instance of the Router service and whenever URL changes, corresponding 
Route is matched from the routing configuration array. On successful match, it applies redirects and the 
router builds a tree of ActivatedRoute objects and contains the current state of the router. Before redirection, 
the router will check whether new state is permitted by running guards (CanActivate). 
Route Guards is simply an interface method that router runs to check the route authorization. After guard runs,
 it will resolve the route data and activate the router state by instantiation the required components into 
```
 <router-outlet> </router-outlet>.
```

# What are Event Emitters and how it works in Angular 2?
Angular 2 doesn’t have bi-directional digest cycle, unlike angular 1. In angular 2, any change occurred in 
the component always gets propagated from the current component to all its children in hierarchy. 
If the change from one component needs to be reflected to any of its parent component in hierarchy, 
we can emit the event by using Event Emitter api.

In short, EventEmitter is class defined in @angular/core module which can be used by components and 
directives to emit custom events.

@output() somethingChanged = new EventEmitter();

We use somethingChanged.emit(value) method to emit the event. This is usually done in setter when 
the value is being changed in the class.

This event emit can be subscribed by any component of the module by using subscribe method.

myObj.somethingChanged.subscribe(val) => this.myLocalMethod(val));

# What is the use of codelyzer in angular 2 application.
All enterprise applications follows a set of coding conventions and guidelines to maintain code in better way. 
Codelyzer is an open source tool to run and check whether the pre-defined coding guidelines has been followed or not. 
Codelyzer does only static code analysis for angular and typescript project.

Codelyzer runs on top of tslint and its coding conventions are usually defined in tslint.json file. 
Codelyzer can be run via angular cli or npm directly. Editors like Visual Studio Code and Atom also supports codelyzer
 just by doing a basic settings.

To set up the codelyzer in Visual Studio code, we can go to File -> Preferences -> User Settings and 
add the path for tslint rules.
``` 
{
  "tslint.rulesDirectory": "./node_modules/codelyzer",
  "typescript.tsdk": "node_modules/typescript/lib"
}
To run from cli: ng lint. 

To run from npm: npm run lint

```

# What is lazy loading and How to enable lazy loading in angular 2?
Most of the enterprise application contains various modules for specific business cases. Bundling whole application code and 
loading will be huge performance impact at initial call. Lazy lading enables us to load only the module user is interacting 
and keep the rest to be loaded at runtime on demand.

Lazy loading speeds up the application initial load time by splitting the code into multiple bundles and loading them on demand.

Every Angular application must have one main module say AppModule. The code should be splitted into various child modules (NgModule) 
based on the application business case.

Plunkr Example: Link
1.  We don't require to import or declare lazily loading module in root module.
2.  Add the route to top level routing (app.routing.ts) and set loadChildren. loadChildren takes absolute path 
    from root folder followed by #{ModuleName}. RouterModule.forRoot() takes routes array and configures the router.
3.  Import module specific routing in the child module.
4.  In the child module routing, specify path as empty string ' ', the empty path. RouterModule.forChild again 
    takes routes array for the child module components to load and configure router for child.
5.  Then, export const routing: ModuleWithProviders = RouterModule.forChild(routes);

# What are the security threats should we be aware of in angular 2 application?

Just like any other client side or web application, angular 2 application should also follow some of 
the basic guidelines to mitigate the security risks. Some of them are:
a.  Avoid using/injecting dynamic Html content to your component.
b.  If using external Html, that is coming from database or somewhere outside the application, sanitize it.
c.  Try not to put external urls in the application unless it is trusted. Avoid url re-direction unless it is trusted.
d.  Consider using AOT compilation or offline compilation.
e.  Try to prevent XSRF attack by restricting the api and use of the app for known or secure environment/browsers.

# How would you optimize the angular 2 application for better performance?
Well, optimization depends on the type and size of application and many other factors. But in general, 
I would consider the following points while optimizing the angular 2 app:
1.  Consider AOT compilation.
2.  Make sure the application is bundled, uglified, and tree shaking is done.
3.  Make sure the application doesn’t have un-necessary import statements.
4.  Make sure that any 3rd party library, which is not used, is removed from the application.
5.  Have all dependencies and dev-dependencies are clearly separated.
6.  I would consider lazy loading instead of fully bundled app if the app size is more.


# How would you define custom Typings to avoid editor warnings?
Well, in most of the cases, the 3rd party library comes with its own .d.ts file for its type definition. 
In some cases, we need to extend the existing type by providing some more properties to it or if we need to 
define additional types to avoid Typescript warning.

If we need to extend the type definition for external library, as a good practice, we should not touch the node_modules or 
existing typings folder. We can create a new folder, say “custom-typings” and keep all customized type definition in that.

To define typings for application (JavaScript/Typescript) objects, we should define interfaces and entity classes in models 
folder in the respective module of the application.
For those cases, we can define or extend the types by creating our own “.d.ts” file.

# What is shadow DOM? How is it helping Angular 2 to perform better?
Shadow DOM is a part of the HTML spec which allows developers to encapsulate their HTML markup, CSS styles and JavaScript. 
Shadow DOM, along with a few other technologies, gives developers the ability to build their own 1st class tags, 
web components and APIs just like the 
```
<audio>
```
Collectively, these new tags and APIs are referred to as Web Components. Shadow DOM provides better separation of 
concern along with lesser conflict of styles and scripts with other HTML DOM elements.

Since shadow DOM are static in nature, it’s a good candidate to be cached as it is not accessible to developer. 
The cached DOM would be rendered faster in the browser providing better performance. Moreover, 
shadow DOM can be managed comparatively well while detecting the change in angular 2 application and re-paint of 
view can be managed efficiently.

# What is AOT compilation?
AOT compilation stands for Ahead Of Time compilation, in which the angular compiler compiles the angular components and 
templates to native JavaScript and HTML during the build time. 
The compiled Html and JavaScript is deployed to the web server so that the compilation and render time can be saved by the browser.

Advantages
1.  Faster download: Since the app is already compiled, many of the angular compiler related libraries are not required to be bundled, 
the app bundle size get reduced. So, the app can be downloaded faster.
2.  Lesser No. of Http Requests: If the app is not bundled to support lazy loading (or whatever reasons), for each associated html and css, 
there is a separate request goes to the server. The pre-compiled application in-lines all templates and styles with components, 
so the number of Http requests to the server would be lesser.
3.  Faster Rendering: If the app is not AOT compiled, the compilation process happens in the browser once the application is fully loaded. 
This has a wait time for all necessary component to be downloaded, and then the time taken by the compiler to compile the app. 
With AOT compilation, this is optimized.
4.Detect error at build time: Since compilation happens beforehand, many compile time error can be detected, 
providing a better degree of stability of application.

Disadvantages
1.  Works only with HTML and CSS, other file types need a previous build step
2.  No watch mode yet, must be done manually (bin/ngc-watch.js) and compiles all the files
3.  Need to maintain AOT version of bootstrap file (might not be required while using tools like cli)
4.  Needs cleanup step before compiling

# What are the core differences between Observables and Promises?

A nice answer taken from stack overflow:
A Promise handles a single event when an async operation completes or fails.
Note: There are Promise libraries out there that support cancellation, but ES6 Promise doesn't so far.
An Observable is like a Stream (in many languages) and allows to pass zero or more events where the callback is called for each event. 
Often Observable is preferred over Promise because it provides the features of Promise and more. 
With Observable it doesn't matter if you want to handle 0, 1, or multiple events. You can utilize the same API in each case. 
Observable also has the advantage over Promise to be cancelable. 
If the result of an HTTP request to a server or some other expensive async operation isn't needed anymore, 
the Subscription of an Observable allows to cancel the subscription, while a Promise will eventually call the success or 
failed callback even when you don't need the notification or the result it provides anymore. Observable provides operators like map, 
forEach, reduce, ... similar to an array. There are also powerful operators like retry(), or replay(), ... that are often quite handy.

Promises vs Observables
◦Promises: 
i.  returns a single value
ii. not cancellable

◦Observables:
1.  works with multiple values over time
2.  cancellable
3.  supports map, filter, reduce and similar operators
4.  proposed feature for ES 2016
5.  use Reactive Extensions (RxJS)
6.  an array whose items arrive asynchronously over time

# Explain local reference variables, ViewChild, and ContentChild.
Local template variables in angular2 is used to refer HTML elements and use their properties to access siblings or children.

Let’s consider you have an input field named username.
```
<input type="text" required ... />
```
This HTMLInputField can be made available to the template using # symbol with a variable name say username.
```
 <input type="text" #username required ... />
```
Now, this HTMLInputElement can be accessed from anywhere in the current template for example, 
checking validation and showing appropriate message based on the validation rule. But, 
username HTML reference is not accessible in the component/directive.

To access this in the component, angular 2 provides @ViewChild decorator which accepts the local reference variable.

@ViewChild('username') username: HTMLInputElement;

ViewChild element can be read after the view is initialized (ngAfterViewInit).

ContentChild is used to query the reference of the DOM within ng-content. Content Child are set before the ngAfterContentInit lifecycle hook.

For example:
```
Hide   Copy Code
// <code>app.component.ts</code>
<my-component>
    <p #contentRef>{{test}}</p>
</ my-component >
 
// MyComponent.component.ts
@Component({
    selector: ‘my-component',
    template: `
    <ng-content></ng-content>
    <div> ContentChild Example </div>
})
export class LifecycleComponent implements ngAfterContentInit{
                @ContentChild(‘contentRef’)   childContent: HTMLElement;
 
ngAfterContentInit() {
              this.log('ngAfterContentInit');
console.log(this.childContent);
    }
}

```
# What's New in Angular 4? [Angular 4 New Features] 

1. Smaller & Faster Apps - Angular 4 applications is smaller & faster in comparison with Angular 2.

2. View Engine Size Reduce - Some changes under to hood to what AOT generated code compilation that means in Angular 4, 
improved the compilation time. These changes reduce around 60% size in most cases.

3. Animation Package- Animations now have their own package i.e. @angular/platform-browser/animations

4. Improvement - Some Improvement on *ngIf and *ngFor.

5. Template - The template is now ng-template. You should use the “ng-template” tag instead of “template”.
 Now Angular has its own template tag that is called “ng-template”.

6. NgIf with Else – Now in Angular 4, possible to use an else syntax as,
```
<div *ngIf="user.length > 0; else empty"><h2>Users</h2></div>
<ng-template #empty><h2>No users.</h2></ng-template>
```
7. AS keyword – A new addition to the template syntax is the “as keyword” is use to simplify to the “let” syntax.
Use of as keyword,
```
<div *ngFor="let user of users | slice:0:2 as total; index as = i">
    {{i+1}}/{{total.length}}: {{user.name}}
</div>
```
To subscribe only once to a pipe “|” with “async” and If a user is an observable, you can now use to write,
```
<div *ngIf="users | async as usersModel">
    <h2>{{ usersModel.name }}</h2> <small>{{ usersModel.age }}</small>
</div>
```
8. Pipes - Angular 4 introduced a new “titlecase” pipe “|” and use to changes the first letter of each word into the uppercase. 
The example as,
```
<h2>{{ 'anil singh' | titlecase }}</h2>
<!-- OUPPUT - It will display 'Anil Singh' -->
```
9. Http - Adding search parameters to an “HTTP request” has been simplified as,
```
//Angular 4 -
http.get(`${baseUrl}/api/users`, { params: { sort: 'ascending' } });

//Angular 2-
const params = new URLSearchParams();
params.append('sort', 'ascending');
http.get(`${baseUrl}/api/users`, { search: params });
```

10. Test- Angular 4, overriding a template in a test has also been simplified as,
```
//Angular 4 -
TestBed.overrideTemplate(UsersComponent, '<h2>{{users.name}}</h2>');

//Angular 2 -
TestBed.overrideComponent(UsersComponent, {
    set: { template: '<h2>{{users.name}}</h2>' }
});
```
11. Service- A new service has been introduced to easily get or update “Meta Tags” i.e.
```
@Component({
    selector: 'users-app',
    template: `<h1>Users</h1>`
})
export class UsersAppComponent {
    constructor(meta: Meta) {
        meta.addTag({ name: 'Blogger', content: 'Anil Singh' });
    }
}
```

12. Forms Validators - One new validator joins the existing “required”, “minLength”, “maxLength” and “pattern”. 
An email helps you validate that the input is a valid email.

13. Compare Select Options - A new “compareWith” directive has been added and it used to help you compare options from a select.
```
<select [compareWith]="byUId" [(ngModel)]="selectedUsers">
    <option *ngFor="let user of users" [ngValue]="user.UId">{{user.name}}</option>
</select>
```
14. Router - A new interface “paramMap” and “queryParamMap” has been added and it introduced to represent the parameters of a URL. 
```
const uid = this.route.snapshot.paramMap.get('UId');
this.userService.get(uid).subscribe(user => this.name = name);
```
15. CanDeactivate - This “CanDeactivate” interface now has an extra (optional) parameter and it is containing the next state.

16. I18n - The internationalization is tiny improvement.
```
//Angular 4-
<div [ngPlural]="value">
    <ng-template ngPluralCase="0">there is nothing</ng-template>
    <ng-template ngPluralCase="1">there is one</ng-template>
</div>

//Angular 2-
<div [ngPlural]="value">
    <ng-template ngPluralCase="=0">there is nothing</ng-template>
    <ng-template ngPluralCase="=1">there is one</ng-template>
</div>
```
# What is ECMAScript ES5/ES6? 
The ECMAScript is a scripting language which is developed by Ecma International Org.
Currently ECMAScript available in multiple versions that are ES5 and ES6 and both of versions fully supported to Chrome,
 Firefox, Opera, Safari, and IE etc. 

# What is Traceur compiler?
The “Traceur” is a JavaScript compiler. The Traceur compiler is very popular now days use to allow use to use the features 
from the future. This compiler is fully supported to ES5, ES6 and also to vNext.

The main goal of Traceur compiler is to inform to design of new JavaScript features and wrote the programming code of 
new efficient and good manners.

# What is Advantages of Angular 2?

1.       There is many more advantage of Angular 2.
2.       The Angular 2 has better performance.
3.       The Angular 2 has more powerful template system.
4.       The Angular 2 provide simpler APIs, lazy loading and easier to application debugging.
5.       The Angular 2 much more testable.
6.       The Angular 2 provides to nested level components.
7.       The Angular 2 execute run more than two programs at the same time.

The Angular 2 architecture diagram identifies the eight main building blocks as.

1.       Module
2.       Component
3.       Template
4.       Outpouts
5.       Data Binding
6.       Directive
7.       Service
8.       Dependency Injection

The Angular 2 framework consists of several libraries, the some of them working as core and some are optional.

# Modern browsers are supported in Angular 2? 
All the Angular 2 framework code is already being written in ECMAScript 6.
The set of modern browsers are

1.       Chrome
2.       Firefox
3.       Opera
4.       Safari
5.       IE version10 and 11.

On mobiles, it is supporting to the list of Chrome on Android, iOS 6+, Windows Phone 8+ and 
Fire-Fox mobile and also trying to support to older versions of Android.

# Angular 1 and Angular 2 Integration 
1. Angular frameworks provide the support of mixing code of Angular 1 and Angular 2 in the same application.
2. We can write the mixing components of Angular 1 and Angular 2 in the same view.
3. We can inject services across frameworks of Angular 1 and Angular 2 in the same application.
4. Both Angular 1's and Angular 2's data binding works across frameworks in the same view.

# Best Key Differences - Constructor Vs. ngOnInit [Angular 2] 
Angular 2 Constructors:-
1.      The constructor is a default method runs when component is being constructed.
2.      The constructor is a typescript feature and it is used only for a class instantiations and nothing to do 
with Angular 2.
3.      The constructor called first time before the ngOnInit().

Angular 2 ngOnInit:-
1.      The ngOnInit event is an Angular 2 life-cycle event method that is called after the first ngOnChanges and 
the ngOnInit method is use to parameters defined with @Input otherwise the constructor is OK.
2.      The ngOnInit is called after the constructor and ngOnInit is called after the first ngOnChanges.
3.      The ngOnChanges is called when an input or output binding value changes.
Example as,
```
import {Component, OnInit} from '@angular/core';

export class App implements OnInit{
  constructor(){

  }

  ngOnInit(){

  }
}
```
When will ngInit be called? How would you make use of onNgInit()?

# “What”? “Why”? and “Advantages of Angular2”?
# Why should you use Angular2 ? What are the Advantages of Angular2 ?

The core differences and many more advantages on Angular2 vs. Angular 1 as following,
1.      Angular2 has better performance.
2.      Angular2 has more powerful template system.
3.      Angular2 provide simpler APIs, lazy loading and easier to application debugging.
4.      Angular2 much more testable
5.      Angular2 provides to nested level components.
6.      Angular2 execute run more than two programs at the same time.
7.      Angular1 is controllers and $scope based but Angular2 is component based.
8.      The Angular2 structural directives syntax is changed like ng-repeat is replaced with *ngFor etc.
9.      In Angular2, local variables are defined using prefix (#) hash. You can see the below *ngFor loop Example.

There are more advantages over performance, template system, application debugging, testing, components and nested level components.
For Examples as,
Angular 1 Controller:-
```
var app = angular.module("userApp", []);
   app.controller("productController", function($scope) {
   $scope.users = [{ name: "Anil Singh", Age:30, department :"IT" },
  { name: "Aradhya Singh", Age:3, department :"MGMT" }];
}); 
```
Angular 2 Components using TypeScript:-
Here the @Component annotation is used to add the metadata to the class.
```
import { Component } from 'angular2/core';
@Component({
  selector: 'usersdata',
  template: `<h3>{{users.name}}</h3>`
})
 
export class UsersComponent {
  users = [{ name: "Anil Singh", Age:30, department :"IT" },
  { name: "Aradhya Singh", Age:3, department :"MGMT" }];
}
```
Bootstrapping in Angular 1 using ng-app,
```
angular.element(document).ready(function() {
   angular.bootstrap(document, ['userApp']);
});
```
Bootstrapping in Angular 2,
```
import { bootstrap } from 'angular2/platform/browser';
import { UsersComponent } from './product.component';

bootstrap(UserComponent);
```
The Angular2 structural directives syntax is changed like ng-repeat is replaced with *ngFor etc.

For example as,
```
//Angular 1,
<div ng-repeat="user in users">
     Name: {{user.name}}, Age : {{user.Age}}, Dept: {{user.Department}}
</div>

//Angular2,
<div *ngFor="let user of users">
     Name: {{user.name}}, Age : {{user.Age}}, Dept: {{user.Department}}
</div>
```
# When will ngInit be called? How would you make use of ngOnInit()? 

In Angular 1.x, ngInit is called when template is re-rendered. In other words “ng-init” is called, 
when I take turns back to a page.
In Angular2, there is no “ng-init” but we can create a ways like this using the directive and ngOnInit class. 
Angular 2 provides life cycle hook ngOnInit by default.
The ngOnInit is invoked when the component is initialized and invoked only once when the directive is instantiated. 
It is a best practice to implement these life-cycle interfaces.

According to Angular2 Doc, “The ngOnInit is called right after the directive's data-bound properties have been checked for the first time, 
and before any of its children have been checked. It is invoked only once when the directive is instantiated.”
For example as,
```
import { Directive, Input } from '@angular/core';

@Directive({
  selector: '[ngInit]'
})

class NgInit {
  @Input() ngInit;

  ngOnInit() {
    if(this.ngInit) { this.ngInit(); }
  }
}


In template as following,

<div *ngIf="Timer.dateTime === currentDateTime">
    <div *ngIf="Timer.checked" [ngInit]="Start"></div>
    <div *ngIf="!Timer.checked" [ngInit]="Stop"></div>
</div>
```

# Angular 2  Component Lifecycle Hooks
“Could anyone tell me about the usage of ngOnInit if we already have a constructor?” but 
Angular 2 provides life cycle hook ngOnInit by default.
Angular 2 Components and Directives has multiple life-time hooks where we custom logic can be executed.
Angular 2 Constructors:-
The constructor is a default method runs when component is being constructed.
The constructor is a typescript feature and it is used only for a class instantiations and nothing to do with Angular 2.
The constructor called first time before the ngOnInit().
Example as,
```
import {Component} from 'angular2/core';
import {UserService} from './userService';

@Component({
  selector: ‘list-user’,
  template: `<ul><li *ngFor="#user of users">{{user.name}}</li></ul>`
})

class App_Component {
  users:Array<any>;
  constructor(private _userService: UserService) {
      this.users = _userService.getUsers();
  }
}
```
Angular 2 ngOnInit and ngOnChanges:-

The ngOnInit event is an Angular 2 life-cycle event method that is called after the first ngOnChanges and the ngOnInit 
method is use to parameters defined with @Input otherwise the constructor is OK.
The ngOnInit is called after the constructor and ngOnInit is called after the first ngOnChanges.
The ngOnChanges is called when an input or output binding value changes.
Examples as,
```
import {Component, OnInit} from '@angular/core';
export class App implements OnInit{
  constructor(){
  }

  ngOnInit(){
  }
}
```
Angular 2 ngOnDestroy :-
The ngDestroy directive is called in a component lifecycle just before the instance of the component is finally destroyed.
Example as,
```
@Directive({
    selector: '[destroyDirective]'
})
export class OnDestroyDirective implements OnDestroy {

  //Call Constructor and set hello Msg.
  constructor() {
    this.helloMsg = window.setInterval(() => alert('Hello, I am Anil'), 2000);
  }

  //Destroy to the component
  ngOnDestroy() {
     window.clearInterval(this.helloMsg);
  }
}
```
![Component_Lifecycle](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/Component_Lifecycle.png)

 Angular 2 Complete lifecycle hook interface inventory:-
1.      ngOnChanges - called when an input binding value changes.
2.      ngOnInit - after the first ngOnChanges.
3.      ngDoCheck - after every run of change detection.
4.      ngAfterContentInit - after component content initialized.
5.      ngAfterContentChecked - after every check of component content.
6.      ngAfterViewInit - after component's view(s) are initialized.
7.      ngAfterViewChecked - after every check of a component's view(s).
8.      ngOnDestroy - just before the component is destroyed.

Angular 2 Lifecycle Events Log:-
1.      onChanges
2.      onInit
3.      doCheck
4.      afterContentInit
5.      afterContentChecked
6.      afterViewInit
7.      afterViewChecked
8.      doCheck
9.      afterContentChecked
10. afterViewChecked
11. onChanges
12. doCheck
13. afterContentChecked
14. afterViewChecked
15. onDestroy

# What is the Best way to Declare and Access a Global Variable in Angular 2? 
This post helps us to learn “Declare and Access a Global Variable in Angular 2” using “Typescript” and also share 
the steps to create and use of this global variables.

Steps – 
1.     Create Global Variables.
2.     Import and Use the Global Variables in the Component.
3.     Result
Create Global Variables :- “app.global.ts”
```
import { Injectable } from '@angular/core';
@Injectable()

export class AppGlobals {

    readonly baseAppUrl: string = 'http://localhost:57431/';

    readonly baseAPIUrl: string = 'https://api.github.com/';

}
```
Import and Use the Global Variables in the Component:- “user.component.ts”
```
import { Component, Injectable} from '@angular/core';

import { CommonModule } from '@angular/common';

import { HttpModule, Http } from '@angular/http';

import { UserService } from '../service/user.service';

import { AppGlobals } from '../shared/app.globals';

@Component({

    selector: 'user',

    templateUrl: './user.component.html',

    styleUrls: ['./user.component.css'],

    providers: [UserService, AppGlobals]

})

export class UserComponent {

    //USERS DECLARATIONS.

    users = [];

    //HOME COMPONENT CONSTRUCTOR

    constructor(private userService: UserService, private _global: AppGlobals) { }

    //GET USERS SERVICE ON PAGE LOAD.

    ngOnInit() {

        this.userService.getAPIUsers(this._global.baseAPIUrl + 'users/hadley/orgs')
        .subscribe(data => this.users = data);

        this.userService.getAppUsers(this._global.baseAppUrl + 'api/User/GetUsers')
        .subscribe(data => console.log(data));   

    }

}

//END BEGIN – USERCOMPONENT
```

“user.server.ts” :-
```
import { Injectable, InjectionToken } from '@angular/core';

import { Http, Response } from '@angular/http';

import 'rxjs/add/operator/map';

//BEGIN-REGION - USERSERVICE

@Injectable()

export class UserService {

    constructor(private _http: Http) {

    }

    getAPIUsers(apiUrl) {

        return this._http.get(apiUrl).map((data: Response) => data.json());

    }

    getAppUsers(apiUrl) {

        return this._http.get(apiUrl).map((data: Response) => data);

    }

}

//END BEGIN – USERSERVICE
```
# Angular 2 Components Example 
In Angular 2, the components are the main way to build or specify HTML elements and business logic on the page.
In AngularJs 1, we are handling using scope, directives and controllers but all those concepts are using in a 
single combined that is called components.
The component is the core functionality of Angular 2 app but we need to know to pass the data in to the components 
to configure them.
To build an Angular 2 application you define a set of components, for every HTML elements, views, and route.
Angular 2 applications must have a root component that contains all other components. That means all Angular 2 applications 
have a component tree.

Application è Component è Component1 and Component2

Example of Components
```
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
    selector: 'home',
    templateUrl: './home.component.html',
    styleUrls: ['./home.component.css'],
})

export class HomeComponent {
    userlist: Users[];

    constructor() {
        this.userlist = [
            { Id: '1001', name: 'Anil Singh', site: 'http://www.code-sample.com' },
            { Id: '1002', name: 'Alok', site: 'http://www.code-view.com' },
            { Id: '1003', name: 'Reena', site: 'http://www.code-sample.xyz' },
            { Id: '1004', name: 'Dilip', site: 'http://www.codefari.com' },
        ];
    }

    values = '';
    onKeyUp(event: any) {
        this.values = event.target.value;
        console.log(this.values);
    };

    onKeyDown(event: any) {
        this.values = event.target.value;
        console.log(this.values);
    };
}

export class Users {
    Id: String;
    name: String;
    site: String;
}

/* For HTML Components
 <input type="text" [(value)]="values" (keyup)="onKeyUp($event)" (keydown)="onKeydown($event)" />
*/
```

Angular 2 Component Summary

·         Angular 2 Component meta-data annotation is used to register the components.
·         Angular 2 components are used to create UI widgets.
·         Angular 2 components are used to split to application into smaller parts.
·         Only one component is used per DOM element.
·         In the Angular 2 components, @View, template and templateUrl are mandatory in the components.

# Angular 2 components vs directives 

Angular 2 components vs directives   
@Components
@Component meta-data annotation is used  to register the components.
The components are used to create UI widgets.
The components are used to split to application into smaller parts.
Only one component is used per DOM element. 
In the components, @View, template and templateUrl are mandatory in the components. 
 
@Directive
@Directive meta-data annotation is used  to register the directives.
The directives are used to add behavior to existing DOM elements.
The directives are use to design a reusable components.
More than one directive are used per DOM element.
The directive do not have @View etc.

Example for using Component.
```    
import {Component, View} from 'angular2/core';

    @Component({
       selector: 'hello-world'
    })
    @View({
       template: "<h1>Hello  {{angular}}</h1>"
    })
    class hello {
        constructor(public angular: string) {}
    }
    <hello-world></hello-world>
```
Example for using Directive.
```
import {Component, View} from 'angular2/core'';
@Component({
    selector: 'user-detail'
})

@View({
    template: "<div> <h1>{{userName}}</h1> <p>{{phone}}</p>"
})

class userDetail {
    constructor(public userName: string, public phone: string) {}
}
<user-detail></user-detail>
```
# Angular 2 @Inputs - How to Passing data into Angular 2 components with @Input? 
@Input allows you to pass data into your controller and templates through html and defining custom properties.
@Input  is used to define an input for a component, we use the @Input decorator.
Angular 2 components is the core components of applications but you must need to know “how to pass data into components to dynamically?” 
and that time you need to define an input component.
You can see the below example for passing the user data in to the components.
Example 1,
```
import { Component, Input } from '@angular/core';

@Component({
  selector: “user-info”,
  template: “<div> Hello, This is {{ userInfo.name}}</div>”
})

export class UserInfo {
  @Input() userInfo;
  constructor() { }
}
<user-info [userInfo]="currentUser"></user-info>
The components <user-info></user-info> is use to render the user information on the view.
```
Example 2,
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  styles: [`
    .app {
      text-align: center;
      background: #f5f5f5;
    }
  `],
  template: `
    <div class="app">
      <counter [count]="defaultCount"></counter>
    </div>
  `
})
export class AppComponent {
  defaultCount: number = 20;
}
```
# Angular 2 Component Outputs [@Output Property] 
@Output decorator is used to binds a property of a component to send the data from child component to parent component and 
this is a one-way communication.
@Output decorates output properties and its binds a property of the type of angular EventEmitter.
If you want to bind an event on an element, you can use the new Angular2 events i.e.
```
@Component(...)
   class yourComponent {
      addUser(event) {
     }
}
```
The method addUser() will be called when user clicked on button.
```
<button (click)="addUser()">Click</button>
<button (click)="addUser($event)"></button>
```
# What happen if you want to create a custom event?
Now come to the outputs, if you want to create your custom event in Angular 2 that time we will use to new @Outputdecorator.
Examples,
```
import { Component} from 'angular2/core';
import {  bootstrap} from 'angular2/platform/browser';

@Component({
    selector: 'my-app',
    providers: [Service],
    template: '<div>Hello my name is {{name}}!</div>'
})
class MyApp {
    constructor(service: Service) {
        this.name = service.getName();
        setTimeout(() => this.name = 'Anil Singh,', 1000);
    }
    }
    class Service {
      getName() {
        return 'Hello';
    }
}

bootstrap(App);
```
In the above example, we will need to import Output and Event-Emitter to create our new custom event.
```
import { Component , Output, EventEmitter} from 'angular2/core';
import {  bootstrap} from 'angular2/platform/browser';

@Component({
    selector: 'my-app',
    providers: [Service],
    template: '<div>Hello my name is {{name}}!</div>'
})
class MyApp {
    constructor(service: Service) {   
        this.userClicked.emit(this.user);

        this.name = service.getName();

        setTimeout(() => this.name = 'Anil Singh,', 1000);
    }
 }
 class Service {
      getName() {
        return 'Hello';
    }
   @Output() userClicked = new EventEmitter();
}
bootstrap(App);
```
Now when we are using the components anywhere in our application, we can bind the custom event i.e.
```
<my-app (userClicked)="userClicked($event)"></my-app>
```
# Angular 2 Hidden Attribute with Multiple Examples 
Angular 2 [hidden] is a special case binding to hidden property.
 It is closest cousin of ng-show and ng-hide.
It is more powerful to bind any property of elements. Both the ng-show and ng-hide are used to manage the visibility of 
elements using ng-hide css class. It is also set the display property “display:none”.
All the above features are supported in Angular 2 but added some extra feature like animations etc.
```
<div [hidden]="!active">
    Hello, this is active area!
</div>
```
Note: - Don't use hidden attribute with Angular 2 to show/hide elements.


# Don't use hidden attribute with Angular 2. Here is why?
The hidden attribute is used to hide elements. Browsers are not supposed to display elements that have 
the hidden attribute specified. Browsers attach "display: none" styles to elements with hidden attribute.
Example,
```
import { Component } from 'angular2/core';

@Component({
  selector: 'demo',
  templateUrl: 'app/component.html'
})
export class MainComponent {
  Ishide: true;
}

<div [hidden]="Ishide">
     Hey, I’m using hidden attribute.
</div>
```
Works great but some time its override hidden attribute with some css and that time behave wrong!..
For example,
```
Be sure to don't have a display css rule on your <p> tags who override hidden behaviour like i.e.
p {  
    display: inline-block !important;
}
```
The above hidden html attributes acts like display: none;

# How do Components Communicate with Each Other in Angular 2? 
In Angular 1, I have some ways to communicate between controllers i.e.
1.      $rootScope,
2.      $scope,
3.      $emit,
4.      $broadcast

Now In Angular 2, we have different ways to communicate between components.
A parent component and its children share a service whose interface enables bi-directional communication within the family.
The following examples for Services communication,
```
import {Injectable} from '@angular/core';

@Injectable()
export class MyService {
  constructor() { }
}
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './myApp.component.html'
})
export class MyAppComponent { }
```
The following example to calling service from any other component,
```
import {Component, OnInit} from '@angular/core';
import {MyService} from './app/myService'; 

@Component({
  selector: '<my-component></my-component>',
  templateUrl: 'app/component.html',
  providers: [MyService]
})

export class MyComponent implements OnInit {
  constructor(private msInstance: MyService) {}
  ngOnInit() { 
      this.msInstance.getServices(); 
  }
}
```
Example for Sibling Component Communication,
```
import { Component, ViewChild, AfterViewInit } from '@angular/core';
import { ListComponent } from './list.component';
import { DetailComponent } from './detail.component';

@Component({
  selector: 'app-component',
  template: '<list-component></list-component><detail-component></detail-component>',
  directives: [ListComponent, DetailComponent]
})
class AppComponent implements AfterViewInit {
  @ViewChild(ListComponent) listComponent:ListComponent;
  @ViewChild(DetailComponent) detailComponent: DetailComponent;

  ngAfterViewInit() {
    // afther this point the children are set, so you can use them
    this.detailComponent.doSomething();
  }
}
```
# How To Display Validation and Error Messaging on form submit in Angular 2?
In Angular 1, the ng-messages modules are used to help us to display error messages and validation to our forms.
In Angular 2, the ngModel provides error objects for each of the built-in input validators. You can access these errors 
from a reference to the ngModel itself then build useful messaging around them to display to your users.
And also, we can use the properties “pristine” and “touched” to display error messages.
1.      If we want to display errors after the user fills something in a field, use the pristine property.
2.      If we want to display errors after the user put the focus on a field, use the touched property.
Example as,
```
<div *ngIf="(!loginForm.controls.email.valid && !loginForm.controls.email.pristine)">
  **Email is required.
</div>
```
# What is an Angular 2 Service?
Angular 2 service is a class that encapsulates some methods (GET/POST/PUT) and provides it result as a service for 
across your application.

# What are the features of Angular 2 Service?
The Angular 2 is using services concept and it provide the multiple features to us that are,
1.      Services are singleton objects.
2.      Services are capable of returning the data in the form promises or observables.
3.      Service class is decorated with Injectable decorator.
4.      The Injectable decorator is required only if our service class is making use of some Angular injectable 
like Http, 
Response and HttpModule service within it.

# What are the differences between Observables & Promises?
1.      Promise:- Promises are only called once and It can return only a single value at a time and the Promises 
are not cancellable.
2.      Observables:- Observables handle multiple values over time and it can return multiple values and the Observables are cancellable.
3.      The Observables are more advanced than Promises.
# Steps for creating an Angular 2 Service:-
There are four steps as,
1.      Import the injectable member i.e. 
import {Injectable} from '@angular/core';

2.      Import the HttpModule, Http and Response members’ i.e.
import { HttpModule, Http, Response } from '@angular/http';

3.      Add the @Injectable Decorator i.e. @Injectable()

4.      Export to the Service class i.e.
```
export class UserService {

       constructor(private _http: Http) {  }

   }
```
Steps for Calling an Angular 2 Service in the Angular 2 Component class:-
There are four steps to calling a service in component as,
1.      Create or Import the Service to the component class.
2.      Add it as a component provider.
3.      Include it through Dependency Injection.
4.      Use the Service function in the component.
In the below Example, 

I hope this will help you to understand and create the basic of Angular 2 service. I am creating a user service and 
this user service returns the list of users.
After creating user service, I will use the user service “getUsers()” method in the user component’s ngOnInit() method 
to load the returns user collections on user screen.

app.module.ts :-
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { UniversalModule } from 'angular2-universal';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { AppComponent } from './components/app/app.component';
import { UserComponent } from './components/user/user.component';
import { HeaderComponent } from './components/shared/header/header.component';
import { MenuComponent } from './components/menu/menu.component';
import { LoginComponent } from './components/login/login.component';
import { RegistrationComponent } from './components/registration/registration.component';

@NgModule({

    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        UserComponent,
        HeaderComponent,
        MenuComponent,
        LoginComponent,
        RegistrationComponent
    ],
    imports: [
        UniversalModule, // MUST BE FIRST IMPORT. THIS AUTOMATICALLY IMPORTS BROWSERMODULE, HTTPMODULE, 
        AND JSONPMODULE TOO.
        RouterModule.forRoot([ //RouterModule.forRoot method in the module imports to configure the router.
            { path: '', redirectTo: 'user', pathMatch: 'full' },
            { path: 'user/:id', component: UserComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'user' }
        ]),
        FormsModule,
        ReactiveFormsModule 
    ]
})

export class AppModule {
}
```
user.component.ts and user.service.ts :-
```
import { Component, Injectable} from '@angular/core';
import { CommonModule } from '@angular/common';
import { HttpModule, Http, Response } from '@angular/http';

//BEGIN-REGION - USERSERVICE
@Injectable()
export class UserService {
     constructor(private _http: Http) {  }
    getUsers(apiUrl) {
        return this._http.get(apiUrl).map((data: Response) => data.json());
    }
}

//END BEGIN - USERSERVICE

//BEGIN-REGION - USERCOMPONENT

@Component({
    selector: 'user',
    templateUrl: './user.component.html',
    styleUrls: ['./user.component.css'],
    providers: [UserService]

})
export class UserComponent {
    //USERS DECLARATIONS.
    users = [];
    //FETCHING JSON DATA FROM REST APIS
    userRestApiUrl: string = 'https://api.github.com/users/hadley/orgs';
    //HOME COMPONENT CONSTRUCTOR

    constructor(private userService: UserService) {  }
    //GET USERS SERVICE ON PAGE LOAD.

    ngOnInit() {
        this.userService.getUsers(this.userRestApiUrl).subscribe(data => this.users = data);
    }
}

//END BEGIN – USERCOMPONENT
```
user.component.html :-
```
<div class="row">
<div class="col-lg-12">
    <div class="ibox float-e-margins">
        <div class="ibox-title">
            <h2>Angular 2 - User Services</h2>
        </div>
        <hr />
        <div class="ibox-content">
            <div class="table-responsive">
                <table class="table table-striped">
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Name </th>
                            <th>Description </th>
                            <th>URls </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr *ngFor="let user of users; let i = index">
                            <td>{{user.id}}</td>
                            <td>{{user.login}}</td>
                            <td>{{user.description}}</td>
                            <td><a href="{{user.public_members_url}}"> {{user.public_members_url}}</a></td> 
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>        
    </div>
</div>
</div>
```
# What is Pipes?
“Pipes transform displayed values within a template.”
Sometimes, the data is not displays in the well format on the template that time where using pipes.
You also can execute a function in the template to get its returned value.
The angular 2 have some additional pipes names that are async, decimal, percept and so on. And also some of pipes not 
supported in angular 2 that are number, orderBy and filter and these are archiving using “custom pipes”.
Key Points:-
Pipe class implements the “PipeTransform” interfaces transform method that accepts an input value and returns 
the transformed result.
There will be one additional argument to the transform method for each parameter passed to the pipe.
The “@Pipe” decorator allows us to define the pipe name that is globally available for use in any template in the across application.
For example as,
```
import { Pipe, PipeTransform } from '@angular/core';
@Pipe({
    name: 'barcode',
    pure: false
})
export class BarCodePipe implements PipeTransform {
    transform(value: string, args: any[]): string {
        if (!value) {
            return '';
        }
        return "****-****_" + (value.length > 8 ? (value.length - 8): '')
    }
}
```
# Angular 2 Built-in Pipes:-

1.      DatePipe,
2.      UpperCasePipe,
3.      LowerCasePipe,
4.      CurrencyPipe,
5.      PercentPipe,
6.      JsonPipe,
7.      AsyncPipe,
8.      And so on..

# Why use Pipes?
Sometimes, the data is not displays in the correct format on the template that time where using pipes.
You also can execute a function in the template to get its returned value.
For example as,
If you want to display the bank card number on your account detail templates that how to displays this card number?  
I think you should display the last four digits and rest of all digits will display as encrypted like
 (****-****-****_and your card numbers) that time you will need to create a custom pipe to achieve this.

# What is a pure and impure pipe?
In Angular 2, there are two types of pipes i.e.
1.      pure
2.      impure
The pure pipe is by default. Every pipe has been pure by default. If you want to make a pipe impure that time you will 
allow the setting pure flag to false.

Pure Pipes:-
Angular executes a pure pipe only when it detects a pure change to the input value. A pure change can be primitive or non-primitive.
Primitive data are only single values, they have not special capabilities and the non-primitive data types are used to store the group of values.
For example for pipe pure,
```
import { Pipe, PipeTransform } from '@angular/core';
@Pipe({
    name: 'barcode'
})
export class BarCodePipe implements PipeTransform {
    transform(value: string, args: any[]): string {
        if (!value) {
            return '';
        }
        return "****-****_" + (value.length > 8 ? (value.length - 8): '')
    }
}
```
Impure Pipes:-

Angular executes an impure pipe during every component change detection cycle. An impure pipe is called often, 
as often as every keystroke or mouse-move. If you want to make a pipe impure that time you will allow the setting pure flag to false.

For example for pipe impure,
```
import { Pipe, PipeTransform } from '@angular/core';
@Pipe({
    name: 'barcode',
    pure: false
})
export class BarCodePipe implements PipeTransform {
    transform(value: string, args: any[]): string {
        if (!value) {
            return '';
        }
        return "****-****_" + (value.length > 8 ? (value.length - 8): '')
    }

}
```
# What is Async Pipe?
Angular 2 provides us special kinds of pipe that is called Async pipe and the Async pipe subscribes to an Observable or 
Promise and returns the latest value it has emitted.
The Async pipe allows us to bind our templates directly to values that arrive asynchronously manner and this is the great 
ability for the promises and observables.

Example for AsyncPipe with Promise using NgFor,
```
@Component({
    selector: 'app-promise',
    template: '<ul> < li * ngFor="let user of users | async">  Id: {{user.id }}, Name: {{user.name }} </li>< /ul>'
})
export class PromiseComponent {
    //USERS DECLARATIONS.
    users = [];
    //FETCHING JSON DATA FROM REST APIS
    userRestApiUrl: string = 'https://api.github.com/users/hadley/orgs';

    //HOME COMPONENT CONSTRUCTOR
    constructor(private userService: UserService) { }
    //GET USERS SERVICE ON PAGE LOAD.
    ngOnInit() {
        this.userService.getUsers(this.userRestApiUrl).subscribe(data => this.users = data);
    }
}
```
# How to create a custom Pipes?
# How to create a globally available custom “Pipe”?
The “@Pipe” decorator allows us to define the pipe name that is globally available for use in any template in the across application.

Steps for Creating a Custom Pipe:-
1.      Create a typescript class. 
2.      Decorate the class using @Pipe. 
3.      Implement PipeTransform interface. 
4.      Override transform() method. 
5.      Configure the class in application module with @NgModule. 
6.      Ready to use our custom pipe anywhere in application.
In the below example, 

I am using the custom pipe in the user temple to display our custom “Ids” values at the place of Id.
Table of Component
1.      user.component.ts
2.      user.service.ts
3.      custom.barcode.pipe.ts
4.      app.module.ts
5.      user.component.html

user.component.ts :-
```
import { Component, Injectable} from '@angular/core';
import { CommonModule } from '@angular/common';
import { HttpModule, Http } from '@angular/http';
import { UserService } from '../shared/service/user.service';
import { BarCodePipe } from '../shared/pipe/custom.barcode.pipe';
@Component({
    selector: 'user',
    templateUrl: './user.component.html',
    styleUrls: ['./user.component.css']
})

export class UserComponent {
    //USERS DECLARATIONS.
    users = [];
    //FETCHING JSON DATA FROM REST APIS
    userRestApiUrl: string = 'https://api.github.com/users/hadley/orgs';
    //HOME COMPONENT CONSTRUCTOR
    constructor(private userService: UserService) {  }
    //GET USERS SERVICE ON PAGE LOAD.
    ngOnInit() {
        this.userService.getUsers(this.userRestApiUrl).subscribe(data => this.users = data);
    }
}
//END BEGIN - USERCOMPONENT
```
user.service.ts :-
```
import { Injectable } from '@angular/core';
import { Http, Response } from '@angular/http';
import 'rxjs/add/operator/map';
//BEGIN-REGION - USERSERVICE
@Injectable()
export class UserService {
    constructor(private _http: Http) {
    }
    getUsers(apiUrl) {
        return this._http.get(apiUrl).map((data: Response) => data.json());
    }
}

//END BEGIN – USERSERVICE
```
custom.barcode.pipe.ts :-
```
import { Pipe, PipeTransform } from '@angular/core';
@Pipe({
    name: 'barcode',
    pure: false
})
export class BarCodePipe implements PipeTransform {
    transform(value: string, args: any[]): string {
        if (!value) {
            return '';
        }
        return "....-" + (value.length > 2 ? (value.length - 2) : '')
    }
}
```
app.module.ts :-
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { UniversalModule } from 'angular2-universal';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { AppComponent } from './components/app/app.component';
import { UserComponent } from './components/user/user.component';
import { HeaderComponent } from './components/shared/header/header.component';
import { MenuComponent } from './components/menu/menu.component';
import { LoginComponent } from './components/login/login.component';
import { RegistrationComponent } from './components/registration/registration.component';
import { UserService } from './components/shared/service/user.service';
import { BarCodePipe } from './components/shared/pipe/custom.barcode.pipe';
import { MyPipePipe } from './components/shared/pipe/test.pipes';

@NgModule({
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        UserComponent,
        HeaderComponent,
        MenuComponent,
        LoginComponent,
        RegistrationComponent,
        BarCodePipe,
        MyPipePipe
    ],

    imports: [
        UniversalModule, // MUST BE FIRST IMPORT. THIS AUTOMATICALLY IMPORTS BROWSERMODULE, HTTPMODULE, 
        AND JSONPMODULE TOO.
        RouterModule.forRoot([ //RouterModule.forRoot method in the module imports to configure the router.
            { path: '', redirectTo: 'user', pathMatch: 'full' },
            { path: 'user/:id', component: UserComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'user' }
        ]),

        FormsModule,
        ReactiveFormsModule  
    ],
    providers: [UserService]
})
export class AppModule {
}
```
user.component.html :-

```
<div class="row">
<div class="col-lg-12">
    <div class="ibox float-e-margins">
        <div class="ibox-title">
            <h2>Angular 2 - User Services</h2>
        </div>
        <hr />
        <div class="ibox-content">
            <div class="table-responsive">
                <table class="table table-striped">
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>Name </th>
                            <th>Description </th>
                            <th>URls </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr *ngFor="let user of users; let i = index" class="tbl-row-border">
                            <td>{{user.id | barcode: true}}</td>
                            <td>{{user.login}}</td>
                            <td>{{user.description}}</td>
                            <td><a href="{{user.public_members_url}}" target="_blank">{{user.public_members_url}}</a></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div> 
    </div>
</div>
</div>
```
# There are 3 types of directives in Angular 2.
1.     Components Directives - directives with a template
2.     Structural Directives - change the DOM layout by adding and removing DOM elements.
3.     Attribute Directives - change the appearance or behavior of an element, component, or other directive.

# What are components directives?
A component is a directive with a template and the @Component decorator is actually a @Directive decorator extended 
with template oriented features.

1.     To register a component, we use @Component meta-data annotation.
2.     The directives are used to add behavior to existing DOM elements.
3.     The directives are used to design a reusable component.
4.     Only one component can be present per DOM element.
5.     Multiple directives are used per DOM element.
6.     The directive does not have @View etc.

# What are structural directives?
The Structural directives are responsible for HTML layout and It is using Angular 2 for reshape the DOM's structure and also removing, 
or manipulating elements.

# What are attribute directives?
Attribute directives are used to change the behavior, appearance or look of an element on a user input or via data from the service.
For example as,
```
import {Component, View} from 'angular2/core'';
@Component({
    selector: 'user-detail'
})

@View({
    template: "<div> <h1>{{userName}}</h1> <p>{{phone}}</p>"
})
class userDetail {
    constructor(public userName: string, public phone: string) {}
}
<user-detail></user-detail>
```
# Angular 2 Templates with Examples 
A template is a HTML view that tells Angular 2 for render your components in the views.
The Angular 2 templates are very similar to Angular 1 but Angular 2 has some small syntactical changes.
You can see the changes as below,
1.      {}: Is use to rendering the HTML elements.
2.      []: Is use to binding properties.
3.      (): Is use to handling your events.
4.      [()]: Is use to data binding.
5.      *:  Is use to asterisk Operations like *ngFor="let item of items; let i=index;”

A very simple template example as,
{}: RENDERING:
```
 My name is {{name}}
```
[]: BINDING PROPERTIES: 
```
 <user-control [name]="userName"></user-control>
```
(): HANDLING EVENTS:
```
 <your-component (click)="onClick($event)"></your-component>
```
[()]: TWO-WAY DATA BINDING: 
```
 <input [(ngModel)]="userName">
```
*: THE ASTERISK: 
```
 <your-component *ngFor="#user of users"></your-component>
```
# Angular 2 templateUrl and styleUrls 
Angular 2 templateUrl: - The templateUrl is a function which returns HTML template.
Angular 2 styleUrls:- The styleUrls is a component which use to write inline styles, style Urls and 
template inline style.
The example for using templateUrl and styleUrls as,
```
import {Component} from 'angular2/core';

@Component({
    selector: 'app'
    templateUrl: 'index.html',
    styleUrls: ['main_style.css']
})

export class App_Component { }
```
# What are directives?
Angular lets you extend HTML with new attributes called directives.
There are two other kinds of Angular directives,
1.      Components 
2.      Attribute directives

# What are structural directives?
The “Structural directives” are responsible for HTML layout. They shape or reshape the DOM structure; 
it is using for adding, removing and manipulating the elements.
The “Structural directives” is used to enable an element as a template for creating additional elements. 
If you want to create structural directive that time you should have knowledge of template elements and 
structural directives are easy to recognize.
The two familiar examples of structural directive as,
1.      *ngIf
2.      *ngfor
An asterisk (*) precedes the directive attribute name as
```
 <div *ngIf="user" >{{user.name}}</div>
```
# How to creating a structural directive?
```
 @Directive({
  selector: '[appDelay]'
})
export class DelayDirective {
  constructor(
    private templateRef: TemplateRef<any>,
    private viewContainerRef: ViewContainerRef
  ) { }

  @Input()
  set appDelay(time: number): void { }
}
```
# How to create multiple structural directives?
```
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
    styles: [`
    .tabs-sec {
      background-color: #cccff;
      display: flex;
      flex-direction: row;
      width: 100%;
    }
  `],
  template: `
    <div class="tabs-sec">
      <app-tab
        *ngFor="let tab of tabs; let i = index"
        [active]="isSelected(i)"
        (click)="setTab(i)">
        {{ tab.title }}
      </app-tab>
    </div>
    <div [ngSwitch]="tabNumber">
      <template ngFor [ngForOf]="tabs" let-tab let-i="index">
        <app-tab-content *ngSwitchCase="i">
          {{tab.content}}
        </app-tab-content>
      </template>
      <app-tab-content *ngSwitchDefault>clect to select your tab</app-tab-content>
    </div>
  `
})
export class AppComponent {
  tabNumber = -1;
  tabs = [
    { title: 'Blogger1', content: 'Tab Blogger 1' },
    { title: 'Blogger2', content: 'Tab Blogger 2' },
    { title: 'Blogger3', content: 'Tab Blogger 3' },
  ];

  setTab(num: number) {
    this.tabNumber = num;
  }
  
  isSelected(num: number) {
    return this.tabNumber === i;
  }
}
```
# Angular 2 Router Outlet Directives [Angular 2 Route Params and Config] 
Router-outlet directive: - Router-outlet directive is used to render the components for specific location 
of your applications. Both the template and templateUrl render the components where you use this directive.
Syntax:-
```
<router-outlet> </router-outlet>
```
Router-link directive:- Router-link directive is used to link a specific part of your applications.
Syntax:-
```
<router-link> </router-link>
```
Example,
```
<a [router-link]="['/AboutMe']">About Me</a>
```
The Route-Config: - The route config is used to map components to URLs.
```
Syntax:-
@RouteConfig([
        {path: '/',        component: Home_Component, as: 'Home'},
        {path: '/AboutMe', component: AboutMe_Component, as: 'AboutMe'  }
        {path: '/ContactMe', component: ContactMe_Component, as: 'ContactMe'  }
    ])

```
The Route Params: - The route parameter is used to map given URL's parameters based on the rout URLs and it is an optional parameters for that route.

 Syntax:-
 ```
params : {[key: string]: string}
```
Example,
```
@RouteConfig([
         {path: '/employ/:id', component: employe, name: 'emp'},
])
```
# How to use styleUrls and styles in Angular 2? 
The Angular 2 “styles” or “styleUrls” should only be used for css rules and it is affect the style of 
the template elements.
This is the best approaches to add styles directly to the components and the view encapsulation is set per component. It is use for some situations.
An example to add external styles to the components result text color is red,
Syntax –
```
@Component({
    selector: 'home',
    templateUrl: './home.component.html',
    styleUrls: ['./home.component.css'],
    styles: ['.tbl-row-border { border: 1px solid red;}','.txt-color{color:red;}']
})
```

 home.component.html :-

```
<div class="row">
<div class="col-lg-12">
<div class="ibox float-e-margins">
<div class="ibox-title">
    <h5>Angular 2 for loop typescript example - *ngFor</h5>
</div>
<div class="ibox-title">
    <input type="text" [(value)]="values" (keyup)="onKeyUp($event)" /> <strong>Resut- {{values}}</strong>
</div>
<div class="ibox-content">
    <div class="table-responsive">
        <table class="table table-striped">
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Name </th>
                    <th>SiteUrl </th>
                    <th>Actions </th>
                </tr>
            </thead>
            <tbody>
                <tr *ngFor="let user of userlist; let i = index" class="tbl-row-border">
                    <td>{{user.Id}}</td>
                    <td>{{user.name}}</td>
                    <td><a href="{{user.site}}" target="_blank">{{user.site}}</a></td>
                    <td><a (click)="addUser(user)">A</a>|<a (click)="updateUser(user)">E</a>|
                    <a (click)="deleteUser(user)">D</a></td>
                </tr>
            </tbody>
        </table>
    </div>
</div>
</div>
</div>
</div>
```

 home.component.ts :-
```
import { Component } from '@angular/core';
import { CommonModule } from '@angular/common';

@Component({
    selector: 'home',
    templateUrl: './home.component.html',
    //styleUrls: ['./home.component.css'],
    styles: ['.tbl-row-border { border: 1px solid red;}']
})

export class HomeComponent {
    userlist: Users[];

    constructor() {
        this.userlist = [{ Id: '1001', name: 'Anil SIngh', site: 'http://www.code-sample.com' },
        { Id: '1002', name: 'Alok', site: 'http://www.code-view.com' },
        { Id: '1003', name: 'Reena', site: 'http://www.code-sample.xyz' },
        { Id: '1004', name: 'Dilip', site: 'http://www.codefari.com' },
        ];
    }

    values = '';
    onKeyUp(event: any) {
        this.values = event.target.value;
    };

    addUser(user) {
        alert(JSON.stringify(user));
    };

    updateUser(user) {
        alert(JSON.stringify(user));
    };

    deleteUser(user) {
        alert(JSON.stringify(user));
    };
}

export class Users {
    Id: String;
    name: String;
    site: String;
}
```
 app.module.ts :-

```
import { NgModule } from '@angular/core';
import { RouterModule } from '@angular/router';
import { UniversalModule } from 'angular2-universal';
import { AppComponent } from './components/app/app.component';
import { HomeComponent } from './components/home/home.component';
import { HeaderComponent } from './components/shared/header/header.component';
import { MenuComponent } from './components/menu/menu.component';

@NgModule({
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        HomeComponent,
        HeaderComponent,
        MenuComponent        
    ],
    imports: [
        UniversalModule, // Must be first import. This automatically imports BrowserModule, HttpModule, 
        and JsonpModule too.
        RouterModule.forRoot([
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home', component: HomeComponent },
            { path: '**', redirectTo: 'home' }
        ])
    ]
})
export class AppModule {
}
```
# How To Import CSS using System.import? 
You do need the “System.import” to bootstrap and run your application.
It can't run without it, and if it does, you might have a cashed version in your browser.
The error is -
This error indication that some of the script files didn't get loaded correctly!
syntax error: unexpected token 
Syntax is -
```
System.import('./app/bootstrap/css/boots-trap.css!').then(() => {
    System.import('./app/main-app.css!');
});

```
# Load external css style into Angular 2 components 
The “styles” or “styleUrls” should only be used for css rules and it is affect the style of the template elements.
This is the best approaches to add styles directly to the components and the view encapsulation is set per component. 
An example to add external styles to components as,
```
@Component({
    selector: 'app',
    templateUrl: 'app/login.html',
    styleUrls: [
        'app/app.css',
        'app/main.css'
    ],
    encapsulation: ViewEncapsulation.None,
})

export class Component {}
```
# Angular 2 Routing Concepts and Examples 
In the below routing example I am using Angular 2 
for the client side and ASP.NET Core with single page application (SPA) for the server application.
“The Router is use to map applications URLs to application components. There are three main components that you are using to configure routing.”
1.           Routes: - It uses to describe our application's Routes.
2.           Router Imports: - It uses to import our application's Routes.
3.           RouterOutlet: - It is a placeholder component and use to get expanded to each route's content.
4.           RouterLink: - It is use to link to application's routes.
Routes: - The Routes is uses to describe our application's Routes. The “RouterModule.forRoot” method in 
the module imports to configure the router.

# Five concepts that need Routes Representation
1.           Path (a part of the URL)
2.           Route Parameters
3.           Query/Matrix Parameters
4.           Name outlets
5.           A tree of route segments targeting outlets
Syntax:-
```
RouterModule.forRoot([
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home/:id', component: HomeComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'home' }

        ])
```
Example,
```
@NgModule({
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        HomeComponent,
        HeaderComponent,
        MenuComponent,
        LoginComponent,
        RegistrationComponent
    ],

    imports: [
        UniversalModule, // MUST BE FIRST IMPORT. THIS AUTOMATICALLY IMPORTS BROWSERMODULE, HTTPMODULE, 
        AND JSONPMODULE TOO.
        RouterModule.forRoot([ //RouterModule.forRoot method in the module imports to configure the router.
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home/:id', component: HomeComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'home' }
        ]),

        FormsModule,
        ReactiveFormsModule
    ]
})
```
Router Imports - The Angular Router is an optional service that presents a particular component view for a given URL i.e.
```
import { RouterModule, Routes } from '@angular/router';
```
Example,
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { UniversalModule } from 'angular2-universal';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { AppComponent } from './components/app/app.component';
import { HomeComponent } from './components/home/home.component';
import { HeaderComponent } from './components/shared/header/header.component';
import { MenuComponent } from './components/menu/menu.component';
import { LoginComponent } from './components/login/login.component';
import { RegistrationComponent } from './components/registration/registration.component'

@NgModule({

    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        HomeComponent,
        HeaderComponent,
        MenuComponent,
        LoginComponent,
        RegistrationComponent
    ],

    imports: [
        UniversalModule, // MUST BE FIRST IMPORT. THIS AUTOMATICALLY IMPORTS BROWSERMODULE, HTTPMODULE, AND JSONPMODULE TOO.
        RouterModule.forRoot([ //RouterModule.forRoot method in the module imports to configure the router.
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home/:id', component: HomeComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'home' }
        ]),
        FormsModule,
        ReactiveFormsModule
    ]
})

```
Router-outlet directive: - Router-outlet directive is used to render the components for specific location of
your applications. Both the template and templateUrl render the components where you use this directive.
```
Syntax :- <router-outlet></router-outlet>
```
Example
```
<div class='container'>
    <div class='row'>
        <router-outlet></router-outlet>
    </div>
</div>
```
The Route Params: - The route parameter is used to map given URL's parameters based on the rout URLs and 
it is an optional parameters for that route.
```
Syntax: -   params: {[key: string]: string}
```
Example
```
@NgModule({
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        HomeComponent,
        HeaderComponent,
        MenuComponent,
        LoginComponent,
        RegistrationComponent
    ],

    imports: [
        UniversalModule, // MUST BE FIRST IMPORT. THIS AUTOMATICALLY IMPORTS BROWSERMODULE, HTTPMODULE, AND JSONPMODULE TOO.
        RouterModule.forRoot([ //ROUTERMODULE.FORROOT METHOD IN THE MODULE IMPORTS TO CONFIGURE THE ROUTER.
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home/:id', component: HomeComponent }, //HERE ID IS A ROUTE PARAMETER. 
            { path: 'login', component: LoginComponent },
            { path: 'registration', component: RegistrationComponent },
            { path: '**', redirectTo: 'home' }
        ]),
        FormsModule,
        ReactiveFormsModule
    ]
})
```
Router-link directive: - Router-link directive is used to link a specific part of your applications.
```
Syntax :- <router-link></router-link>
```
Example, 
```
<ul class='nav navbar-nav'>
    <li [routerLinkActive]="['link-active']">
        <a [routerLink]="['/login']">
            <span class='glyphicon glyphicon-Login'></span> Login
        </a>
    </li> 
    <li [routerLinkActive]="['link-active']">
        <a [routerLink]="['/registration']">
            <span class='glyphicon glyphicon-Register'></span> Register
        </a>
    </li> 
    <li [routerLinkActive]="['link-active']">
        <a [routerLink]="['/Billing']">
            <span class='glyphicon glyphicon-Billing'></span> Billing
        </a>
    </li> 
</ul>    
```
# Angular2 cookies | angular2 http cookies | angular2 http get set cookie 

Installation:- 
To install ng2-cookies library, run the below given code i.e.
```         
              $npm install ng2-cookies
```
You can include angular2-cookie library for the same which has given below.
```
<script src="~/cookie/angular2-cookie.min.js"></script>
```

In Angular 2 CookieService, 7 methods are available but 6 methods are also available in Angular 1. 
Only one method is added in Angular 2 that is removeAll() method.

The Cookie Service methods as given below
1.                get()
2.                getObject()
3.                getAll()
4.                put()
5.                putObject()
6.                remove()
7.                removeAll()

get() :- This method is returns the value of given cookie key.
getObject() :- This method is returns the desterilized value of given cookie key.
getAll() :- This method is returns a key value object with all the cookies.
put() :- This method is use to set a value for given cookie key.
putObject() :- This method is use to serializes and set a value for given cookie key.
remove() :-This method is use to remove given cookie.
removeAll() :-This method is use to remove all cookies.

You can create your own functions to get cookie value, set cookie value and delete cookie value.
The full example for creating your own functions as,
```
@Component({
    selector: 'cookie-consent',
    template: cookieconsent_html,
    styles: [cookieconsent_css]
})
export class CookieConsent {
    private isConsented: boolean = false;

    constructor() {
        this.isConsented = this.getCookie(COOKIE_CONSENT) === "1";
    }

    private getCookie(name: string) {
        let ca: Array<string> = document.cookie.split(';');
        let caLen: number = ca.length;
        let cookieName = name + "=";
        let c: string;

        for (let i: number = 0; i < caLen; i += 1) {
            c = ca[i].replace(/^\s\+/g, "");
            if (c.indexOf(cookieName) == 0) {
                return c.substring(cookieName.length, c.length);
            }
        }
        return "";
    }

    private deleteCookie(name) {
        this.setCookie(name, "", -1);
    }

    private setCookie(name: string, value: string, expireDays: number, path: string = "") {
        let d:Date = new Date();
        d.setTime(d.getTime() + expireDays * 24 * 60 * 60 * 1000);
        let expires:string = "expires=" + d.toUTCString();
        document.cookie = name + "=" + value + "; " + expires + (path.length > 0 ? "; path=" + path : "");
    }

    private consent(isConsent: boolean, e: any) {
        if (!isConsent) {
            return this.isConsented;
        } else if (isConsent) {
            this.setCookie(COOKIE_CONSENT, "1", COOKIE_CONSENT_EXPIRE_DAYS);
            this.isConsented = true;
            e.preventDefault();
        }
    }
}
```


Use of Angular 2 cookies, the example in detail as give below

//Use of Angular 2 cookies, the example in detail as give below.
```
import {Component} from 'angular2/core';
import {Cookie} from 'angular2-cookie/core';

@Component({
    selector: 'my-cookie-app',
    template: '<div>Cookies in Angular 2</div>',
    providers: [Cookie]
})

export class App_Component {
    constructor(private _cookie:Cookie){}
 
    getCookie(key: string){
        return this._cookie.get(key);
    }

    getCookieObject(key: string){
        return this._cookie.getObject(key);
    }
}
```
//And other are available methods [put(), putObject(), remove() and removeAll()] 
//All methods work similar like above methods.

# Dependency Injection (DI) in Angular 2 [Why @Injectable()?] 
Dependency Injection is a powerful pattern for managing code dependencies.
Angular 2 Dependency Injection consists of three things.
              1.       Injector
              2.       Provider
              3.       Dependency

Injector :- The injector object use to create instances of dependencies.

Provider :- A provider is help to injector for create an instance of a dependency. 
A provider takes a token and maps that to a factory function that creates an object.

Dependency :- A dependency is the type of which an object should be created.

# Why @Injectable()?
@Injectable() marks a class as available to an injector for instantiation. An injector reports an error when 
trying to instantiate a class that is not marked as @Injectable().

Injectors are also responsible for instantiating components. At the run-time the injectors can read class metadata 
in the JavaScript code and use the constructor parameter type information to determine what things to inject.

# How to use Dependency Injection (DI) correctly in Angular 2?
The basics Steps of Dependency injection,
1.      A class with @Injectable() to tell angular 2 that it’s to be injected “UserService”.
2.      A class with a constructor that accepts a type to be injected.

Example, UserService marked as @Injectable as,
```
import {Injectable, bind} from 'angular2/core';
import {Http} from 'angular2/http';

@Injectable() /* This is #Step 1 */
export class UserService {
  constructor(http: URL /* This is #Step 2 */ ) {
    this.http = URL;
  }
}
```
Example as,
```
import {Injectable} from "@angular/core";
@Injectable()
export class InjectToService {
    id: string;
    constructor() {
        this.resetPasscode();
    }
    resetPasscode(): void {
        this.id = this.generatePasscode();
    }
    private generatePasscode(): string {
        var date = new Date().getTime();

        var pascode = '00X000-00000-7000-Z0000-00000'.replace(/[xy]/, function(f) {
            var random = (date + Math.random() * 16) % 16 | 0;
            date = Math.floor(date / 16);
            return (f == '0' ? random : (random & 0x3 | 0x8)).toString(16);
        });

        return pascode;
    };
}
```
# What are the difference between @Inject and @Injectable?
@Inject() - Angular 2
Angular 2 @Inject() is a special technique for letting Angular know that a parameter must be injected.
Example as,
```
import { Inject } from '@angular/core';
import { Http } from '@angular/http';

class UserService {
  users:Array<any>;

  constructor(@Inject(Http) http:Http) {
    //TODO AS PER YOU.
  }
}
```

@Injectable() - Angular 2

@Injectable() marks a class as available to an injector for instantiation. An injector reports an error when trying to instantiate a class that is not marked as @Injectable().

# How to use Dependency Injection (DI) correctly in Angular 2?
The basics Steps of Dependency injection,
1.      A class with @Injectable() to tell angular 2 that it’s to be injected “UserService”.
2.      A class with a constructor that accepts a type to be injected.

Example, UserService marked as @Injectable as,
```
import {Injectable, bind} from 'angular2/core';
import {Http} from 'angular2/http';

@Injectable() /* This is #Step 1 */
export class UserService {
  constructor(http: Http/* This is #Step 2 */ ) {
    this.http = Http;
  }
}
```
# Angular 2 @NgModel [Purpose Of Root Module & Export Module] 
The @NgModule is a new decorator. This module is recently added in Angular 2.

The @NgModule is a class and work with the @NgModule decorator function. @NgModule takes a metadata object 
that tells Angular “how to compile and run module code”.
The @NgModules page guides you from the most elementary @NgModule to a multi-faceted sample with lazy modules.

The @NgModule main use to simplify the way you define and manage the dependencies in your applications and 
using @NgModule you can consolidate different components and services into cohesive blocks of functionality.

The Basic Example of @NgModule as,
```
@NgModule({
  imports: [BrowserModule],
  declarations: [YourComponent],
  bootstrap: [YourComponent]
})
class YourAppModule {}
```
# The @NgModule is a way to organize your dependencies for
1.      Compiler
2.      Dependency Injection

The declarations of @NgModule.declarations as,
```
@NgModule({
     declarations: [
        AppComponent,
        YourComponent,
        YourDirective,
        YourPipe,
        ...OTHER DIRECTIVES AND SO ON.
   ]
})
```
The @NgModule providers as,
```
@NgModule({
    providers: [
        YourService,
        SomeLibraryService,
    ],
})
```
The @NgModule exporting as,
```
@NgModule({
    declarations: [YourComponent, YourPipe]
    exports: [YourComponent, YourPipe],
    providers: [YourService]
})
export class YourModule { }
```
# Why Angular 2 modules needed?
An Angular @NgModule allows us to define a context for compiling templates.

# Why @NgModule?
1.      Easy to use Components
2.      Easy to use Directives
3.      Easy to use Pipes
4.      Providers’ Inheritance
5.      Library Architecture
6.      Easy to migrate from angular.module()
7.      So on

# What is a Root Module?
Each application only has one root module and each component, directive and pipe should only be associated to 
a single module. This one is the main reason.

# How Should We Organize Modules?
There are no standard ways to group modules, but the recommendations are,
1.      Features as a module
2.      Shared utilities as a module

Module’s Features:-

For example, suppose that your application has customer, product and feature. Each module has some components, directives and pipes. 

Module’s Utility:-
For the functions or features that can be shared across modules and application, consider creating a shared module.


# How to declaration Module?
```
import {NgModule, ApplicationRef} from '@angular/core';
import {CommonModule} from '@angular/common';
import {FormsModule} from '@angular/forms';
import {MaterialModule} from '@angular2-material/module';
import {AppComponent} from './app.component';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, CommonModule, FormsModule, MaterialModule],
  entryComponents: [AppComponent]
})
class AppModule {
  constructor(appRef: ApplicationRef) {
    appRef.bootstrap(AppComponent);
  }
}
```


//Bootstrapping
```
import {AppModule} from './app.module';
import {platformBrowserDynamic} from '@angular/browser-platform-dynamic';
platformBrowserDynamic().bootstrapModule(AppModule);


@NgModule
class NgModule {
  declarations: Array<ComponentType | DirectiveType | PipeType>;
  imports: Array<ModuleType | ModuleWithProviders>;
  exports: Array<ComponentType | DirectiveType | PipeType | ModuleType>;
  providers: Array<Providers | Array<any> >;
  entryComponents: Array<ComponentType>;
  schemas: Array<any>;
}
```


# What is One Root Module?
When we create an Angular 2 app, we define a root module. We learned about this in the previous post. 
This root module is defined with @NgModule and works quite well for small apps.

// app.module.ts
```
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule],
  declarations: [
    AppComponent,
    VehicleListComponent,
    VehicleSelectionDirective,
    VehicleSortingPipe
  ],
  providers: [
    LoggerService,
    VehicleService,
    UserProfileService
  ],
  bootstrap: [AppComponent],
})
export class AppModule { }  
```
Our root module declares our components, pipes and directives.
Our root module imports common features from the Angular 2 BrowserModule, FormsModule, and HttpModule.
Final Conclusions are,
1.      The Use of NgModule.providers

    a.  Remove Component.providers

2.      Use NgModule.declarations

    a.   Remove Component.directives/pipes

3.      Keep a single scope

4.      Use modules

    a.  Http, Forms, Router, and so on.

5.      Make modules

6.      Module as a Library


# Angular 2 Modules vs. JavaScript Modules vs. Angular 1 Modules 

Angular 2 Modules -
The Angular module — a class decorated with @NgModule — is a fundamental feature of Angular.

JavaScript also has its own module system for managing collections of JavaScript objects.
 It's completely different and unrelated to the Angular module system.
Angular Modules are the unit of reusability.
Angular modules represent a core concept and play a fundamental role in structuring Angular applications.
Every Angular app has at least one module, the root module, conventionally named AppModule.
Important features such as lazy loading are done at the Angular Module level.
Angular Modules logically group different Angular artifacts such as components, pipes, directives, and so on.
Angular Modules help to organize an application into cohesive blocks of functionalities and extend it with capabilities from external libraries.
App module looks like below,
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes  } from '@angular/router';
import { HttpModule } from '@angular/http';
import { FormsModule, ReactiveFormsModule } from '@angular/forms';
import { AppComponent } from './components/app/app.component'
import { NavMenuComponent } from './components/navmenu/navmenu.component';
import { HomeComponent } from './components/home/home.component';
import { UserComponent } from './components/user/user.component';
import { UserService } from './components/service/user.service';
import { BarCodePipe } from './components/pipe/custom.pipe';

export const sharedConfig: NgModule = {
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        NavMenuComponent,
        HomeComponent,
        UserComponent,
        BarCodePipe
    ],
    imports: [
        RouterModule.forRoot([
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home', component: HomeComponent },
            { path: 'user', component: UserComponent },
            { path: '**', redirectTo: 'home' }
        ])
    ],
    providers: [UserService]
};
```
Angular 1 Module -
1.     Services

2.     Directives

3.     Controllers

4.     Filters

5.     Configuration information

6.     And so on…
JavaScript Modules -
In JavaScript Modules, every file is one module. In Angular 2, one component is normally a file.
JavaScript also has its own module system for managing collections of JavaScript objects. 
It's completely different and unrelated to the Angular module system.
Avoid leaking code to the global namespace and thus to avoid naming collisions.
Encapsulate code to hide implementation details and control what gets exposed to the outside.
Structure our applications and we can’t use a single file.

# Angular 2 Compiler | What is Traceur compiler in Angular 2
![Traceurcompiler](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/Traceurcompiler.png) 
The Traceur is a JavaScript compiler. The Traceur compiler used to allow us to use the features from the future. 
The Traceur compiler is fully supported to ECMAScript(ES6) and ES.vNext also.
The main goal of Traceur compiler is to inform the designs of new JavaScript features and also allow us to write 
the code in better manners and it also prefer, tell us to use design patterns.
Now the days Traceur compiler are broadly used in Angularv2.0 because Angular v2.0 are fully used to ES5 and ES6.

# List down the popular AngularJS IDE Plugins/Extensions for web development?

Here is a list of IDE Plugins and Extensions which can enhance the way you code with AngularJS:
◾Sublime Text
◾WebStorm

◾Eclipse

◾Netbeans

◾Visual Studio 2012/2013 Express or higher

◾TextMate

◾Brackets

◾ATOM

# What are the web application security risks that a web developer should avoid while doing development using AngularJS?
Following are the most critical web application development flaws that a developer should take care of:
◾Injection attack.

◾Broken Authentication and Session Management.

◾Cross-Site Scripting (XSS)

◾Insecure direct object references.

◾Security misconfiguration.

◾Sensitive Data Exposure.

◾Missing Functions Level Access Control.

◾Cross Site Request Forgery (CSRF).

◾Using components that possess vulnerabilities.

◾In-validated redirects and forwards.

# What are the security features provided by AngularJS?
AngularJS provides built-in protection from the following security flaws.
◾It prevents cross-side scripting attacks: Cross-site scripting is a technique where anyone can send a request from client side and can get the confidential information easily.

◾It prevents HTML injection attacks.

◾It prevents XSRF protection for server side communication: It can be handled by “Auth token” mechanism. When the user logins for the first time a user id and password is sent to the server and it will, in turn, return an auth token. Now, this token does the authentication in the future transactions.

#### What is the use case of services?

The main use case of Services is to move duplicated code into a single location, acting like a Singleton. It encourages DRY (Don't Repeat Yourself), which is a principle in Software Engineering, aimed at reducing repitition of information or code in a multi-layered architecture.

Services can serve as a method of interaction between an application and a data store. It also can provide communication channels between directives, as well as any other business logic access.

#### How are the services injected to your application?

There are two ways to inject a service into your application:

- Per Application: Provides the service at an application level
- Per Component: Provides the service at a component level (and all child components)

Providing a service at an application level or a higher level creates a single instance of that service and shares it with all sub directives. This is useful in the case of sharing properties or state between service holders.

Providing a service for every different component would create an instance for each of the components with separate resources.

Injecting a service can be done by importing the service and specifying it in the `NgModule`'s metadata array preperty `providers`, and inject it into the directive using it via the constructor. To inject a service into another service, annotate the target service class with `@Injectable`.

```ts
//annotation used for services injecting other services
@Injectable()
export class MessageService {
	//injected service
	constructor(private errorService: ErrorService){}
}
```

#### How do you unit test a service with a dependency?
[insert answer]

#### Why is it a bad idea to create a new service in a component like the one below?

```ts
let service = new DataService();
```

That's a bad idea for several reasons including:

Our component has to know how to create a DataService. If we ever change the DataService constructor, we'll have to find every place we create the service and fix it. Running around patching code is error prone and adds to the test burden.

We create a new service each time we use new. What if the service should cache data and share that cache with others? We couldn't do that.

We're locking the component into a specific implementation of the DataService. It will be hard to switch implementations for different scenarios. Can we operate offline? Will we need different mocked versions under test? Not easy.
* How would you select a custom component to style it.
* What pseudo-class selector targets styles in the element that hosts the component?
* How would you select all the child components' elements?
* How would you select a css class in any ancestor of the component host element, all the way up to the document root?
* What selector force a style down through the child component tree into all the child component views?

We can use the /deep/ selector to force a style down through the child component tree into all the child component views. The /deep/ selector works to any depth of nested components, and it applies both to the view children and the content children of the component.

* What does :host-context() pseudo-class selector targets?

 It works just like the function form of :host(). It looks for a CSS class in any ancestor of the component host element, all the way up to the document root. It's useful when combined with another selector.

* What does the following css do?

```css
:host-context(.theme-light) h2 {
  background-color: red;
}
```

 Applies a background-color style to all <h2> elements inside the component, only if some ancestor element has the CSS class theme-light.
#### What is the diffrence between RouterModule.forRoot() vs RouterModule.forChild()? Why is it important?

* forRoot creates a module that contains all the directives, the given routes, and the router service itself.
* forChild creates a module that contains all the directives and the given routes, but does not include the router service.
It registers the routers and uses the router service created at the root level.
* This is important because location is a mutable global property. Having more than one object manipulating the location is not a good idea.

#### How does loadChildren property work?

```ts
const routes: Routes = [
  ...,
  { path: 'edit', loadChildren: 'app/edit/edit.module#EditModule' },
  ...
]
```

* In the above example, loadChildren tells the router to fetch the EditModule bundle assigned to it *when* the user visits '/edit' url. (To be more precise, it will ask the module loader to find and load it.)
* Router will get the router configuration from edit module.
* It merges EditModule router configuration with the main application configuration.
* Activate all the needed components.

#### Do you need a Routing Module? Why/not?
Yes if the user was expected to navigate between different URLs. The Routing Module interprets the browser's URL as an instruction to load a specific component and its view. The application has to have its main router configured and bootstraped by passing an array of routes to `RouterModule.forRoot()`, and since this returns a module, it has to be added to the `imports` meta property in the main application module.

The RouterModule:

- separates our routing concerns from our feature module
- provides a module to replace or remove when testing our feature module
- provides a common place for require routing service providers including guards and resolvers
- is not concerned with feature module declarations

#### When does a lazy loaded module is loaded?

The `loadChildren` property is used by the Router to map to a bundle and lazy-load it. The router will take our `loadChildren` string and dynamically load in a module, add its routes as child routes to the configuration dynamically and then load the requested route. This will only happen when the route is first requested and the module will be immediately be available for subsequent requests.

Note that lazy-loaded modules should be removed from modules tehy were part of since they will be loaded on demand.


#### Below link doesn't work. Why? How do I fix it?

```html
<div routerLink='product.id'></div>
```

The routerLink should specify a defined path in the routing configuration and the required path parameter (`product.id`). The code above tries to visit a specific product page, so it should be done using *Link Parameters Array*:

```html
<div [routerLink]="['/product', product.id]"></div>
```

The above is correct in the case of having `product/:id` as a path in the application router configuration.


#### Can you explain the difference between ActivatedRoute and RouterState?

After the end of each successful navigation lifecycle, the router builds a tree of ActivatedRoute objects that make up the current state of the router. We can access the current RouterState from anywhere in our application using the Router service and the routerState property. 

RouterState is the current state of the router including a tree of the currently activated routes in our application along     convenience methods for traversing the route tree.

* What is the minimum definition of a component?
* What is the difference between a component and a directive?
* How do components communicate with each other?
* How do you create two way data binding in Angular?
* How would you create a component to display error messages throughout your application?

* What does a lean component mean to you?

Components don't fetch data from the server, validate user input, or log directly to the console. They delegate such tasks to services.
A component's job is to enable the user experience and nothing more. 
It mediates between the view (rendered by the template) and the application logic (which often includes some notion of a model). 
A good component presents properties and methods for data binding. It delegates everything nontrivial to services.
* What does this line do:

```ts
@HostBinding('class.valid') isValid;
```

Binds a host element property (here, the CSS class valid) to a directive/component property (isValid).

* What would be a good use for NgZone service?

The most common use of this service is to optimize performance when starting a work consisting of one or more asynchronous tasks that don't require UI updates or error handling to be handled by Angular. Such tasks can be kicked off via runOutsideAngular and if needed, these tasks can reenter the Angular zone via run.

* Why would you use renderer methods instead of using native element methods?

You are not sure what the context you are doing the rendering. You might be assuming the browser compilation and native DOM methods to be available but that might not be the case. It is better to be safe and let Angular handle the manupulation for elements.
* How do you transition between two states:

```ts
  animations: [
    trigger('heroState', [
      state('inactive', style({
        backgroundColor: '#eee',
        transform: 'scale(1)'
      })),
      state('active',   style({
        backgroundColor: '#cfd8dc',
        transform: 'scale(1.1)'
      })),
      transition('inactive => active', animate('100ms ease-in')),
      transition('active => inactive', animate('100ms ease-out'))
    ])
  ]
```

* How do you define a wildcard state?

```ts
* => *
* => active
```
* Why do you need type definitions?


* How would you define a custom type?


* What is the difference between an Interface and a Class?


* First line below gives compile error, second line doesn't. Why?


* What are Discriminated union types?

https://basarat.gitbooks.io/typescript/content/docs/types/discriminated-unions.html
https://github.com/Microsoft/TypeScript/pull/9163

# What is Void Elements?
void or self-closing elements, and they are written without a separate end tag.
```
<input />
```
# Quoting Literal Values in Attributes
Most of the time, the values of attributes are evaluated as JavaScript expressions
```
<td [ngSwitch]="item.done" >
```
There will be occasions when you need to provide a specific value rather than have Angular read a value from the data model, and this requires additional quoting to tell Angular that it is dealing with a literal value
```
<td [ngSwitch]="'Apples'" >
```

# What is Rest function?
 In javascript you can’t create two functions with the same name and different parameters and expect JavaScript to differentiate between them based on the arguments you provide when invoking the function. This is called
polymorphism, and although it is supported in languages such as Java and C#, it isn’t available in JavaScript. Instead, if you define two functions with the same name, then the second definition replaces the first.
There are two ways that you can modify a function to respond to a mismatch between the number of parameters it defines and the number of arguments used to invoke it.Default parameters deal with the situation where there are fewer arguments than parameters and allow you to provide a default value for the parameters for which there are no arguments.

Using a Default Parameter
```
let myFunc = function (name, weather = "raining") {
 console.log("Hello " + name + "."); console.log("It is " + weather + " today");};
myFunc("Adam");
```
> Rest parameters are used to capture any additional arguments when a function is invoked with additional arguments
Using a Rest Parameter 
```
let myFunc = function (name, weather, ...extraArgs) {
 console.log("Hello " + name + "."); console.log("It is " + weather + " today"); 
for (let i = 0; i < extraArgs.length; i++) {
 
console.log("Extra Arg: " + extraArgs[i]);
 
}
};
myFunc("Adam", "sunny", "one", "two", "three");
```
The rest parameter must be the last parameter defined by the function, and its name is prefixed with an ellipsis(three periods,...). The rest parameter is an array to which any extra arguments will be assigned. 

# Functions as Arguments to Other Functions
```
let myFunc = function (nameFunction) { return ("Hello " + nameFunction() + ".");};
console.log(myFunc(function () { return "Adam";}));
```
> Chaining Functions Calls
```
let myFunc = function (nameFunction) { return ("Hello " + nameFunction() + ".");};

let printName = function (nameFunction, printFunction) {
 
printFunction(myFunc(nameFunction));}printName(function () { return "Adam" }, console.log);
```
> Arrow Functions
```
let myFunc = (nameFunction) => ("Hello " + nameFunction() + ".");
let printName = (nameFunction, printFunction) => printFunction(myFunc(nameFunction));
printName(function () { return "Adam" }, console.log);
```
>VARIABLE CLOSURE :a function inside another function—creating inner and outer functions—then the inner function is able to access the outer functions variables, using a feature called closure.
```
let myGlobalVar = "apples";
let myFunc = function(name) { let myLocalVar = "sunny"; 
let innerFunction = function () {
 
return ("Hello " + name + ". Today is " + myLocalVar + ".");
 
}
 
return innerFunction();
};

console.log(myFunc("Adam"));
```

# Template Strings 
Template strings, which allow data values to be specified inline, which can help reduce errors and result in a more natural development experience. 
>The traditional way to do this is through string concatenation
```
let message ="It is " + weather + " today"

```
> Template String 
Template strings begin and end with backticks (the ` character), and data values are denoted by curly braces preceded by a dollar sign.

```
let message = `It is ${weather} today`;
```
# The Equality Operator (==, !=) vs. the Identity Operator (===, !==)

```
let firstVal = 5;
let secondVal = "5";
if (firstVal == secondVal) 
{ console.log("They are the same");} 
else 
{ console.log("They are NOT the same");}
```
> the equality operator tests that values are the same irrespective of their type.
```
if (firstVal == secondVal) // is true
```
> If you want to test to ensure that the  values and  the types are the same, then you need to use the identity operator (===, three equal signs, rather than the two of the equality operator)
```
if (firstVal === secondVal) // is false
```
# Converting Numbers to Strings
```
let myData1 = (5).toString() + String(5);
```
# Enumerating the Contents of an Array
```
let myArray = [100, "Adam", true];
for (let i = 0; i < myArray.length; i++) 
{ console.log("Index " + i + ": " + myArray[i]);}
console.log("---");
myArray.forEach((value, index) => console.log("Index " + index + ": " + value));
```
# the Built-in Array Methods

```
concat(otherArray): This method returns a new array that concatenates the array on which it has been called with the array specified as the argument. Multiple arrays can be specified.

join(separator): This method joins all the elements in the array to form a string. The argument specifies the character used to delimit the items.

pop(): This method removes and returns the last item in the array.

shift(): This method removes and returns the first element in the array.

push(item): This method appends the specified item to the end of the array.

unshift(item): This method inserts a new item at the start of the array.

reverse(): This method returns a new array that contains the items in reverse order.

slice(start,end): This method returns a section of the array.

sort(): This method sorts the array. An optional comparison function can be used to perform custom comparisons.

splice(index, count): This method removes count:  items from the array, starting at the specified index. The removed items are returned as the result of the method.

unshift(item): This method inserts a new item at the start of the array.

every(test): This method calls the test  function for each item in the array and returns true if the function returns true for all of them and false otherwise.

some(test): This method returns true if calling the test function for each item in the array returns true at least once.

filter(test): This method returns a new array containing the items for which the test function returns true.

find(test): This method returns first item in the array for which the test function returns true.

findIndex(test): This method returns the index of the first item in the array for which the test function returns true.

foreach(callback): This method invokes the callback function for each item in the array, as described in the previous section.

includes(value): This method returns true if the array contains the specified value.

map(callback): This method returns a new array containing the result of invoking the callback function for every item in the array.

reduce(callback): This method returns the accumulated value produced by invoking the callback function for every item in the array.


```
These methods can be chained together to process a data array
```
let products = [ { name: "Hat", price: 24.5, stock: 10 }, 
{ name: "Kayak", price: 289.99, stock: 1 }, 
{ name: "Soccer Ball", price: 10, stock: 0 }, 
{ name: "Running Shoes", price: 116.50, stock: 20 }];

let totalValue = products .filter(item => item.stock > 0) .reduce((prev, item) => prev + (item.price * item.stock), 0);

console.log("Total value: $" + totalValue.toFixed(2));
```