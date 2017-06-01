# What is webpack?
```
Webpack is a module bundler, it helps you to achieve:
•	it manages your 3rd party app dependencies. Like, if you install libraries with npm, 
    you can use Webpack to import those files using a variety of 
    JavaScript module approaches (like AMD, CommonJS), 
    more lately also the official ES2015 (aka ES6) module spec. 
•	It allows you to do “code splitting”, like splitting JavaScript modules 
    into different files/bundles for better caching or lazy loading. 
•	Via plugins, it helps you minify your files, 
    concatenate them so they’re ready to be deployed in 
    production (as you want to minify your files for performance reasons) 
•	Via plugins it also allows to achieve other stuff, 
    like to inline images, or compile SASS to CSS etc.
All in all, it’s like a task runner, that has already a huge amount of plugins for you, 
ready to use, and which cope most of the use cases one may encounter.

```
# What is BrowserSync?
```
BrowserSync is a tool that synchronizes your code files with one or more browsers. 
Like if you start an application you’re developing and you use browsersync, 
it will keep a WebSocket connection to your development server and whenever you change a file, 
it’ll do a refresh in the browser. Moreover, afaik, you can also 
connect multiple browser which will behave in the same way. 
Like if you scroll in one window, all others will scroll as well. 
This might turn out to be quite useful in mobile testing.

```
# What is Angular CLI?

```
Angular CLI is simply a command line interface that bundles. Like it helps you generate code, 
following the best practices of the official Angular 2 StyleGuide. Under the hood it uses Webpack, 
to the exactly the stuff (minify files, bundle them, etc..). The difference is that you don’t have to know Webpack, 
how it works and how it has to be configured and set up. 
It will be done by the CLI for you, obviously within the limits of it.

```
# How would I go deploying if I dont use CLI?
```
You’d simply have to use Webpack (or some other module bundler + task runner)
 and write the configuration yourself. 
That’s totally fine and there are a couple of good starters out there:
•	Using webpack: 
•	Using SystemJS and Gulp:


```
# Why should you use angular-cli?
```
A project should have a bundler, regardless of the technology stack. 
A bundler is software that bundles your application code along with its resources into a minimized, 
zipped bundle that can be easily deployed on the server (at its most basic form).
There are many bundlers out there, most widely used are Grunt, Gulp and lately, Webpack. 
They each take a different approach to fulfill the task at hand – but Webpack really stands out from the crowd.
While Grunt and Gulp simply bundle all js files and all assets, 
Webpack maintains a dependency tree (by scanning import statements) and 
that allows it to only bundle resources and js files your code actually uses, 
as well as identify chunks of code – using code splitting – and bundle chunks together 
for a more efficient bundle.
Webpack has a lot more to it, it is actually used by the Angular team and is part of it’s documentation. 
However (with its loaders and plugins), it is often overwhelming to properly configure.
The angular team went the extra mile and created anguar-cli – a very powerful tool 
that goes way beyond the simple bundler or generator.
•	It has Webpack under the hood, already pre-configured, so you enjoy the benefits without 
    the hassle of configuration. 
•	It is very easy to use with a set of cli commands, the main ones are: 
•	ng new – create a new angular-cli enabled project 
•	ng init – initialize the current project for angular-cli 
•	ng test – run all unit tests (using karma/jasmine stack) 
•	ng e2e – run all protractor e2e tests 
•	ng serve – will run your app in a local web server 
•	ng build – will compile TypeScript code, bundle the dependency tree and dump it to the dist folder. 
•	ng build --prod – will also minify, zip, hash etc.
•	It comes with a code generator – you can use it to create skeletons of 
    the most common ones (Components, Directives, Services and Pipes) 
    by simply using the cli command ng g <type>.

Now you are probably wondering – how can I modify the underlined Webpack configuration? 
    After all, the only constant thing is change…
    Well, fear not! You have full access to project configuration files like karma.conf.js, 
    protractor.conf.js, tslint.json, tsconfig.json and package.json.
    More over, you can also modify angular-cli configuration using the angular-cli.json file,
    where you have full control of application root folder and configuration files relative locations, 
    as well as specifying css and js files you want loaded into the index.html file 
    as globals (bootstrap and lodash to name a few).

```
# How does Angular CLI compare to Angular2 seed?
```
•	Like in case of Angular Seed you can customise you coding structure I mean to say you can chose 
    any tool to convert your scss to CSS or ts to js for exams Gulp ,grant etc whatever it is, 
    but in case of Angular CLI we don't know who Angular will compile the code and make the project run.
•	Angular CLI comes with Lazy loading whereas in seed we have to setup the same manually.
•	Angular CLI provides you standardised folder structure according to style guide 
    whereas in case of Angular Seed we can customise our structure.

```
# Would you use Webpack with Angular and Angular 2?
```
Webpack is a bundler for modules. The main purpose is to bundle JavaScript files for usage in a browser, 
yet it is also capable of transforming, bundling, or packaging just about any resource or asset.
•	Bundles both CommonJS and AMD modules (even combined). 
•	Can create a single bundle or multiple chunks that are asynchronously loaded 
    at runtime (to reduce initial loading time). 
•	Dependencies are resolved during compilation reducing the runtime size. 
•	Loaders can preprocess files while compiling, e.g. coffeescript to JavaScript, 
    handlebars strings to compiled functions, images to Base64, etc. 
•	Highly modular plugin system to do whatever else your application requires.
We can use webpack for both angular and angular 2. For both its works excellent. 
Specially when writing codes using typescript. It automatically finds all the modules and bundles them. 
You can separate bundles for libraries and application code. 
Awesome thing is its having so many loaders which simplifies complex tasks.
You can use webpack in run time and also can be used with other bundlers and task runners like Gulp, 
Grunt, Karma etc.

```
# What is mean by Full-Stack Web Developer?
```
FULL STACK WEB DEVELOPMENT = 
LAMP STACK + MEAN STACK + RUBY ON RAIL
Mean stack: mostly small scale APIs and some front end work using Angular.
As this MEAN (MongoDB, ExpressJS, AngularJS, NodeJS) 
e.g
Api in NodeJS ( server side ) Client side routing Gulp script with browser-sync and 
nodemon Angular2 components Angular2 services Auth guard - newly introduced in angular2
LAMP (Linux, Apache, MySQL, PHP)

```
# Difference between LAMP STACK and MEAN STACK!
```
• LAMP STACK
    Languages: Perl/PHP/Python: Commonly used programming languages.

    Database: MySQL (RDBMS): Conventional database system.

    Web Server: Apache: Commonly used.

    Servers: “LAMP” is derived from [OS]: Linux (L), Macintosh (M), or 
            Windows (W) Apache web server (A)MySQL (M)
            PHP (often now also Python and Perl) (P)
            Apache is used to host HTTP files, MySQL for databases, 
            and PHP/Python/Perl for Programming language used for creating dynamic webpages.


• MEAN STACK
    Languages: AngularJS: Extension of Javascript.

    Database: MongoDB(NoSQL database): A cross-platform document-oriented database system.
        JSON-style documents with dynamic schemas provide simplicity and power, 
        making the integration of data into certain applications (particularly Javascript-based ones)
        fast and easy.

    Web Server: ExpressJS: is a Node.js Web application framework. It creates an MVC-like application 
    on the server side. 
        It also allows users to create routes and templates.

    Servers:    “MEAN” is derived from MongoDB (M), ExpressJS (E), AngularJS (A), and Node.js (N). 
        Node.js is the server that runs your application. Node.js is an event-driven 
        I/O server-side JavaScript environment.

```
# When Would I Use LAMP vs MEAN?
```
LAMP: Good for : APIs,Simple websites, e-Commerce.

MEAN: Good for: Tech-heavy start-ups, GUI-focused apps and Team who know only Javascript.

```
# How do you integrate sass with node in an Angular CLI project?
```
•	ng set defaults.styleExt scss
Also download node-sass library so that Angular-cli can understand the syntax when building.
•	npm install node-sass --save-dev

or 

if you create a new project completely
•	ng new project --style=scss

```
# How does React JS compare to Angular 2?
```
• Angular2
    Watchers: Watchers are attached to each component and each time a component is changed, 
    watchers check if we should modify something else; and if needed, 
    make appropriate modifications. The Angular 2 team did a great job to make that part way faster 
    than its previous version. 
    So from now on, each time a component is changed, we don’t have to run any verifications on objects 
    (depending on immutable elements).

    There is another striking point in using Angular 2: it requires TypeScript.

• React
    React is more like a UI component render than a full framework. The big thing (that everyone is talking about) 
    is the virtual DOM. 
    This is a killer feature which is giving React three main advantages:

    •	The changes occur by comparison between the DOM and the virtual DOM only, 
        so React will only change what’s needed in the most optimal way. 

    •	We don’t really need a browser to test React as we don’t interact directly with the DOM.

    •	We can connect the Virtual DOM to another entity (look at the mobile developments made in native code or 
    Electron)

    Components created in React have a state (representing the component-related data) and 
    updating this state will allow your page to be reactive. 
    Imagine creating a “counter” component — the thing that you will likely want to change is the value of that 
    counter, it will then be the state of our counter component.


```
# Which is the best platform, Angular 2 or React Js?
```
• Angular 2

    Developed by: Google
    Modern JavaScript: Yes
    Language: TypeScript
    Out-of-box Tools: Great
    Learning Curve: Intermediate
    Advanced Programming: YES
    Performance: Little bit slower but not concerning
    Size: 766k
    Learning Curve: Programming background
    Native Support: Ionic, NativeScript
    MVC Support: Full support
    Rendering: Server side


• React
    Developed by: Facebook
    Modern JavaScript: Yes
    Language: JSX
    Out-of-box Tools: Ok
    Learning Curve: Beginner
    Advanced Programming: No
    Performance: Fast
    Size: 151k
    Learning Curve: JavaScript background
    Native Support: React Native
    MVC Support: View only
    Rendering: Server side
```
# Explain in short: angular-cli ,gulp,yeoman,grunt,systemjs,webpack, browserify, rollup,jspm,seed and requirejs/
```
• bower: Focuses on packages that are used in the browser. 
    Each bower install <packagename> points to exactly one file to be included for (more can be downloaded). 
    Due to the success of webpack, browserify and babel it's mostly obsolete as a first class dependency manager. 

• npm: Historically focuses on NodeJS code but has overthrown bower for browser modules. 
    NPM also loads MANY files into your project and a fresh npm install is always a good reason to brew a new cup 
    of coffee. 
    NPM is easy to use but can break your app when changing environments 
    due to the loose way of referencing versions and the arbitrariness of module publishing. 
    Research Shrink Wrap and npm install --save-exact 
    e.g. Use npm to install node modules for helping me write the application in node.
    Use node as the runtime for my application. ie. run node appname

• npm run-script: You might not need task runners at all. 
    NodeJS scripts are really easy to write so most use-cases allow for customizedtask-automation workflow. 
    Run scripts from the context of your package.json file using npm run-script

• grunt: Facilitates task automation. Gulps older and somewhat more sluggish brother. 
    The JavaScript community used to hang out with him in 2014 a lot. 
    Grunt is already considered legacy in some places but 
    there is still a great amount of really powerful automation to be found. 
    Configuration can be a nightmare for larger use-cases. There is a grunt module for that though.

• gulp: Does the same thing as grunt but is faster.

• webpack Don't miss out on webpack. 
    Especially if you feel lost on the many ways of writing JavaScript into coherent modular code. 
    Webpack packages .js files into modules and does so splendidly. 
    Webpack is highly extensible and offers a good development environment too: 
    webpack-dev-server Use in conjunction with babel for the best possible JavaScript experience to date.

• Yeoman: Scaffolding. Extremly valuable for teams with different backgrounds as it provides a controllable 
    common ground for your projects architecture. There even is a scaffolding for scaffolds.
    e.g. Use yeoman to scaffold a basic skeleton.

```
# What are the difference between node and nodejs...npm vs nvm?
```
• Node and NodeJS: are the same thing, node is just a shorter way to say Node JS. 
    This is assuming that they are both referring to the javascript runtime environment 
    that allows you to write server side code.
• nvm (Node version manager): is a command line interface (CLI) to install different versions of nodejs in 
    your machine.
• npm (node package manager) is a CLI for managing your node modules (e.g. Creating a package, etc).
    It let's you install software (libraries, plugins, frameworks and applications). 
    Typically this software is installed to build Node applications. 
npm depends on Node. nvm installs Node.

```
# Yarn vs npm
```
• npm
npm is the default package manager for Node.js. 
In npm, these tasks are executed per package and sequentially, 
meaning it will wait for a package to be fully installed before moving on to the next.
npm, global operations are performed using the -g or --global flag,
The npm install command will install dependencies from the package.json file and allows you to 
add new packages. 

• Yarn
Facebook package manager called Yarn release at the same time.
Yarn executes these tasks in parallel, increasing performance.
Yarn commands need to be prefixed with global. Just like npm, project-specific dependencies shouldn’t need 
to be installed globally.
yarn install only installs the dependencies listed in yarn.lock or package.json, in that order.



```

# What is Yeoman?
```
Yeoman is a generic scaffolding system allowing the creation of any kind of app. 
It allows for rapidly getting started on new projects and streamlines the maintenance of existing projects.
Yeoman is language agnostic. It can generate projects in any language (Web, Java, Python, C#, etc.)
Yeoman by itself doesn't make any decisions. Every decision is made by generators which are basically 
plugins in the Yeoman environment.
Here are some common use cases:
•	Rapidly create a new project 
•	Create new sections of a project, like a new controller with unit tests 
•	Create modules or packages 
•	Bootstrapping new services 
•	Enforcing standards, best practices and style guides 
•	Promote new projects by letting users get started with a sample app 
•	Etc, etc


```

# Yeoman vs glup 
```
•   Yeoman(A set of tools for automating development workflow) 
    Yeoman supports both Bower and npm, and is flexible in regard to tools to allow it to work with a 
    wider range of project requirements.
    Yeoman supports both major build systems - Grunt and Gulp. These build systems 
    will help you automate tasks such as minification & concatenation of files, 
    running tests, deploying and live-updating your webpage among many others.

•   glup (The streaming build system)
    In Gulp, the transforms are performed through chains which makes it easier to understand 
    the order of operations, and easier to modify it.


```
# In 2003 to 2008 if you need to get the job as a Web Developer, what you should be knowing?
![You would need to be able to do some](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/1.PNG)
```
•   HTML: For UI design.
•   JavaScript: To write some javascript probably for some validation logic or to make some annoying pop-ups 
        appear or something like that. 
•   CSS: To do some styling or to make it attractive.
•   SQL: For writing some sequel to talk to a relational database. 
•   asp.net or asp, PHP, java vb.net, or C#: To do some server-side programming.
```
# These day if you want to get job as a typical Web Developer he has to have following experience.
```
 1)  Different languages that compile to JavaScript and different standards ES2015, ES2016 
    and son on (Transcompile to JS) 
    >   Language that compile to JS 
    •  CoffeeScript: Unfancy JavaScript
    •  EmberScript: Ember.js-infused CoffeeScript.
        
    >   Static typing : Some of the projects listed below are also statically typed.
    •  TypeScript :Typed superset of JavaScript by Microsoft.
    •  ActionScript :With Apache FlexJS - Based on ECMAScript 4, ActionScript provides typing 
            and can be compiled to JavaScript.

    >   JavaScript Language Extensions
    • JSX: A superset to add an XML-like syntax to represent HTML elements in React by Facebook.
    • Dart, Babel, Traceur etc.

2) Different client side Model View Framework as well as libraries 
    • Handlebars:
    • Threejs: 
    • AngularJS : 
    • React: 
    • Ember: 
    • Jquery: 

3) Different Client-side application architecture/ Pattern
    • MVC: bidirectional data flow.  
    • Redux: unidirectional data flow. 
    • other members of flux family . 
4) Package Manager :Package managers simplify installing and updating project dependencies, 
    which are libraries such as: jQuery, Bootstrap,Angularjs,react
    • NPM (node package manager): NPM packages for frontend AND backend. Any NPM package 
        that you find might be intended for node only, browser only, or both.
    • Bower (package manager for the web):When Bower was created, NPM existed already, 
        but it was for node, not the browser. Node packages didn't usually include assets 
        (like bundled JS and CSS) in their NPM packages. If you needed the assets, 
        you would just download them. That's janky - and that's why Bower was created.
    • JSPM (For users of the SystemJS bundler):JSPM doesn't host any of its own packages. 
        It allows you to install packages that are hosted on NPM or github.
    • Yarn (Fast, reliable and secure dependency management):
        the new dependency manager created by the engineers of Facebook. 
5)  Build Tools: Automate your build process.
    
    •	Transcompiling JavaScript: CoffeeScript, Dart, Babel, Traceur etc.
    •	JavaScript Transforms: wrapping in modules or ng-annotate etc.
    •	Bundling/Concatenation: combining of scripts and styles into multiple files
    •	Minification: scripts, styles and html
    •	Source Maps: for both scripts and styles
    •	CSS Preprocessor: Less, Sass, Stylus etc.
    •	Style Transforms: Autoprefixer, PostCSS etc.
    •	Cache Busting: renaming files with a hash to prevent incorrect caching
    •	Image Optimization
    •	Compiling Templates: Mustache or HandlebarsJS, Underscore, EJS, Jade etc.
    •	Copying Assets: html, fav icon etc.
    •	Watching for Changes
    •	Incremental Rebuild
    •	Clean Build: deleting all files at start or preferably cleaning up files as needed
    •	Injecting References: generating script and style tags that reference the bundled files
    •	Build Configurations: separate Dev, Test and Prod configuration, for example to not 
        minify html in dev build
    •	Serve: running a development web server
    •	Running Unit Tests
    •	Running JavaScript and CSS Linters: jshint, csslint etc.
    •	Dependencies: handle dependencies on npm and Bower packages, Browserfy etc.
    > Here is the list  of build tools available
    •	Browserify browser-side require() the node way
    •   Webpack(webpack-dev-server) 
    •	Grunt (configuring )
    •	Gulp (code)
    •	Rollup: focuses particularly on bundling ES6 code. Tree shaking is one of its 
        selling points. 
    •	Traceur is a future-EcmaScript to current-EcmaScript compiler. 

6)  Styling got their whole collection of technologies in order to write effective 
    and maintainable styles.
    
    •   CSS:The standard CSS @import allows you to split into multiple files. 
        The problem with this is that it creates additional HTTP requests.
        
    •   LESS is written in javascript so you will need NodeJS to run it.
        Less tends to be simpler to learn (it's a strict superset of CSS, 
        so any valid CSS file is a valid Less file

    •  SASS: To run you will need to have Ruby installed. 
    •  CSS Reset  (reset.css): Instead of resetting all values
    •  Bootstrap: It provides a framework for creating user interfaces.

7) Different platforms that our code is need to run. 

    • Search Engine Optimization (SEO) :An application that can only run in the client-side 
        cannot serve HTML to crawlers
    • Mobile Computer Science Principles  (CSP) :Build socially useful mobile apps
    • NPM
    • Mobile
    • Nodejs
    • Isomorohic/ Universal.


```
# What is JavaScript Frameworks?
```
It give you space to focus on developing interactive elements of the user interface without worrying 
too much about code structure and code maintenance. JavaScript frameworks work on MVC design paradigm 
and enforce structure to ensure more scalable, reusable, maintainable JavaScript code. 
It however is not necessary that all frameworks ride on MVC pattern, there are many variations to it 
and one has choice to go with MV*, MVVM, MVP as is best suited to the project needs.
```
# Brief discussion of client side Model View Library.
====================================================
# jQuery
```
Plain JavaScript along with jQuery has been used to build complex web interfaces but with lot more 
effort and complexity in code development and maintenance.
``` 
# Handlebars 
```
It’s the templating engine that Ember.js uses. Handlebars works by allowing you to define templates 
using simple script blocks.
```
# Threejs
```
The ever popular Three.js along with the newer Babylon.js offer web developers an abstract foundation 
for crafting feature rich WebGL creations ranging from animated logos to fully interactive 3D games.
 • Three.js was originally written in ActionScript before being translated to JavaScript. Having been 
 created before the introduction of WebGL, Three.js has the unique convenience of a modular rendering 
 interface allowing it to be used with SVG and HTML5’s canvas element in addition to WebGL.
```
# AngularJS 
```
AngularJS framework gives super powers to HTML by adding all the necessary features required to build 
dynamic views (interactive user interface). It gives option to extend HTML attributes by the 
use of Angular directives. Extending HTML with AngularJS is very simple, one can use standard AngularJS 
directive or develop a custom directive and mount it on any div. 
Two way data binding is at the core of Angular.js. When user interacts with the interface and 
provides an input, the view and the model (JavaScript objects) are synchronized, the logic in the model 
is executed and the DOM gets updated.
The reverse is true as well, if model gets updated, view is re-rendered. 
This essentially takes away all the pain of writing manual code for DOM manipulation.
Recently released Framework ReactJS is giving tough competition to AngularJs but 
Angular is holding the ground tight and growing in demand as ever before. The main reason behind Angular's 
continuous growth is the improvements and advancements it brings in with every new release.  

```
# React.js /What powers Facebook and Instagram’s user Interface? 
```
React.js JavaScript Framework is behind the user interface of Facebook as well and Instagram. This gives us 
a quick idea about how powerful is ReactJS when it comes to building large scale applications of extreme 
dynamic nature.
ReactJS was first released as open source in 2013 under BSD license. The community is growing rapidly ever 
since its release and I must say it is the fastest growing JavaScript framework as of today. One can find tons 
of resources, tutorials and React component libraries to get going within no time.
ReactJS is best at rendering complex user interfaces with high performance. The basic fundamental behind 
React is the concept of virtual DOM. ReactJS utilizes a virtual DOM, which can be rendered either at client 
side or server side and communicate back and forth.
When the data manipulation is much more dynamic and complex, client side DOM manipulations become 
performance intensive.
The React approach to handle this is –
•	Render the DOM at server side, the virtual DOM. 
•	Compare virtual DOM to the browser/actual DOM and figure out differences. 
•	Update only the selective/changed nodes of browser DOM instead of re-rendering the entire DOM.
Another biggest advantage of react is the re-usability it brings on the table in the form of reactive components. 
React component libraries can be created and used across applications or made available for public use.

```
# Ember.js
```
•	EmberJS is another powerful MVC JavaScript framework. 
Ember was initially released in 2011 as open source JavaScript framework by Yehuda Katz under MIT license. 
EmberJS competes with the likes of Angular and React when it comes to building interactive 
frontend user interfaces and also has a very active community of developers.
•	Ember also rides on the principal of two way data binding like AngularJS, i.e. update view when model 
changes and update model when the view changes, keeping both in sync all of the time.
Ember is managing to be among the top JavaScript Frameworks by continuously strengthening itself 
with new superpowers. 
•	It is coming up with Fastboot.js module that allows server side rendering of DOM, 
the concept similar to what React is already using for better performance in complex UI rendering.
•   Ember targets the best of both AngularJS (two way data binding) and ReactJS (server side rendering). 
The way Ember community continues to power it with awesome features, I am more than sure that it will continue 
to ride the growing wave of JavaScript Frameworks.

```
# Aurelia.js
```
AureliaJS is the creation of Rob Eisenberg and team who come mostly from the world of Angular and Durandal. 
Aurelia though is an open source product is officially managed by Durandal Inc., a startup company
that creates libraries, tools and frameworks to support next generation of web development.
Aurelia is just released, in January 2015, and is ready for production use. 
• It extends the capabilities of Durandal and is termed as NextGen version of it by Eisenberg. 
For the existing developers who work in Durandal or Angular1 and 2, Aurelia comes with a clear migration path.
AureliaJS is new but if you are evaluating a JavaScript Framework, it definitely needs a consideration. 
It is managed by highly professional community and carries a great legacy.
A power fact about AureliaJS is that it is highly modularized and comprises of many independent small libraries. 
One can use entire framework in the project, use few of the required libraries, or 
extend the selected libraries to create custom framework.
Aurelia is self-contained package and doesn't have any external dependencies except for polyfills.

```
# Meteor.js
```
MeteorJS is the magical full stack platform for building end to end mobile and web applications 
completely in JavaScript at lightning speed. MeteorJS is the power player and comes equipped with all 
the features you need for frontend rendering, backend development, business logic and database management.
Meteor is the baby of Meteor Development Group, it was first released in 2012 as an open source 
JavaScript framework under MIT license.
The MeteorJS ecosystem has grown huge at rapid pace and the community too is vibrant and helpful. 
You would find tons of resources, tutorials and custom packages that give super powers to MeteorJS.
The best thing about MeteorJS is that you use only JavaScript for end to end application development, 
no need to invest time learning anything else. Meteor.JS is modular and the packages and 
libraries can be used on demand.
The server side packages run in the node.js and you do not need anything else but MeteorJS packages 
to access the database, all in JavaScript, this makes MeteorJS applications real time web applications.
From Performance perspective, any changes in the database are reflected back on the UI in the real time and 
vice versa without the handshake between different languages or without major overhead of server response times.

```
# Backbone.js / Are you looking for a lightweight but full featured JavaScript Framework?
```
The popularity and power of backbone can be judged from the fact that biggies like Pinterest, Foursquare, 
Walmart, Disqus and Delicious are using backone.js. 
This is just a small subset of backbone users and the actual list is really huge to be covered here.
The good thing about backbone is that it is simple, small size package and easy to learn. 
You can get started building apps with Backbone JavaScript Framework within no time.
Backbone is very flexible in a way that it comes with just the minimal and you can build anything on top of it, 
by writing your own code or by using third party JavaScript frameworks. 
One can even build a fully functional opinionated framework with backbone at the core.
Over the past few months or so, I see comparatively slow growth in Backbone usage as compared to the rivals 
Angular, Ember or the newly launched React.
The main reason for that appears to be the sluggish release cycle of backbone and lack of power features 
that other frameworks offer out of the box.
• It of course is still useful but more as a side framework rather than the core framework of your web project.

```
# Polymer.js
```
Polymer was released by Google back in 2013. Polymer uses the concept of web components to extend HTML capabilities.
Web Components is the browser technology released by W3C using which new custom HTML elements can be created. 
For example <audio> is a standard HTML5 element but with the web components and related technologies 
you can create your own custom element - like <my-audio>.
Polymer gives powers and brings structure in building custom HTML elements using browser based technologies 
that includes web components.

```
# Knockout.js
```
Knockout works under the MVVM design paradigm and that makes it a little different from Ember and Angular.
Knockout has had its golden time but as of now it is growing at a much slower pace as compared to 
the earlier competitors like Angular, Ember or Backbone. 
The slow growth is simply because it lags way behind in terms of improvements and adding more features.
Developer community is slowly moving to frameworks like React and Angular. 
Knockout has a great legacy and can definitely make a come back but only if someone else adopts it and 
starts nurturing it with the latest and greatest of the world of JavaScript technologies..

```
# Mercury.js
```
It is fast growing in popularity and is getting lot of attention from the community of JavaScript Developers.
Mercury appears to be inspired by react and runs on the concept of virtual DOM rendering. 
It is modern JavaScript framework, fully modular and can be used to the extent you need.
Looking at the underlying concepts, compact size, modular approach, performance and popularity, 
Mercury makes its place in list of best 10 JavaScript frameworks of modern times. 

```
# Vue.js
```
VueJs is relatively new and is gaining lot of traction among the community of developers. 
VueJs works with MVVM design paradigm and has a very simple API. 
VueJs demonstrate minimalism to the extreme and allows you to use selective modules, as required.
Vue is inspired by AngularJS, ReactiveJs, knockoutJS and RivetsJS and 
updates model and view via two way data binding.
While Vue is not in the league of Angular or Ember but conceptually 
has all the potential to be the JavaScript framework of future and hold respactable market share. 
```
=======================================
# Difference Between Angular vs React vs Vue
=======================================
1) A REAL, EXTREME framework comparison
```
• Angular:
It is a full framework with all the tooling and best practices designed on top of it.


• React:
Its on the other hand is just a small view library that you would need while making an app.

• Vue

```
2) Learning curve :Assume you know JavaScript + ES2015 quite well
```
• Angular:
It goes 3rd and although after you learn angular you should know everything else associated to 
it (typescript, MVC…), angular itself is a huge library that requires more time to learn.


• React:
    React to a high standard in just a week.
    It uses the least abstractions, however it will take more time to learn the best practices, 
    as there are a lot of ways in which you can do the same thing or go wrong.

• Vue 
    It is probably the best choice if you want an easy to learn framework.

```

3)  Scalability
```
• Angular: 
It is easy to scale thanks to its design as well as a powerful CLI.
angular is not simple at all. It’s complexity often causes a lot of confusion and angular 
specific 3rd party libraries and syntax
angular is way bigger, causing longer load times and performance issues on mobiles.

• React:
Its claims to be more testable and therefore scalable than vue and I think that is partly true.
react is fairly simple to understand but in fact it takes a long time to set up a react project.
react is bigger than vue, but still smaller than angular. That’s all I’ve got to say.


• Vue
Its being just behind react, it is a good choice however it lacks a list of best scaling practices, 
resulting in a lot of spaghetti code.
vue comes with prebuilt data binding and MVC model, making it way easier to set up 
compared to react and angular.
vue is the smallest and contains a lot as well. Actually you might think it doesn’t matter,
but say that to a cheap android 3g smartphone and I don’t think you will be so sure about it.
```
4)  Beyond the web
```
• Angular:
It comes with ionic 2 and nativescript, but neither of those mobile frameworks allow angular 
to reach the performance of react native.


• React:
It comes with react native, alibaba rax, reactWindows and next.js, it is the best choice when it

• Vue
Its the best choice for vue developers that enjoy native mobile development, all thanks to alibaba weex.
```
1) Templating
```
• Angular:
In Angular, you can only bind to scope. This means that in complex scenarios like 
binding to a server/async service, or when binding to a large model, you will need to have an intermediate 
model in the way, plus you will need to deal with digest cycles and with explicit watches. 


ul>
    <li ng-repeat="item in items">{{item}}</li>
</ul>



• React:
var createItem = function(itemText) {
    return <li>{itemText}</li>;
};
return <ul>{this.props.items.map(createItem)}</ul>;

React only provides syntactic sugar for binding that is called valueLink 
(a single attribute for both "value" and "onChange" properties). 
This concept is so simple that it doesn't sound like it will do the job, yet it does. 
And if you understand it well, you will be able to create your own linkState or similar functions that will 
answer all of your binding needs.

• Vue

```
# ES6 modules 
![ES6 modules compare to old](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/3.PNG)
```
One of the main goals of ES6 modularity is to make it really simple to install and use any Javascript library 
from anywhere on the Internet (github, npm, etc.). Only two things are needed:
•   a single command to install the library (jspm install jquery)
•   One single line of code to import the library and use it (var $ = require('jquery');)

Libraries export objects in a common module format (ES6 modules).
export default function $() { ... }

We import a module into a local scope and use it.	
import $ from 'jquery';

```
# Why is modularity important in JavaScript?
```
Modularity is important in JavaScript by the same reasons it’s important in any other language: 
•   it encourages the development of small isolated modules with clear interfaces, as opposed to 
    large chunks of monolithic code.
•   it helps with testability, as modules can be replaced at runtime with mocks that implement the same interface
•   it improves code maintainability, as smaller and well isolated modules are easier to understand
◾   abstract code: to delegate functionality to specialised libraries so that we don't 
    have to understand the complexity of their actual implementation
◾   encapsulate code: to hide code inside the module if we don't want the code to be changed
◾   reuse code: to avoid writing the same code over and over again
◾   manage dependencies: to easily change dependencies without rewriting our code


```
# Module patterns in ES5 
EcmaScript 5 and earlier editions were not designed with modules in mind. Over time, developers came up with different 
patterns to simulate modular design in JavaScript below are few easy pattern.
```
•   Immediately Invoked Function Expression (IIFE):Its an anonymous function that is invoked when it is declared. 

    ◾encapsulate code complexity inside IIFE so we don't have to understand what the IIFE code does
    ◾define variables inside the IIFE so they don't pollute the global scope 
    (var statements inside the IIFE remain within the IIFE's closure)


(function(){
  // ...
})()

e.g

// Function expression
(function(){
  console.log('test');
})

which is 
// => returns function test(){ console.log('test') } so that we can all it.

•   Revealing Module: Its similar to an IIFE, but we assign the return value to a variable.

    // Expose module as global variable
    var singleton = function(){

    // Inner logic
    function sayHello(){
        console.log('Hello');
    }

    // Expose API
    return {
        sayHello: sayHello
    }
    }()
    // Note that here we used bracket
    We can now access the module's API through the variable:
    // Access module functionality
    singleton.sayHello(); 
 ================================================
Without executing the function at declaration time.

// Expose module as global variable
var Module = function(){

  // Inner logic
  function sayHello(){
    console.log('Hello');
  }

  // Expose API
  return {
    sayHello: sayHello
  }
}


Now access it

Instead, we instantiate a module using the Module constructor function:
var module = new Module();  

to access its public API:
module.sayHello();  
// => Hello


```
# Widely adapted and well known module formats 
Before EcmaScript 6 or ES2015, JavaScript did not have an official syntax to define modules. 
```
◾Asynchronous Module Definition (AMD):Its used in browsers and uses a define function to define modules:

    //Calling define with a dependency array and a factory function
    define(['dep1', 'dep2'], function (dep1, dep2) {

        //Define the module value by returning a value.
        return function () {};
    });

◾CommonJS:Its used in Node.js and uses require and module.exports to define dependencies and modules:

    var dep1 = require('./dep1');  
    var dep2 = require('./dep2');

    module.exports = function(){  
    // ...
    }

◾Universal Module Definition (UMD):It can be used both in the browser and in Node.js.
◾System.register :It was designed to support the ES6 module syntax in ES5:

    import { p as q } from './dep';

    var s = 'local';

    export function func() {  
    return q;
    }

    export class C {  
    }

◾ES6 module format: It uses an export token to export a module's public API.Unfortunately, 
    the native module format is not yet supported by all browsers.
We can already use the ES6 module format today, but we need a transpiler like Babel to transpile 
our code to an ES5 module format such as AMD or CommonJS before we can actually run our code in the browser.

It uses an export token to export a module's public API:
// lib.js

// Export the function
export function sayHello(){  
  console.log('Hello');
}

// Do not export the function
function somePrivateFunction(){  
  // ...
}

and an import token to import parts that a module exports:
import { sayHello } from './lib';

sayHello();  
// => Hello

We can even give imports an alias using as:
import { sayHello as say } from './lib';

say();  
// => Hello

or load an entire module at once:
import * as lib from './lib';

lib.sayHello();  
// => Hello

The format also supports default exports:
// lib.js

// Export default function
export default function sayHello(){  
  console.log('Hello');
}

// Export non-default function
export function sayGoodbye(){  
  console.log('Goodbye');
}

which you can import like this:
import sayHello, { sayGoodbye } from './lib';

sayHello();  
// => Hello

sayGoodbye();  
// => Goodbye

You can export not only functions, but anything you like:
// lib.js

// Export default function
export default function sayHello(){  
  console.log('Hello');
}

// Export non-default function
export function sayGoodbye(){  
  console.log('Goodbye');
}

// Export simple value
export const apiUrl = '...';

// Export object
export const settings = {  
  debug: true
}


```

# What is Module loaders?

A module loader interprets and loads a module written in a certain module format.
```
A module loader runs at runtime.

◾you load the module loader in the browser
◾you tell the module loader which main app file to load
◾the module loader downloads and interprets the main app file
◾the module loader downloads files as needed


A few examples of popular module loaders are:
◾RequireJS: loader for modules in AMD format
◾SystemJS: loader for modules in AMD, CommonJS, UMD or System.register format

```
# What is Module bundlers?
A module bundler replaces a module loader.
```
In contrast to a module loader, a module bundler runs at build time.
◾you run the module bundler to generate a bundle file at build time (e.g. bundle.js)
◾you load the bundle in the browser

Examples of popular module bundlers are:
◾Browserify: bundler for CommonJS modules
◾Webpack: bundler for AMD, CommonJS, ES6 modules


```