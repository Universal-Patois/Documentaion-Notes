<style>
r { color: Crimson }
o { color: Coral }
y { color: Khaki }
g { color: MediumSpringGreen }
b { color: SkyBlue }
i { color: Violet }
h { color:  Plum }
hh { color: Pink }
</style>
# <r>TypeScript Notes</r>

## <o>Table of Contents</o>
* [Types used in TypeScript](#types-used-in-typescript)
* [Typing Parameters of functions](#typing-parameters-of-functions)
* [TypeScript events for React](#typescript-for-react)
* [Index Signatures](#index-signatures)

## <o>Types used in TypeScript</o>

* `string`: A string of text. e.g. `"Hello World"`
* `number`: A number. e.g. `10`
* `boolean`: A boolean value. e.g. `true`
* `any`: This type can be used to define variables that can hold any type of value. However, it is not recommended to use this type unless necessary, as it bypasses TypeScript's type checking.
* `void`: No type. Represents the absence of value. Typically used for functions that for not return a value e.g. `undefined`
* `null` and `undefined`: These types are used to represent the absence of value.
* `never`: This type represents the type of values that never occur. This type is typically used for functions that throw errors or infinite loops.
* `Array<T>`: Represents an array of type `T`. e.g. `number[]` represents an array of numbers.
* `Tuple`: Represents an array with a fixed number of elements whose types are known, but need not be the same. e.g. `[string, number]` represents an array with a string and a number.
* `Enum`: Represents a set of named constants. e.g. `enum Color { Red, Green, Blue }` defines an enumeration of colors.
* `Function`: Represents a JavaScript function. This type can be used to define variables that can hold any function. e.g. `let greet: Function; greet = () => console.log("Hello World");`
* `unknown`: Represents a value that is unknown at compile time. This type is similar to `any`, but it is safer because it requires a type assertion or type guard to access its properties or call its methods.

These are some of the most commonly used types in TypeScript, but there are many more types and variations that can be used to define variables and functions. For a complete list of types, see the [TypeScript documentation](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html).

[back to top](#table-of-contents)

## <o>Typing Parameters of functions</o>

### <y>Type a parameter as a string</y>

```ts
function greet(name: string) {
  console.log(`Hello, ${name}!`);
}

greet("John"); // Output: Hello, John!
```

### <y>Type a parameter as a number</y>

```ts
function addNumbers(x: number, y: number) {
  return x + y;
}

const result = addNumbers(10, 5); // Result: 15
```

### <y>Type a parameter as a boolean</y>

```ts
function isOldEnough(age: number): boolean {
  return age >= 18;
}
```

### <y>Type a parameter as an array</y>

```ts
function getSum(numbers: number[]) {
  let sum = 0;
  numbers.forEach(num => sum += num);
  return sum;
}

const numbers = [1, 2, 3, 4, 5];
const result = getSum(numbers); // Result: 15
```

### <y>Type a parameter as an object</y>

```ts
interface Person {
  name: string;
  age: number;
}

function greetPerson(person: Person) {
  console.log(`Hello, ${person.name}!`);
}

const john = { name: "John", age: 30 };
greetPerson(john); // Output: Hello, John!
```

[back to top](#table-of-contents)
## <o>TypeScript events for React</o>
  
  - [TypeScript Event Typing](https://devtrium.com/posts/react-typescript-events)

## <o>Index Signatures</o>

  * [Index Signature](https://www.typescriptlang.org/docs/handbook/2/index-signatures.html)
  * Index Signature is a way to define the type of values that can be accessed using an index in an object or class.
  * It allows you to specify the types of properties that can be accessed using an index signature.

  An index signature is defined using square brackets and the type of the index:
  
  ```ts
    interface MyObject {
  [key: string]: string;
  }
  ```

