# typescript-types-heritages

### Differences between Types and Interfaces:

Interfaces:

    Extending: Interfaces in TypeScript can be extended using the extends keyword. This allows you to create new interfaces that inherit properties and methods from existing ones.

    Declaration Merging: When you declare multiple interfaces with the same name, TypeScript automatically merges them together. This is useful when you need to spread an interface's definition across multiple parts of your codebase.

    Implementing Classes: Interfaces can be used to define contracts that classes must adhere to. A class can explicitly implement an interface using the implements keyword.

    Declaration Only: Interfaces can declare both methods and properties, but they cannot define actual implementations. They define the shape of an object but don't contain any executable code.

    Compatibility: Interfaces are more open to structural compatibility. This means that if an object has all the required properties of an interface, it's considered compatible with that interface, even if it has additional properties.

Types:

    Union and Intersection Types: TypeScript's type system allows you to create union types (A | B) and intersection types (A & B), which are not directly achievable with interfaces.

    Mapped Types: TypeScript introduces mapped types, which are used to transform and create new types based on existing ones. An example is the Partial<T> mapped type, which makes all properties of T optional.

    Type Aliases: With type aliases, you can give a name to a complex type, making your code more readable and understandable. This is especially useful when dealing with long and complex type definitions.

    Computed Properties: Types can be used to create computed property names using template literal types. This can be helpful when you need to generate types based on dynamic keys.

    Literal Types: TypeScript's literal types allow you to narrow down the possible values of a variable. For example, you can have a type that only accepts the values 'foo' or 'bar'.

    Mapped Tuple Types: Types can be used to create mapped tuple types, which allow you to transform each element of a tuple type into a new type.

### In our Code:

```typescript
interface Vehicle {
  maxSpeed: number
  brand: string
}

interface Car extends Vehicle {
  horsePower: number
}

interface Boat extends Vehicle {
  sails: number
}

type Tractor = {
  horsePower: number
} & Vehicle

type Moped = {
  kickstand: string
} & Vehicle
```

In our code, both types and interfaces are being used to extend vehicle to the interface. When typing "moped." in VSCode, typescript knows to show and target kickstand, brand, and maxSpeed, because these are parts of the interface that is being tacked on to Moped via the "&".
