# Built-in types

- Boolean
- Number
- String
- Array
- Enum

Also, the following additional built-in types are available:

- Void: for absence of a type (return value when a function does not return a value)
- Null: for `null` value only
- Undefined: for `undefined` value only
- Never: for values that will never occur (return value when a function never returns - infinite loop or exception)
- Any: opt-out of type checking


## Assigning types

Types can be assigned to a variable by using type annotations or by type inference:

```typescript
let aString = "Hello";                  // This uses type inference (string)
let anotherString : string = "Hello";   // This uses a type annotation
```

It's more friendly and useful to use type annotations to be explicit about types.
For example, it can be difficult to guess the type if a variable is assigned the return value of a function.


## Union types

We can assign more than one value using the pipe syntax:

```typescript
let stringOrNumber: string | number = "hello";
stringOrNumber = 42;
```


## Managing undefined and null types

When a variable is assigned a specific type, it will also allow `undefined` and `null` to be assigned as values.

```typescript
let name: string = "Audrey";
name = undefined; // This is valid
```

To prevent this, there is a compiler option called `--strictNullChecks`.

If we really want undefined or null to be valid values we must add them to a union.

```typescript
let aString: string = "hello";
aString = undefined;            // This is invalid

let aNullableString: string | null = "hello";
aNullableString = null;                         // This is valid
aNullableString = undefined;                    // This is invalid

let nullableOrUndefinedString: string | null | undefined = "hello";
nullableOrUndefinedString = null;                                   // This is valid
nullableOrUndefinedString = undefined;                              // This is valid
```


## Type assertions

When you may know better than the compiler what is the type of a variable, it's possible to assert the type.

This may happen when you are importing code or when variables are of type any.

This is achieved with by using the following syntax:

```typescript
let aNumber: any = 5;
let aString: any = "hi";

let five = <number> aNumber;
let hi = aString as string;
```


## Control flow-based type analysis

TypeScript uses flow-based type analysis to determine what is the type of a variable through the code based on the code logic.

It assigns the most specific type possible based on this.

```typescript
let stringOrNumber: number | string | undefined;

if (typeof stringOrNumber === 'string') {
    console.log(stringOrNumber)             // if we hover over the variable here, the compiler will say type is string
} else if (typeof stringOrNumber === 'number') {
    console.log(stringOrNumber)             // here, the compiler will say type is number
}

console.log(stringOrNumber);                // here, the compiler will say type is number or string or undefined
```