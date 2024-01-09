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

