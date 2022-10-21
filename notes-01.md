# 1. The big picture

- Typescript is a strongly-typed programming language that provides better tooling for JavaScript. It was created to overcome some of the challenges of working with JavaScript.

- When you write TypeScript source code, it compiles (aka transpile/transcompile) to JavaScript source code. The compiled code is readable and standardised, not a minified version.

- Using TypeScript doesn't affect how we run the application, it's something that helps the developer by providing features:

    1. Static Types
    2. Classes, namespaces, modules and interfaces
    3. Tooling: static type analysis, detect unreachable code, debugging...

- The TypeScript code is compiled by the tsc (typescript compiler), which generates the compiled JavaScript files.

- You can specify how the code is compiled, by passing flags or creating a `tsconfig.json` file. This file can be created with the `tsc --init` command.


## Types

- When you create a variable in TypeScript, the type is inferred from the type of the value that is assigned to the variable.

```typescript
let animal = "Dog"; // type inference

animal = 2; // This will cause an error since animal is now of type string
```

- We can also assign an explicit type next to the variable to define a type. If the value is not assigned and type is not provided, the variable will be of type `any`.

```typescript
let something; // type "any"
let age: number; // type "number"
```

- When declaring a function, the types of the arguments and return type can also be defined as follows:

```typescript
function animalDetails(animal: string, age: number): string {
    return `Animal type: ${animal}. Age: ${age}`;
}
```

- Since types can be inferred, if the function return type is not specified, TypeScript will determine the type based on what is being returned. Also, any variables that are assigned the value returned by the function will have an inferred type based on the return type of the function.

```typescript
function animalDetails(animal: string, age: number) {
    return `Animal type: ${animal}. Age: ${age}`;
}

let details = animalDetails(animal, age); // details has type string.
```


## Classes

- With TypeScript you can create classes with access modifiers: public, protected and private.

```typescript
class User {
    name: string;
    age: number;
    isActive: boolean;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
        this.isActive = true; // if we don't set all properties the constructor will error
    }

    private userDetails() {
        return `${this.name} (age ${this.age})`;
    }
}
```

## Modules

- You can define what kind of module you want to use in the tsconfig file. Then use the export/import keywords to use the modules.
