# Custom types

These are supported thanks to the use of Interfaces and Classes:

|| Interfaces                       || Classes                              ||
| Define a new type                 | Define a new type                     |
| Have properties (as signatures)   | Have properties (with implementation) | 
| Methods (as signatures)           | Methods (with implementation)         |
| Cannot be instantiated            | Can be instantiated                   |

The interface is a high level abstraction of what a class that implements it should have, like a blueprint.

The class has all the details required for the class to work.


## Interfaces

Defined using the interface keyword followed by the name, then in the body the properties and methods are added.

```typescript
interface Employee {
    name: string;
    title: string;
}

interface Manager extends Employee {
    department: string;
    numOfEmployees: number;
    scheduleMeeting: (topic: string) => void;
}
```


## Structural type system

The `developer` object below, even if it has additional properties, meets the requirements for the `Employee` interface.

This means that we can use the `developer` object anywhere where an employee type is required, even if not explicitly declared as `Employee` type.

This is because of the **structural type system**, since the structure matches we can treat the object as the type it matches.

This is also known as **duck typing**.

```typescript
interface Employee {
    name: string;
    title: string;
}

let developer = {
    name: "Michelle",
    title: "Senior Developer",
    editor: "VSCode"
}

let newEmployee: Employee = developer; // This is fine!
```
