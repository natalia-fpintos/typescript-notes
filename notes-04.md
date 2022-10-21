# Function types

Functions can define types for the parameters and return types.

In JavaScript, all parameters are optional in functions, however TypeScript makes all parameters mandatory.

The way around this, is to declare a parameter optional with the `?` syntax.

All optional parameters should go at the end of the function signature, after the required parameters.

```typescript
function sayNameAge(name: string, age: number, greeting?: string): string {
    if (greeting) {
        return `${greeting}! I am ${name}, my age is ${age}`;
    } else {
        return `Hello! I am ${name}, my age is ${age}`;
    }
}
```

The `--noImplicitAny` option will not allow implicitly assigning the `any` type if you forget to define types for parameters.
