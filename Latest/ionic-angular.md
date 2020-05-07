[Coding Style](https://angular.io/guide/styleguide)
## Function/ Method Overloading
#1: Any Type
```
function reverse(stringOrArray: any): any {
  // ...
}

```
#2: Union Types
```
function reverse(
  stringOrArray: string | any[]
): string | any[] {
  // ...
}

e.g

reverse(Math.random); // Error!

const elpmaxe: string | any[] = reverse("example");
const numbers: string | any[] = reverse([1, 2, 3, 4, 5]);

```
#3: Union Types + Generics

```
function reverse<T>(
  stringOrArray: string | T[]
): string | T[] {
  // ...
}

```
#4: Function Overloads
```
function reverse(string: string): string;
function reverse<T>(array: T[]): T[];
function reverse<T>(
  stringOrArray: string | T[]
): string | T[] {
  return typeof stringOrArray === "string"
    ? stringOrArray
        .split("")
        .reverse()
        .join("")
    : stringOrArray.slice().reverse();
}

```

## Interface

Contracts that define types
Compiler enforces the contract via type checking.

# Duck Typing

```
interface Duck {
walk:()=> void;
swim: ()=> void;
quack: ()=>void;
}

let probablyADuck ={
walk: ()=console.log('walking like a duck');
swim: ()=console.log('walking like a duck');
quack: ()=console.log('walking like a duck');
}

function FlyOverWater(bird: Duck){

}

FlyOverWater(probablyADuck);

```
## Reusable type for function
interface StringRemover {
    //describing function,
    //parameters are in left side parenthesis,
    //right side 'string' is return type
    (input: string, index: number): string;
}

let remover: StringRemover = function (str: string, i: number): string {
    return str.substring(i);
}

## How to define optional properties in interfaces

```
interface TeslaModelS {
    length: number;
    width?: number;
    wheelbase: number;
    seatingCapacity: number;
    getTyrePressure?: () => number;
    getRemCharging: () => number;
}

```
# Type aliases: e.g  a type that can either be of type string or null:
```
type StringOrNull = string | null;


e.g

function renderObject (objShape: Square | Rectangle | Triangle) {\
    // ...
}
```
# Indexable properties in interfaces

```
interface CustomArray {
    [index: number]: string
}

let cars: CustomArray = ['Hatchback', 'Sedan', 'Land Rover', 'Tesla Model S']
console.log('Element at position 1', cars[1]) // 'Sedan'


e.g

interface TeslaModelSMap {
    engineer: string,
    model: TeslaModelS,
    readonly rating: number
}
interface TeslaModelSReview {
    [id: number]: TeslaModelSMap
}

const TeslaModelSReviewQueue: TeslaModelSReview = [
    {
        engineer: 'John',
        model: modelByJohn1, // modelByJohn1 is of type `TeslaModelS`
        rating: 2
    },
    {
        engineer: 'Ray',
        model: modelByRay1, // modelByRay1 is of type `TeslaModelS`
        rating: 3
    },
    {
        engineer: 'John',
        model: modelByJohn2, // modelByJohn2 is of type `TeslaModelS`
        rating: 4
    },
    // ... other 97 models
]


```

# define function types in interfaces
```
interface Order {
    (customerId: number, modelId: number): boolean 
}

let orderFn: Order = function (cId, mId) {
    // processing the order
    return true // processed successfully!
}
```

# Hybrid types in interfaces

```
interface CarDelivery {
    (string): TeslaModelS,
    getCustomerDetails (): string,
    price: number,
    trackDelivery (): string
}

function manufactureCar (type: string): CarDelivery {
    const model = <CarDelivery> function (type: string) {
        // get the model of type as mentioned in the argument
    }
    model.getCustomerDetails = function () {
        // get the details of customer who has purchased this model
        return 'customer details'
    }
    model.price = 100000
    model.trackDelivery = function () {
        // track the delivery of the model
        return 'tracking address'
    }
    return model
}
let tesla = manufactureCar('tesla')
tesla() // tesla is a function
tesla.getCustomerDetails() // getCustomerDetails is a property defined on function

```

# generics in interfaces

```
interface StackSpec<T> {
    (elements: Array<T>): void
}

function Stack<T> (elements) {
    this.elements = elements
    this.head = elements.length - 1

    this.push = function (number): void {
        this.elements[this.head] = number
        this.head++
    }

    this.pop = function <T>(): T {
        this.elements.splice(-1, 1)
        this.head--
        return this.elements[this.head]
    }

    this.getElements = function (): Array<T> {
        return this.elements
    }
}

let stacksOfStr: StackSpec<string> = Stack
let cars = new stacksOfStr(['Hatchback', 'Sedan', 'Land Rover'])
cars.push('Tesla Model S')

console.log('Cars', cars.getElements()) // ['Hatchback', 'Sedan', 'Land Rover', 'Tesla Model S']

```
