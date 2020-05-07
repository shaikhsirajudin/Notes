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
# 1) trackBy

```
Before =========================

<li *ngFor="let item of items;">{{ item }}</li>

After ==========================

// in the template

<li *ngFor="let item of items; trackBy: trackByFn">{{ item }}</li>

// in the component

trackByFn(index, item) {    
   return item.id; // unique id corresponding to the item
}

```

# 2) const vs let

```
Before ====================================

let car = 'ludicrous car';

let myCar = `My ${car}`;
let yourCar = `Your ${car};

if (iHaveMoreThanOneCar) {
   myCar = `${myCar}s`;
}

if (youHaveMoreThanOneCar) {
   yourCar = `${youCar}s`;
}



After ===========================

// the value of car is not reassigned, so we can make it a const
const car = 'ludicrous car';

let myCar = `My ${car}`;
let yourCar = `Your ${car};

if (iHaveMoreThanOneCar) {
   myCar = `${myCar}s`;
}

if (youHaveMoreThanOneCar) {
   yourCar = `${youCar}s`;
}


```

# 3) Pipeable operators

Use pipeable operators when using RxJs operators.


```
Before======================================
import 'rxjs/add/operator/map';
import 'rxjs/add/operator/take';

iAmAnObservable
    .map(value => value.item)
    .take(1);




After =======================================
import { map, take } from 'rxjs/operators';

iAmAnObservable
    .pipe(
       map(value => value.item),
       take(1)
     );


```

# 4) Isolate API hacks
You can also create custom tags like API_FIX similar to TODO and tag the fixes with it so it is easier to find.

# 5) Subscribe in template

Avoid subscribing to observables from components and instead subscribe to the observables from the template.

```
Before
// // template

<p>{{ textToDisplay }}</p>

// component

iAmAnObservable
    .pipe(
       map(value => value.item),
       takeUntil(this._destroyed$)
     )
    .subscribe(item => this.textToDisplay = item);


=================================================================

After
// template

<p>{{ textToDisplay$ | async }}</p>

// component

this.textToDisplay$ = iAmAnObservable
    .pipe(
       map(value => value.item)
     );






```

# 6) Clean up subscriptions

When subscribing to observables, always make sure you unsubscribe from them appropriately by using operators like take, takeUntil, etc.

```
Before
iAmAnObservable
    .pipe(
       map(value => value.item)     
     )
    .subscribe(item => this.textToDisplay = item);



=======================================================================================


After

Using takeUntil when you want to listen to the changes until another observable emits a value:
private _destroyed$ = new Subject();

public ngOnInit (): void {
    iAmAnObservable
    .pipe(
       map(value => value.item)
      // We want to listen to iAmAnObservable until the component is destroyed,
       takeUntil(this._destroyed$)
     )
    .subscribe(item => this.textToDisplay = item);
}

public ngOnDestroy (): void {
    this._destroyed$.next();
    this._destroyed$.complete();
}

Using a private subject like this is a pattern to manage unsubscribing many observables in the component.

Using take when you want only the first value emitted by the observable:
iAmAnObservable
    .pipe(
       map(value => value.item),
       take(1),
       takeUntil(this._destroyed$)
    )
    .subscribe(item => this.textToDisplay = item);


```
