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

6)  Styling got their whole collection of technologies now in order to write effective 
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