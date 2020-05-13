# What is TypeScript?
TypeScript isn’t a completely new language, it’s a superset of ES6. If we write ES6 code, it’s perfectly valid and compilable TypeScript code. Here’s a diagram that shows the relationship between the languages
![TypeScript](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/TypeScript.PNG)
# What is ES5? What is ES6? 
ES5 is short for “ECMAScript 5”, otherwise known as “regular Javascript”. ES5 is the normal Javascript we all know and love. It runs in more-or-less every browser. ES6 is the next version of Javascript, which we talk more about below.

# What is transpilers/transcompiler?
The TypeScript transpiler takes our TypeScript code as input and outputs browser understandable/ES5 code that nearly all browsers understand.
Note: For converting TypeScript to ES5 there is a single transpiler written by the core TypeScript team. 

# How can we  convert ES6 code (not TypeScript) to ES5 
there are two major ES6-to-ES5 transpilers: traceur²³ by Google and babel²⁴ created by the JavaScript community.

# How to installed TypeScript?
Here is the npm command to install the type script
```
npm install -g typescript
```
# Is it compulsory to use TypeScript for Angular2 programming?
we don’t have to use TypeScript with Angular2. If you want to use ES5 (i.e.“regular” JavaScript), you definitely can. There is an ES5 API that provides access to all functionalityof Angular2.

# What do we get with TypeScript?
There are five big improvements that TypeScript bring over ES5:
• types
• classes
• annotations
• imports
• language utilities (e.g. destructuring)

# Few examples for ES syntax
e.g
```
var name: string;
The syntax name: string says that this function expects name to be a string.

function greetText(name: string): string {
return "Hello " + name;
}

compliling.ts files from command 

$ tsc compiling.ts

```
#Few syntax
```
var name: string = 'Felipe';

var p: Person = new Person();
```
#Arrays are declared
```
var jobs: Array<string> = ['IBM', 'Microsoft', 'Google'];
var jobs: string[] = ['Apple', 'Dell', 'HP'];
```
# Enums
```
enum Role {Employee, Manager, Admin};
var role: Role = Role.Employee;
or initializing

enum Role {Employee = 3, Manager, Admin};

You can also look up the name of a given enum by using its value:

console.log('Roles: ', Role[0], ',', Role[1], 'and', Role[2]);

```
# Any
any is the default type if we omit typing for a given variable. Having a variable of type any allows
it to receive any kind of value
```
var something: any = 'as string';
something = 1;
something = [1, 2, 3];
```
#Void
Using void means there’s no type expected. This is usually in functions with no return value:
function setName(name: string): void {
this.name = name;
}

# Class, Properties, method
```
class Person {
first_name: string;
last_name: string;
age: number;
constructor() {
}
greet() {
console.log("Hello", this.first_name);
}
}
```
# Inheritance and For loop with array
.forEach is a method on Array that accepts a function as an argument and calls that function for each element in the Array.
```
class Report {
 data: Array<string>;

 constructor(data: Array<string>) {
 this.data = data;
 }

 run() {
 this.data.forEach(function(line) { console.log(line); });
 }
}
class TabbedReport extends Report {
headers: Array<string>;
    constructor(headers: string[], values: string[]) {
    super(values)
    this.headers = headers;
    }
    run() {
    console.log(this.headers);
    super.run();
    }
}


```
# Variables in strings
```
var firstName = "Nate";
var lastName = "Murray";
// interpolate a string
var greeting = `Hello ${firstName} ${lastName}`;

var template = ` <div>
<h1>Hello</h1>
<p>This is a great website</p>
</div>`

```
# There are a variety of features in TypeScript/ES6 such as:
• Interfaces
• Generics
• Importing and Exporting Modules
• Annotations
• Destructuring

# What is Fat Arrow Functions?
Fat arrow => functions are a shorthand notation for writing functions.
```
// ES5-like example
var data = ['Alice Green', 'Paul Pfifer', 'Louis Blakenship'];
data.forEach(function(line) { console.log(line); });
```
However with the => syntax we can instead rewrite it like so
```
// Typescript example
var data: string[] = ['Alice Green', 'Paul Pfifer', 'Louis Blakenship'];
data.forEach( (line) => console.log(line) );
```

# Generics Function and Types

## Define a generic identity function using the any type:

```
function identity(arg: any): any {
    return arg;
}

```
## Define a generic identity function using type variable, a special kind of variable that works on types rather than values.

```
function identity<T>(arg: T): T {
    return arg;
}


====

let output = identity<string>("myString");  // type of output will be 'string'
or
let output = identity("myString");  // type of output will be 'string'

```
When access length for array type

```
function loggingIdentity<T>(arg: T): T {
    console.log(arg.length);  // Error: T doesn't have .length
    return arg;
}

```
Can be written

```
function loggingIdentity<T>(arg: T[]): T[] {
    console.log(arg.length);  // Array has a .length, so no more error
    return arg;
}

function loggingIdentity<T>(arg: Array<T>): Array<T> {
    console.log(arg.length);  // Array has a .length, so no more error
    return arg;
}


```


