TypeScript is a statically-typed programming language that is a superset of JavaScript
<br>
<br>
TypeScript has several built-in types, including:
- primitive types
    - number
    - string
    - boolean
    - any
    - void
    - [null and undefined](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#null-and-undefined)
- object types
    - Enumerated types (enum)
    - Tuple types
    - Array types
    - class 
    - interface
- other types
    - any
    - [never](https://www.typescriptlang.org/docs/handbook/2/narrowing.html#the-never-type)
    - object
    - [unknown](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-0.html#new-unknown-top-type)
- non built in types
    - symbol
    - Union types (|) `typeA | typeB`
    - Intersection types (&) `typeA & typeB`
    - [Type aliases](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-aliases) (type)
    - Type assertions
    - [keyof operator](https://www.typescriptlang.org/docs/handbook/2/keyof-types.html#handbook-content) in TypeScript is used to get the union of keys from an object type
<br>

!! You can also create custom types in TypeScript using interfaces, classes, and type aliases.

1. <strong style="color:red;">Type inference</strong> in TypeScript refers to the process of automatically determining the type of a variable based on the value assigned to it. 
2. TypeScript uses structural typing to determine  <strong style="color:red;">type compatibility</strong>. This means that two types are considered compatible if they have the same structure, regardless of their names.
<br>

### Assertions 
NOTE : (used only when we do not explicitly declare the type of our variable ecept for type annotations)
- Type assertions in TypeScript are a way to tell the compiler to treat a value as a specific type, regardless of its inferred type.
- In TypeScript, the as keyword is used for type assertions, allowing you to explicitly inform the compiler about the type of a value when it cannot be inferred automatically
- `as const`,`as any`,`as [type] (type assertions)`,`! (non null assertion) - infers that the vale will not be null/undefined`
<br/>There are two syntaxes for type assertions in TypeScript:
```
The “angle-bracket” syntax: <T>value
The “as” syntax: value as T
```
#### Satisfies keyword
[read about it](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-4-9.html#the-satisfies-operator)
### Type Guards/Narrowing
a way to narrow down the type of a variable. This is useful when you want to do something different depending on the type of a variable.
- typeof
- instanceof
- to be continued...
### Interfaces

### classes
### Generics
### Decorators
### utility types 
- Partial: makes all properties of a type optional.
  - `varName:partial<someType>`
- Readonly: makes all properties of a type read-only.
  - `const todo: Readonly<Todo> = {
  title: 'Delete inactive users',
};
`
- Pick: allows you to pick specific properties from a type.
- Omit: allows you to omit specific properties from a type.
- Exclude: creates a type that is the set difference of A and B.
- Record
- Extract
- NonNullable
- Parameters
- ReturnType
- InstanceType
- Awaited
### Advanced types
these allow for more complex and expressive type systems. Some of the most commonly used advanced types in TypeScript include:

- Intersection Types
- Union Types
- Type Aliases
- Conditional Types
- Index Types
- Mapped Types
- Type Guards
### TS modules




