
# Angular CLI :
is a great tool to create and work with Angular Applications . It takes away all the pain staking work one has to do otherwise manually by making all the configuration files required for bootstrapping an angular application. With few commands it becomes easier to build working components, Services, directives etc .

# Why CLI ?

Setting up Angular could be a tedious work for beginners .I mean what else could be more discouraging for someone learning a new framework than creating a file structure and appending files to it manually and writing that boiler plate code again and again for new projects? And even for those advanced developers who while creating a single component have to create template files , importing component into App.module.ts files declaring it in declarations array and so on.

That’s Why Angular team came up with One Solution.

ANGULAR CLI

Angular cli makes it easier to work in angular environment. As it contains whole bunch of commands to create core building blocks of angular and to even unit -testing them.

CLI is shipped with WebPack which bundles javascript and css files dynamically and add them to index. html like main.bundle.js , polyfill.bundle. js etc. 

# How to install angular/cli

Installation
```
npm install -g @angular/cli
```
Usage
```
ng help
```
Generating and serving
```
ng new PROJECT-NAME
cd PROJECT-NAME
ng serve

ng serve --host 0.0.0.0 --port 4201
```
Generating Components, Directives, Pipes and Services
```
ng generate component my-new-component
ng g component my-new-component # using the alias

# components support relative path generation
# if in the directory src/app/feature/ and you run
ng g component new-cmp
# your component will be generated in src/app/feature/new-cmp
# but if you were to run
ng g component ../newer-cmp
# your component will be generated in src/app/newer-cmp
# if in the directory src/app you can also run
ng g component feature/new-cmp
# and your component will be generated in src/app/feature/new-cmp

> Component 
 ng g component my-new-component  
> Directive  
ng g directive my-new-directive  
> Pipe  
ng g pipe my-new-pipe  
> Service  
ng g service my-new-service  
> Class  
ng g class my-new-class  
> Guard  
ng g guard my-new-guard  
> Interface  
ng g interface my-new-interface  
> Enum  
ng g enum my-new-enum  
Module  
ng g module my-module  



```

#  npm link  is very similar to  npm install -g 

•It creates a folder src/app/nav/ containing these 4 files:
```
nav.component.ts      - The component class + definition 
nav.component.css     - The component stylesheet
nav.component.html    - The component template
nav.component.spec.ts - The component test spec class
```
# Creating html syntax
```
div.bg-primary>a>  

//<div class="bg-primary"><a href=""></a></div> 

```
# Creating a New Angular Application

There are two ways to create a new application using Angular CLI:
ng init: create a new application in the current directory
ng new: create a new directory and run ng init inside the new directory

So ng new is similar to ng init except that it also creates a directory for you.

> Assuming you haven’t created a directory yet, let’s use ng new to create a new project:
```
$ ng new my-app
```

Behind the scenes, the following happens:
a new directory my-app is created
all source files and directories for your new Angular application are created based on the name you specified (my-app) and best-practices from the official Angular Style Guide
npm dependencies are installed
TypeScript is configured for you
the Karma unit test runner is configured for you
the Protractor end-to-end test framework is configured for you
environment files with default settings are created

You will learn more about each of these aspects in the following sections.

At this point you have a working Angular application and your new directory my-app looks like this:
```
├── README.md
├── e2e
│   ├── app.e2e-spec.ts
│   ├── app.po.ts
│   └── tsconfig.e2e.json
├── karma.conf.js
├── package.json
├── protractor.conf.js
├── src
│   ├── app
│   │   ├── app.component.css
│   │   ├── app.component.html
│   │   ├── app.component.spec.ts
│   │   ├── app.component.ts
│   │   └── app.module.ts
│   ├── assets
│   ├── environments
│   │   ├── environment.prod.ts
│   │   └── environment.ts
│   ├── favicon.ico
│   ├── index.html
│   ├── main.ts
│   ├── polyfills.ts
│   ├── styles.css
│   ├── test.ts
│   ├── tsconfig.app.json
│   ├── tsconfig.spec.json
│   └── typings.d.ts
├── tsconfig.json
└── tslint.json
```

Available Options
```
--dry-run: boolean, default false, perform dry-run so no changes are written to filesystem
--verbose: boolean, default false
--link-cli: boolean, default false, automatically link the @angular/cli package (more info)
--skip-install: boolean, default false, skip npm install
--skip-git: boolean, default false, don’t initialize git repository
--skip-tests: boolean, default false, skip creating tests
--skip-commit: boolean, default false, skip committing the first git commit
--directory: string, name of directory to create, by default this is the same as the application name
--source-dir: string, default 'src', name of source directory
--style: string, default 'css', the style language to use ('css', 'less' or 'scss')
--prefix: string, default 'app', the prefix to use when generating new components
--mobile: boolean, default false, generate a Progressive Web App application (see section on upcoming features)
--routing: boolean, default false, add module with routing information and import it in main app module
--inline-style: boolean, default false, use inline styles when generating the new application
--inline-template: boolean, default false, use inline templates when generating the new application
```
# Run $ ng generate --help to see all available options of your locally installed Angular CLI.

Let’s see how you can start your application so you can see it in action.

# Running Your Application

To preview your new application in your browser, navigate to its directory:
```
$ cd my-app
```

and run:
```
$ ng serve
```
> Behind the scenes, the following happens:

1Angular CLI loads its configuration from .angular-cli.json
2Angular CLI runs Webpack to build and bundle all JavaScript and CSS code
3Angular CLI starts webpack dev server to preview the result on localhost:4200

Notice that the ng serve command does not exit and return to your terminal prompt after step 3.

Instead, because it includes LiveReload support, the process actively watches your src directory for file changes. When a file change is detected, step 2 is repeated and a notification is sent to your browser so it can refresh automatically.

To stop the process and return to your prompt, press ctrl-c.

# Adding Features to Your Angular Application

You can use the ng generate command to add features to your existing application:
```
ng generate class my-new-class: add a class to your application
ng generate component my-new-component: add a component to your application
ng generate directive my-new-directive: add a directive to your application
ng generate enum my-new-enum: add an enum to your application
ng generate module my-new-module: add a module to your application
ng generate pipe my-new-pipe: add a pipe to your application
ng generate service my-new-service: add a service to your application
```
The generate command and the different sub-commands also have shortcut notations, so the following commands are similar:
```
ng g cl my-new-class: add a class to your application
ng g c my-new-component: add a component to your application
ng g d my-new-directive: add a directive to your application
ng g e my-new-enum: add an enum to your application
ng g m my-new-module: add a module to your application
ng g p my-new-pipe: add a pipe to your application
ng g s my-new-service: add a service to your application
```

Each of the different sub-commands performs a different task and offers different options and parameters.

# Adding a new component

To add a component with a selector app-site-header, run:
```
$ ng generate component site-header
```
installing component
  create src/app/site-header/site-header.component.css
  create src/app/site-header/site-header.component.html
  create src/app/site-header/site-header.component.spec.ts
  create src/app/site-header/site-header.component.ts
  update src/app/app.module.ts


Angular CLI will automatically adjust the letter case of the file name and component name for you and apply the prefix to the component selector, so the following commands have the same effect:
# All three commands are equivalent
$ ng generate component site-header
$ ng generate component siteHeader
$ ng generate component SiteHeader


# Behind the scenes, the following happens:
a directory src/app/site-header is created
inside that directory 4 files are generated: a CSS file for the component styles
an HTML file for the component template
a TypeScript file with a component class named SiteHeaderComponent and selector app-site-header
a spec file with a sample unit test for your new component

SiteHeaderComponent is added as a declaration in the @NgModule decorator of the nearest module, in this case the AppModule in src/app/app.module.ts

# Available options
--flat: boolean, default false, generate component files in src/app instead of src/app/site-header
--inline-template: boolean, default false, use an inline template instead of a separate HTML file
--inline-style: boolean, default false, use inline styles instead of a separate CSS file
--prefix: boolean, default true, use prefix specified in .angular-cli.json in component selector
--spec: boolean, default true, generate spec file with unit test
--view-encapsulation: string, specifies the view encapsulation strategy
--change-detection: string, specifies the change detection strategy

Run $ ng generate --help to see all available options of your locally installed Angular CLI.

# Generating a New Route

Routes give us a top level view of our application. We can generate them with:
ng generate route about

Angular CLI ng generate route

Now we have our new files in a weird new folder under src/app. Our new folder is +about. What's up with that?


The + dictates that a folder will be lazy loaded (read more in the style guide. A typical lazy loaded folder contains a routing component, its child components, and their related assets and modules. 

Routing is where the lazy loading takes place, and the route is generated for us via the CLI. Generating a route with the CLI generates a new component and its routing. Let's take a look at the src/app/+about folder:
```
|----- +about/
            |----- shared/
                        |----- index.ts
            |----- about.component.css|html|spec.ts|ts
```

That looks awfully similar to when we ran ng generate component hello. That's because it's a component, just like our HelloComponent.

Where does the routing come into play? We have to go to our top level component (the ScotchyScotchComponent in src/app/scotchy-scotch.component.ts).

You can see that the ROUTER_DIRECTIVES AND THE ROUTER_PROVIDERS were imported into our application, injected into our top-level component, and routed using the 
```
@Routes() decorator.
import { Component } from '@angular/core';
import { AboutComponent } from './+about';
import { Routes , ROUTER_DIRECTIVES, ROUTER_PROVIDERS} from '@angular/router';

@Component({
  moduleId: module.id,
  selector: 'scotchy-scotch-app',
  templateUrl: 'scotchy-scotch.component.html',
  styleUrls: ['scotchy-scotch.component.css'],
  directives: [ROUTER_DIRECTIVES],
  providers: [ROUTER_PROVIDERS]
})
@Routes([
  {path: '/about', component: AboutComponent}
])
export class ScotchyScotchAppComponent {
  title = 'scotchy-scotch works!';
}
```
#Generating a New Component

Components are the foundation of Angular development. Let's generate a new component:
ng generate component hello

Angular CLI ng generate component


Note: It's important to name your component simply. If a component is created with the name hello, these are the corresponding naming schemes:
```
•Folder: hello
•Files: `hello.component.[css,html,spec.ts,ts]
•Class: HelloComponent
```
If you use ng generate component HelloComponent, then your component class will be an undesirable HelloComponentComponent.


Here are the files that get created:
```
|- src/
        |----- app/
                    |----- hello/
                                |----- shared/
                                            |----- index.ts
                                |----- hello.component.css|html|spec.ts|ts
                                |----- index.ts
```
Our new component is relegated to its own folder within the src/app folder.


# Running Your Unit Tests

Angular CLI automatically configures the Karma test runner for you when your application is initially created.

When adding a feature to your application, you can use the --spec option to specify whether you want Angular CLI to also create a corresponding .spec.ts file with a sample unit test for your new feature.

Spec files are created in the same directory of their corresponding feature in the src directory. This allows you to easily locate them when working on a feature.

Running all unit tests of your application thus implies running all unit tests specified in all files ending in .spec.ts in all directories inside your src directory.

To run all unit tests, run:
```
$ ng test
```
# Here is what happens behind the scenes:
1Angular CLI loads .angular-cli.json.
2Angular CLI runs Karma with the configuration specified in .angular-cli.json. By default this is karma.conf.js located in the root directory of your application.
3Karma opens the browser specified in the Karma configuration. By default the browser is set to Google Chrome.
4Karma then instructs the browser (Chrome) to run src/test.ts using the testing framework specified in the Karma config. By default this is the Jasmine framework. The file src/test.ts is automatically created when your application is created. It is pre-configured to load and configure the code that is needed to test your Angular application and run all spec files ending in .spec.ts in your src directory.
5Karma reports the result of the test run to the console.
6Karma watches the src file for changes and repeats step 4 and 5 when a file change is detected.

# Running Your End-to-end (E2E) Tests

Angular CLI automatically configures Protractor for you when your application is initially created.

To run your E2E tests, run:
```
$ ng e2e
```
# Here is what happens behind the scenes:
1Angular CLI loads .angular-cli.json.
2Angular CLI runs Protractor with the configuration specified in .angular-cli.json. By default this is the protractor.conf.js file located in the root directory of your application.
3Protractor opens the browser specified in the Protractor configuration. By default the browser is set to Google Chrome.
4Protractor then instructs the browser (Chrome) to run all spec files ending in .e2e-spec.ts in your e2e directory.
5Protractor reports the result of the test run to the console.

To process then exits automatically after step 5.

If you want to learn more about E2E testing your Angular code, you can check out the Official Angular Testing Guide and the Protractor documentation.

# Building Your Application for Production

Running ng serve builds and bundles your Angular application automatically to a virtual filesystem during development.

However, when your application is ready for production, you will need real files that you can deploy to your server or to the cloud.

To build and bundle your application for deployment, run:
```
$ ng build
```
# What happens behind the scenes is:
1Angular CLI loads its configuration from .angular-cli.json
2Angular CLI runs Webpack to build and bundle all JavaScript and CSS code
3The result is written to the outDir directory specified in your Angular CLI configuration. By default, this is the dist directory.

Available options
--aot: enable ahead-of-time compilation
--base-href: string, the base href to use in the index file
--environment: string, default dev, environment to use
--output-path: string, directory to write the output to
--target: string, default development, environment to use
--watch: boolean, default false, watch files for changes and rebuild when a change is detected

# Targets

Specifying a target impacts the way the build process operates. Its value can be one of the following:
development: default mode, do not minify or uglify code
production: minify and uglify code

Building your application in production mode:
```
$ ng build --target=production
```

results in bundles that are minified, uglified and have hashes in their names:

# Environments

Environments let you specify settings to customize your application behavior.

You can define your own environments in the .angular-cli.json file. The default ones are:
```
source: use settings defined in environments/environment.ts
dev: use settings defined in environments/environment.ts
prod: use settings defined in environments/environment.prod.ts

where environments/environment.ts equals:
export const environment = {
  production: false
};


and environments/environment.prod.ts equals:
export const environment = {
  production: true
};
```

The build process will use the dev environment by default.

If you specify a different environment, the build process will use the corresponding environment:
# Uses environments/environment.ts
```
$ ng build
```
# Also uses environments/environment.ts
```
$ ng build --environment=dev
```
# Uses environments/environment.prod.ts
```
$ ng build --environment=prod
```

As you can see in src/main.ts, you can access the environment settings from your code by importing environments/environment:
```
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule);
```

The build process will make sure the right environment is provided when you import it.

# Deploying Your Application

The ng deploy command has been removed from the core of Angular CLI. Read more here.

# Ejecting your application

As of v1.0, Angular CLI provides a command to decouple your application from Angular CLI.

By default, Angular CLI manages the underlying webpack configuration for you so you don’t have to deal with its complexity.

If, at any given time, you wish to manually configure webpack and you no longer want to use Angular CLI with your Angular application, you can run:
```
$ ng eject
```
What happens behind the scenes is:
1A property ejected: true is added to the .angular-cli.json file
2A webpack.config.js file is generated in the root of your application with a standalone webpack configuration so you can build your project without Angular CLI
3The build script in your package.json is updated so you can run npm run build to build your project
4The test script in your package.json is updated so you can run npm run test or npm test to run your unit tests
5The start script in your package.json is updated so you can run npm run start or npm start to start a development server
6The e2e script in your package.json is updated so you can run npm run e2e to run your end-to-end tests

After ejecting your application, you can manually update the webpack configuration to your liking and the Angular CLI commands will no longer work.

So if, for some reason, you want to move away from Angular CLI, the eject command has you covered.

