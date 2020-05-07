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
