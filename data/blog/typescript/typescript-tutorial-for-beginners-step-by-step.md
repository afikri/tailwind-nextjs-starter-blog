---
title: Typescript Tutorial for Beginners Step by Step
date: '2023-01-20'
tags: ['code', 'typescript', 'web-development', 'libraries']
draft: false
summary: ''
---

## 🤝 Introduction to TypeScript

In 2012, Microsoft initiated an open source programming language which is called Typescript. It is a strict syntactical superset of JavaScript, and adds optional static typing to the language. Meaning that in TypeScript, variables can have specific data types (such as number, string, or boolean) and the compiler will check for type compatibility, making it easier to catch errors before the code is run.

One of the main benefits of using TypeScript is that it can help to prevent common coding mistakes and make it easier to understand and maintain large codebases. It also includes features such as class and interface definitions, which can help to make code more organized and reusable.

TypeScript is fully compatible with existing JavaScript code and can be used in any environment that supports JavaScript. It can also be easily integrated with popular web development frameworks such as Angular and React.

To start using TypeScript, what we need to have is Node.js and the TypeScript compiler installed on the computer. Then create a new TypeScript file with the .ts file extension, and use the compiler to transpile the TypeScript code into JavaScript, which can be run in any JavaScript environment.

#### 📔 Why use it

TypeScript is designed for the development of large applications and transcompiles to JavaScript.
Using TypeScript can help improve the maintainability and scalability of the codebase by catching errors early in the development process. The added type checking can also make it easier for other developers to understand and work with the code. Additionally, many popular JavaScript libraries and frameworks, such as Angular and Vue.js, have built-in support for TypeScript.

#### Setting up a TypeScript development environment

To set up a TypeScript development environment, what we need to do the following:

- **Install Node.js** and **npm** (Node Package Manager) on the machine. This will allow us to run and manage JavaScript packages. To make sure the node and npm are installed, issued these command
`node -v` and `npm -v`
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![npm](/static/images/node-npm.PNG)
</div>

- Initialize a new Node.js project by running `npm init` in the project directory. This will create a package.json file that will keep track of the project's dependencies.
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![npm init](/static/images/step2.PNG)
</div>

- Install TypeScript by running npm install typescript. This will add TypeScript as a dependency to the project.
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![npm install](/static/images/step3.PNG)
</div>

- Create a new TypeScript configuration file by running tsc --init. This will create a tsconfig.json file in the project directory. This file can be edited to configure the TypeScript project.
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![typescript](/static/images/step4.PNG)
</div>

- Create a new .ts file and start writing TypeScript code.
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![file ts](/static/images/step5.PNG)
</div>
and use editor to create a ts code
 <div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![ts code](/static/images/step6.PNG)
</div>
- Transpile TypeScript code to JavaScript by running tsc in the terminal.
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![terminal](/static/images/step7.PNG)
</div>
- Run the generated JavaScript file by running node the-javascript-file.js
<div className="my-1 px-2 w-full overflow-hidden xl:my-1 xl:px-2 xl:w-1/2">
![javascript file](/static/images/step8.PNG)
</div>
- (Optional) we could use a code editor that support TypeScript like Visual Studio Code to get IntelliSense and other helpful features.

## Basic Types and Variables

#### Primitive data types

TypeScript, like most programming languages, has several basic data types that can be used to declare variables. These include:

- **number**: used for numeric values, both integers and floating-point values.

```js
let decimal: number = 6
let hex: number = 0xf00d
let binary: number = 0b1010
let octal: number = 0o744
```

- **string**: used for text values.

```js
let name: string = 'John Doe'
let age: number = 30
let sentence: string = `My name is ${name} and I am ${age} years old.`
```

- **boolean**: used for true/false values.

```js
let isStudent: boolean = true
let isValid: boolean = true
let isInvalid: boolean = false
let isDisabled: boolean = false
```

- **any**: used when the type of a variable is not known or when a variable can have different types at different times.

```js
let anything: any = 'hello'
console.log(anything.toUpperCase())
anything = 42
console.log(anything.toFixed(2))
```

- **void**: used for function return types when no value is returned.

```js
function warning(): void {
  console.log('This is a warning message.')
}
```

- **null** and **undefined**: used to represent values that have not been assigned or do not exist.
  To declare a variable in TypeScript, use the let or const keyword, followed by the variable name and an optional type.

```js
let u: undefined = undefined
let n: null = null
```

It's worth noting that TypeScript also has a `unknown` type which is similar to `any`, but it adds more type-safety.

#### Type annotations and type inference

In TypeScript, type annotations and type inference are used to specify the data type of a variable or a function.
Type annotations are used to explicitly specify the data type of a variable or a function. They are added after the variable or function name, preceded by a colon.

```js
let name: string = 'John Doe'
const age: number = 30
let isStudent: boolean = true
```

The above code is equivalent to the previous one, TypeScript can infer that the `name` variable is of type `string`, `age` is of type `number` and `isStudent` is of type `boolean`

It is generally considered best practice to use type inference instead of type annotations when possible because it makes the code more readable and less verbose. However, in some cases, it may be necessary to use type annotations, such as when the type cannot be inferred from the value or when the type needs to be more specific.

`let` or `const` are also used to declare variables in TypeScript, `const` are used for variables whose value should not change and `let` for variables whose value can change.

## Classes and Interfaces

In TypeScript, a class is a blueprint for creating objects (a particular data structure), providing initial values for state (member variables or properties), and implementations of behavior (member functions or methods). Classes are typically used to model real-world objects and their behavior.

An interface in TypeScript is a blueprint for an object's structure. It defines a contract for the shape of an object, specifying the properties and methods that an object should have. Interfaces are used to provide a consistent structure for related objects, and to define contracts for objects that will be used by other parts of the codebase.

A class can implement an interface, which means that it guarantees that it will have all the properties and methods defined in the interface. A class can also extend another class, inheriting its properties and methods.

Here is an example of a class and interface in TypeScript:

```js
interface Shape {
  width: number;
  height: number;
  area(): number;
}

class Rectangle implements Shape {
  width: number
  height: number
  constructor(width: number, height: number) {
    this.width = width
    this.height = height
  }
  area(): number {
    return this.width * this.height
  }
}
```

In this example, the `Rectangle` class implements the `Shape` interface, which means that it must have `width`, `height`, and `area()` properties and methods.

#### Defining classes and constructors

In TypeScript, a class is defined using the `class` keyword, followed by the name of the class. The class body is enclosed in curly braces `{}`.

A constructor is a special method that is called when an object of the class is created. It is used to initialize the object's state and perform any other setup that is required.

Here is an example of a simple class and constructor in TypeScript:

```js
class Person {
  name: string
  age: number
  constructor(name: string, age: number) {
    this.name = name
    this.age = age
  }
}
```

In this example, the `Person` class has two properties: `name` and `age`. The constructor takes two arguments, `name` and `age`, and assigns them to the corresponding properties of the object.

#### Access modifiers (public, private, protected)

There are three types of access modifiers in TypeScript: `public`, `private`, and `protected`.

- `public` is the default access modifier for properties and methods. Properties and methods marked as `public` can be accessed from anywhere in the codebase.
- `private` properties and methods can only be accessed from within the class in which they are defined. Attempting to access a private property or method from outside the class will result in a compile-time error.
- `protected` properties and methods can be accessed from within the class in which they are defined, and from any derived classes. Attempting to access a protected property or method from outside the class or its derived classes will result in a compile-time error.

Here is an example of how access modifiers can be used in a class:

```js
class Person {
  public name: string;
  private age: number;
  protected address: string;

  constructor(name: string, age: number, address: string) {
    this.name = name;
    this.age = age;
    this.address = address;
  }
  getAge(): number {
    return this.age;
  }
}

class Employee extends Person {
  public salary: number;

  constructor(name: string, age: number, address: string, salary: number) {
    super(name, age, address);
    this.salary = salary;
  }
  getAddress(): string {
    return this.address;
  }
}

let person = new Person("John", 25, "New York");
console.log(person.name); // "John"
console.log(person.getAge()); // 25
console.log(person.address); // Error: Property 'address' is protected and only accessible within class 'Person' and its subclasses.

let employee = new Employee("Jane", 30, "Los Angeles", 50000);
console.log(employee.name); // "Jane"
console.log(employee.getAge()); // Error: Property 'age' is private and only accessible within class 'Person'.
console.log(employee.getAddress()); // "Los Angeles"
```

In this example, the `Person` class has three properties: `name`, `age`, and `address`. The `name` property is public and can be accessed from anywhere, the `age` property is private and can only be accessed within the class and the `address` property is protected and can be accessed within the class and its derived classes.

## Functions and Generics

Function is a block of code that can be defined and then invoked, or called, multiple times. Functions can take zero or more arguments, and can return a value or not. Here's an example of a simple function in TypeScript:

```js
function add(a: number, b: number): number {
  return a + b
}
console.log(add(1, 2)) // 3
```

In this example, the `add` function takes two arguments of type `number`, and returns the sum of those numbers as a `number`.

Generics is a way to make a function or class work with any type, instead of a specific one. Generics is a powerful way to make code reusable and more flexible.

Here's an example of a generic function:

```js
function identity<T>(arg: T): T {
  return arg
}
console.log(identity < string > 'hello') // "hello"
console.log(identity < number > 1) // 1
```

In this example, the `identity` function is defined with a type parameter `T`. This means that it can work with any type passed to it. The type parameter `T` is used to specify the type of the argument and return value. The `<string>` and `<number>` are type argument that we passed to the function

It is also able to define generic classes, which use type parameters in a similar way to generic functions. For example:

```js
class GenericNumber<T> {
    zeroValue: T;
    add: (x: T, y: T) => T;
}
let myGenericNumber = new GenericNumber<number>();
myGenericNumber.zeroValue = 0;
myGenericNumber.add = function(x, y) { return x + y; };
```

The `GenericNumber` class is defined with a type parameter `T`. This means that it can work with any type passed to it. The type parameter `T` is used to specify the types of `zeroValue` and the arguments of `add` method.

#### Defining and calling functions

A function can be defined using the `function` keyword, followed by the function name, a set of parentheses containing the function's parameters, and a set of curly braces containing the function's code. Here's an example of a simple function in TypeScript that takes in a single parameter, `x`, and returns the square of that parameter:

```js
function square(x: number): number {
  return x * x
}
```

A function can be called by referencing its name, followed by a set of parentheses containing any necessary parameters. Here's an example of how the **square** function defined above could be called:

```js
let result = square(5)
console.log(result) // prints "25"
```

In addition to function, TypeScript also has support for the fat arrow function, which is a more concise syntax for defining functions. Here's an example of the **square** function defined using the fat arrow syntax:

```js
let square = (x: number) => x * x
```

It can be called this function in the same way as the previous example.

```js
let result = square(5)
console.log(result) // prints "25"
```

Functions can also be defined as a method inside a class and can be called using the object of the class.

```js
class Example {
  square(x: number): number {
    return x * x
  }
}
let ex = new Example()
let result = ex.square(5)
console.log(result) // prints "25"
```

#### Function types and type inference

Function types can be defined using a specific syntax, which includes the type of the parameters and the return type. Here's an example of a function type that takes in two parameters, both of type number, and returns a value of type number:

```js
let myFunc: (a: number, b: number) => number
```

This function type can be used to define a variable that can hold a reference to any function that matches the specified signature. Here's an example of how that variable could be assigned a reference to an actual function:

```js
myFunc = (a, b) => a * b
```

TypeScript also supports type inference, which means that the type of a variable can be inferred from the value it is assigned. For example, in the following code, the type of the "result" variable is inferred to be number because it is assigned the result of a call to the "square" function, which has a return type of number:

```js
let result = square(5)
```

In the case of function types, type inference also works, for example

```js
let square = (x: number) => x * x
let myFunc = square
```

Here myFunc type will be inferred as `(x: number) => number`
TypeScript is possible to explicitly define function types using a specific syntax, and also supports type inference to automatically determine the types of function variables based on their assigned values.

#### Generic types and constraints

Generic types are to define types that can work with multiple types of data. A generic type is defined using a placeholder type, represented by a capital letter, such as `T`, `U`, etc. Here's an example of a generic type that represents an array:

```js
let myArray: Array<T>
```

This type can be used to define a variable that can hold an array of any type, such as an array of numbers or an array of strings. Here's an example of how that variable could be assigned a reference to an actual array:

```js
myArray = [1, 2, 3]
```

It is also OK to use constraints to specify the types that a generic type can be used with.
For example, use the extends keyword to specify that a generic type must be a subtype of a specific class or interface.

```js
class Example {
  name: string;
}

function printName<T extends Example>(arg: T) {
    console.log(arg.name);
}

let ex = new Example();
ex.name = "John";
printName(ex);
```

In this example, the `printName` function is defined with a generic type `T` that is constrained to be a subtype of the `Example` class. This means that the `printName` function can be called with an argument of any type that is a subtype of the `Example` class, such as an instance of the `Example` class.

It is also possible to use the keyword `keyof` to constrain the type parameter to a specific property of a class or interface.

```js
function getProperty<T, K extends keyof T>(obj: T, key: K) {
    return obj[key];
}

let ex = { name: "John", age: 25};
let result = getProperty(ex, "name");
console.log(result);
```

In this example above, the function `getProperty` is defined with two generic types, `T` and `K`. The `K` type is constrained to be a subtype of `keyof T`, which means it can only be a string that is a property of T.

## Advanced Types

TypeScript supports several advanced types that provide additional functionality and flexibility when working with data types. Here are a few examples:

#### Type aliases and intersection types

Type aliases make possible to create a new name for a type that can be used in the code. This can be useful when working with complex types, or when a more meaningful name is given to a type. Here's an example of how could be used a type alias to create a new name for an intersection type:

```js
interface Animals {
  legs: number;
}

interface Person {
  name: string;
}

type AnimalsPerson = Animals & Person
type MyAnimalsPerson = AnimalsPerson
const myAnimalsPerson: MyAnimalsPerson = { legs: 4, name: 'John' }
```

In this example, the `AnimalsPerson` type is defined as an intersection of the `Animals` and `Person` interfaces. This intersection type can be used to represent an object that has properties from both interfaces.

The type alias `MyAnimalsPerson` is defined to be the same as the AnimalsPerson type. Use `MyAnimalsPerson` in the code instead of `AnimalsPerson`

Intersection types are created by using the `&` operator to combine multiple types. In this way, create a new type that includes all the properties and methods of the original types. This can be useful when working with objects that have multiple properties or methods that come from different sources.

Intersection types are also useful when a type that extends multiple types or interfaces needed to be created.

```js
interface A {
  x: number;
}
interface B {
  y: number;
}
let myObj: A & B
myObj = { x: 1, y: 2 }
```

In the above example, the type of `myObj` is an intersection of interfaces `A` and `B`, which means that it has properties `x` and `y`.

#### Enums and union types

Enums, short for enumerations, are a feature in TypeScript that make possible to create a set of named values. Enums are used to define a set of named constants, such as the days of the week, or the values of a set of flags.

Here's an example of an enum that defines a set of named values for the days of the week:

```js
enum Days {
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
}
let today: Days = Days.Sunday;
```

In the above example, the `Days` enum defines a set of named values for the days of the week, and a variable `today` is declared with a type of `Days` and is assigned the value of `Days.Sunday`.

Enums are also useful when working with the set of named values that are numerical in nature. By default, the first value of the enumeration is assigned 0, and the following values are incremented by 1. However, it can also be explicitly set the value of each enumeration member.

```js
enum Color { Red = 1, Green, Blue }
let myColor: Color = Color.Green;
console.log(myColor) // 2
```

Union types make possible to specify that a variable can have one of several types. This can be useful when working with functions that can return multiple types of data. For example, it is useed a union type to specify that a function can return either a string or a number.

```js
let myUnion: string | number
myUnion = 'hello'
myUnion = 10
```

Also use union types in conjunction with enums. For example, use a union type to specify that a variable can have one of several enum values

```js
enum Color { Red, Green, Blue }
enum Size { Small, Medium, Large }
let myProduct: Color | Size;
myProduct = Color.Green;
myProduct = Size.Small;
```

#### Mapped and indexed types

A mapped type is a way to create a new type by applying a transformation to each property of an existing type. For example, use a mapped type to create a new type that has all the properties of an existing type, but with their types modified.

An indexed type, on the other hand, is a way to access the properties of an object using a string or number index. For example, use an indexed type to access the properties of an object using a string key, or to access the elements of an array using a number index.

Both mapped and indexed types can be useful in creating more specific and expressive types for the code, and can help catch errors at compile time.

```js
type Person = { name: string; age: number }
type ReadonlyPerson = { readonly [P in keyof Person]: Person[P] }
```

Here we created a `ReadonlyPerson` by applying a `readonly` keyword to all properties in `Person`

## 💟 Decorators

#### What are decorators and how to use them

A decorator is a design pattern that make possible to add new functionality to existing classes, methods, properties, or parameters. Decorators are a way to extend the capabilities of a class or its members, without modifying their implementation.

Decorators are implemented as functions that take the target class, method, property, or parameter as an argument, and return a new version of it with the added functionality. Decorators can be applied to a class by prefixing the class with the decorator function, or to its members by prefixing them with the decorator function.
For example:

```js
function myDecorator(target: any) {
  console.log('My decorator has been called!')
}

@myDecorator
class MyClass {}
```

Here, the myDecorator function is applied as a decorator to the MyClass class.
Decorators can also be applied to properties and methods:

```js
class MyClass {
  @myDecorator
  myMethod() {}
}
```

In the above example, the myDecorator function is applied to the myMethod method of the MyClass class.
Decorators are widely used in Angular framework, they are used to add metadata to the class, methods, properties etc.

Decorators factory can be created, a function that returns a decorator function.

```js
function myDecoratorFactory(param: string) {
  return function (target: any) {
    console.log(`My decorator factory has been called with param: ${param}`)
  }
}

@myDecoratorFactory('Hello World')
class MyClass {}
```

Here, `myDecoratorFactory` is a decorator factory that takes a single parameter, and returns a decorator function that is applied to the class `MyClass`.

#### Creating custom decorators

To create a custom decorator in TypeScript, need to define a function that will act as the decorator. This function can have any name, but it is common to use the @ symbol in the name to indicate that it is a decorator.

The decorator function should take at least one argument, which is the target class, method, property, or parameter that the decorator will be applied to. Depending on the type of decorator created, it might be included additional arguments to provide additional functionality.
Here is an example of a custom decorator that logs the execution time of a method:

```js
function logExecutionTime(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  const originalMethod = descriptor.value
  descriptor.value = function (...args: any[]) {
    console.log(`Method ${propertyKey} execution started`)
    const start = performance.now()
    const result = originalMethod.apply(this, args)
    const end = performance.now()
    console.log(`Method ${propertyKey} execution finished in ${end - start} ms`)
    return result
  }
  return descriptor
}

class MyClass {
  @logExecutionTime
  myMethod() {
    // method implementation
  }
}
```

Here, the logExecutionTime function is applied as a decorator to the myMethod method of the MyClass class. When the method is called, the logExecutionTime decorator will log the start and end time of the method execution, as well as the execution time in milliseconds.

Decorator factories can also be used, a function that returns a decorator function. This make possible to pass configuration options to the decorator.

```js
function logExecutionTimeFactory(log: boolean) {
  return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
    const originalMethod = descriptor.value
    descriptor.value = function (...args: any[]) {
      if (log) console.log(`Method ${propertyKey} execution started`)
      const start = performance.now()
      const result = originalMethod.apply(this, args)
      const end = performance.now()
      if (log) console.log(`Method ${propertyKey} execution finished in ${end - start} ms`)
      return result
    }
    return descriptor
  }
}

class MyClass {
  @logExecutionTimeFactory(true)
  myMethod() {
    // method implementation
  }
}
```

In this example, `logExecutionTimeFactory` is a decorator factory that takes a single argument, `log`, which indicates whether or not to log the execution time of the method.

It's worth noting that creating custom decorators can be quite complex, and it is a good practice to test them thoroughly before using them in production.

## 📇 Namespaces and Modules

#### Organizing code with namespaces

Organizing code with namespaces in TypeScript is a way to group related variables, functions, classes, and interfaces under a single name, which can help to prevent naming collisions and make the code more maintainable.

One way to use namespaces is to create a top-level namespace that contains sub-namespaces for different areas of functionality.

For example:

```js
namespace MyApp {
  export namespace Users {
    export class User { }
    export function getUser(id: number) { }
  }

  export namespace Orders {
    export class Order { }
    export function getOrder(id: number) { }
  }
}
```

Here, `MyApp` is the top-level namespace that contains two sub-namespaces: `Users` and `Orders`. The `Users` namespace contains a `User` class and a `getUser` function, while the `Orders` namespace contains an `Order` class and a `getOrder` function.

It is also possible to create a namespace for shared utility functions and variables.

```js
namespace MyApp {
  export namespace Utils {
    export function log(message: string) { }
    export const version = "1.0.0";
  }
}
```

In this example, `MyApp.Utils` namespace contains a `log` function and a `version` variable that can be used throughout the application.

Namespaces can also be used to group related classes, interfaces, and functions together.

```js
namespace MyApp.Shapes {
  export class Circle { }
  export class Square { }
  export interface Shape { }
  export function getArea(shape: Shape) { }
}
```

In this example, `MyApp.Shapes` namespace contains `Circle`, `Square` classes, `Shape` interface, and `getArea` function all related to shapes.
It is also possible to split a namespace across multiple files and then combine them together using the `/// <reference path="..." />`

Using namespaces can make the code more organized and easier to understand. It is also possible to reuse the same names for different variables, functions, classes, and interfaces without causing conflicts.

#### Importing and exporting modules

The `export` keyword is to make variables, functions, classes, and interfaces available for other modules to import and use. To import exported members from another module, use the `import` keyword.

To export a member, place the `export` keyword before the declaration of the member.
For example:

```js
export class MyClass {}
export function myFunction() {}
export const myVariable = 'Hello'
```

Here, `MyClass`, `myFunction` and `myVariable` are exported, and can be imported by other modules.

To import an exported member from another module, use the `import` keyword followed by the name of the member. The imported members are assigned to a new variable with the same name as the member being imported.

```js
import { MyClass, myFunction, myVariable } from './myModule'
let myObject = new MyClass()
myFunction()
console.log(myVariable)
```

To import all members of a module using the `*` symbol and reference them using the name of the module.

```js
import * as myModule from './myModule'
let myObject = new myModule.MyClass()
myModule.myFunction()
console.log(myModule.myVariable)
```

Also use the `as` keyword to give an imported member a different name.

```js
import { MyClass as MyNewClass } from './myModule'
let myObject = new MyNewClass()
```

In this example, `MyClass` is imported from `myModule` and assigned to a new variable `MyNewClass`

Also use `default` keyword to export a member that will be the default export of a module.

```js
export default class MyClass {}
```

To import a default export, no need to use curly braces

```js
import MyClass from './myModule'
let myObject = new MyClass()
```

It is also possible to export and import at the same time using the `export =` and `import =` syntax. This can be useful when working with JavaScript modules that don't use the `export` and `import` keywords.

```js
// myModule.js
module.exports = {
  MyClass: MyClass,
  myFunction: myFunction,
}
```

```js
// otherModule.ts
import myModule = require("./myModule");
let myObject = new myModule.MyClass();
myModule.myFunction();
```

In summary, the `export` keyword is used to make variables, functions, classes, and interfaces available for other modules to import and use, whereas the `import` keyword is used to import those exported members from another module. The `default` keyword is used to export a member that will be the default export of a module, and `export =` and `import =` syntax can be used when working with JavaScript modules that don't use the `export` and `import` keywords.
