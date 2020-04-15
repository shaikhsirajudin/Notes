``npm install -g @ionic/cli
https://ionicframework.com/docs/cli

# Debugging ionic app

1) Open the integrated Terminal window with Ctrl+` 
2) ionic serve -b (the -b switch will prevent the page from opening in your default browser).
3) Once app is opened in browser, press F5 in visual studio code and it will attach debugger from chrome instance.



#React
https://github.com/ionic-team/ionic-cli/blob/develop/packages/@ionic/cli/CHANGELOG.md
Make sure you have NodeJS v8.9.4+ installed. We recommend the latest LTS version.
Install the cordova-res and native-run utilities.
```
npm i -g cordova-res native-run
```

#For Angular 8 projects, make sure you have the latest 
```
 npm i @angular-devkit/build-angular
  
 npm i @angular-devkit/architect
 npm i @ionic/angular-toolkit@latest

```

@ionic/angular-toolkit installed.

npm i @ionic/angular-toolkit@latest
For Angular 7 projects, make sure you have the latest 1.x @ionic/angular-toolkit installed.

npm i @ionic/angular-toolkit@1


# Create a new project

syntax


ionic start <name> <template> [options]

```
ionic start
ionic start --list
ionic start myApp
ionic start myApp blank
ionic start myApp tabs --cordova
ionic start myApp tabs --capacitor
ionic start myApp super --type=ionic-angular
ionic start myApp blank --type=ionic1
ionic start cordovaApp tabs --cordova
ionic start "My App" blank
```


# Nestjs Install

```
npm install -g @nestjs/cli


```
https://docs.nestjs.com/cli/overview

Starting New project

```
$ nest new my-nest-project
$ cd my-nest-project
$ npm run start:dev

```

ionic is built on top of Node.js, Node.js a Javascript command runner, which can be downloaded nodejs.org

NPM is the package manager built on top node. Most of the ionic tools are deployed as npm packages it's installed with Node. 
You will need Git, a powerful and flexible source control system and its related tools. 

NVM : Its an elegant set of shell script functions to enable the most flexible use of Node imaginable. The primary purpose of NVM is to enable these to install and switch between multiple versions of node and npm instantly. 
e.g
If you have multiple projects some required Node 8,  but another that requires NOde 4. So its easy to both installed, yet still independent from one another. Another most important features of nvm revolve around root or administrator access.
```

nvm install lts  /* latest version of node. */

nvm ls  /* list all the version of node */

```

Installing ionic  cli.

```
npm -g install ionic@rc

```

Setup git locally 

```
git config --global --list

git init  /* A get new repo will be initialize for the project.

git add . /* add all of the project files newly created/changes to repo
git commit -m"Add enm" /* commit the changes to change set

```

git add -A 

This tells git to stage or add everythings in the dirctory to  new change set

git commit -m "Initial commit" --no-gpg-sign

commits the entire change set to my repo locally


this command lists all of your global Git settings, mostly internal things that control how Git works. User.name and user.email are critical. Without them you cant commit. If its not correct you can correct by using following command.
```
git config --global user.name "Shaikh sirajuddin"

git config --global user.email "sirajuddins@lumeris.com"
```

Cordova installing

This tool will crop and resize JPEG and PNG source images to generate images for modern iOS and Android devices. It will also register the generated images in config.xml so that Cordova projects are updated accordingly.

```
npm install -g cordova-res

```

native-run

```
npm install -g native-run

```


ionic info

this command is used to get the information about ionic framework

ionic docs 
to open online documentation url

ionic help 

get all the command related notes


Create a new project

```
ionic start [<name>] [<template>][options]


```
name : The name of your project directory
template: The starter template to use (e.g. blank, tabs use --list to see all)

Steps to start new project

1) ionic start
2) Project name: my-first-app
3) Framework: Angular
4) Strater tempate: tutotrial

To open the current project from command promt.

code .

this ask VS code to opent in the current folder.

ionic.config.json

It contains the name of the application , project type

package.json

Its contain the project name, scripts command e.g npm run clean

```
npm install -E rxjs 

/* this comman ties the npm package to an explicit version.

tsconfig.json and tslint.json

controls various aspects of compiling the TypeScript from Ionic into Javascript and also linting or checking TypeScript for various rules violations. 

To Run from command

```
ionic serve 

/*This will make project to build and then open your system's default broswer to Ionic's local web server */

To get the list of ionic project

```
ionic start --list

```


Blank Template Project

```
ionic start ps-blank blank --no-git --no-link

ionic start ps-tabs tabs --no-git --no-link --type angular

ionic serve /* to run the application */

ionic start ps-sidemenu sidemenu --type angular --no-git --no-link --no-deps

/* no-deps asking ionic not to bother running npm install for us

/* It specifying the no-git and no-link options */
```

# ionic serve

its the simplest command which reload the application when we save the changes.

```
ionic serve [option]
ionic serve --help

```

# ionic lab
It allow quick representation how your app will look on both iOS and Android devices without firing up an emulator. 

```
my-first-project\iconic s -l -b

where s =serve
-l = --lab
-b = --no-open


my-first-project\iconic s -l -b --lab-host 192.168.15.4 --address 192.168.15.4
```

ionic generate --help

ionic generate <type> <name> [options]

Inputs :
 		type  : The type generator(e.g. page, component, service, module; 			use --list to see all)

		name : The of the component being generated
Option:

 	--list, -l    : list available generators
	--dry-run, -d : Run generate without making any file changes
	--force, -f   :Force overwriting of files
Exmaples

```


ionic generate
ionic generate --list
ionic generate -d
ionic generate page
ionic generate page contact
ionic generate component pages/contact/form
ionic generate component form --change-detection OnPuch
ionic generate directive ripple --skip-import
ionic generate s services/api/user

``` 

To run the ionic from command prompt
```
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

# Generating page

```
ionic g pg Game --flat --styleext cc --spec false --route-path game --prefix app --dry-run

/* The "dryRun" flag means no changes were made.

 ionic g pg Game

ionic g e WordTypes

ionic g i IWord

ionic g s Word --spec false --flat false

where flat to false  this causes CLI to create folder anyway

ionic g m components

ionic g c randomWord --inline-style --inline-template --dry-run
ionic g c randomWord --spec false --inline-style --inline-template --export

```

To Install SASS

* Run npm install node-sass
* npm install --save-dev --unsafe-perm node-sass

ng add @angular/material


Update all dependencies

npm install npm@latest -g

Save dev dependancies

```
npm install <package-name> --save-dev
```

# Ionic Code Coverage

Step 1: Install the following modules into your project:
```
npm install --save-dev karma-coverage-istanbul-reporter istanbul-instrumenter-loader

```
Step 2: Add a new script to your package.json file:
```
"test-coverage": "karma start ./test-config/karma.conf.js --coverage",

```
Warning: Step 3 requires files to be replaced. If you have already altered these files, please look at the commits for this project and review the changes. Do not delete or replace files in your project without making backups.

Step 3: Replace your "test-config/karma.conf.js" and "test-config/webpack-test.js" files in your project with those from this project.

Step 4: Run the "npm run test-coverage" command. Your unit tests will be run and the documentation will be generated in a folder named coverage in the root of your project. Just open the index.html file in the folder in a browser and see how well your project is covered.

# Commands That I am running to run to solve the problem:

/*
ng update @angular/cli @angular/core --force

npm install --save-dev @angular-devkit/build-angular
*/


