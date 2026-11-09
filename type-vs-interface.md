## Type Aliases vs. Interfaces in TypeScript

TypeScript provides the option of both "type" and "interface" to describe the shape of the data. While they can be interchangeable at times, they have their own ruleset and use cases. 

Interface supports declaration merging and describes structures similar to objects. TypeScript will combine any interface that is declared more than once.

For example, 

```typescript
interface User {
  name: string;
}

interface User {
  email: string;
}
```
This will merge both the declarations, hence, when the interface "User" is called, it will require both "name" and "email". 

On the other hand, type alias gives a name to most types including primitives, unions, and tuples.

```typescript
type Point = [x: number, y: number];
type ID = string | number;

type Admin = {
  name: string;
  permissions: string[];
};
```
Interfaces cannot directly represent primitive union such as the one shown above, however, type aliases can. Both constructs can describe shape of objects and can also be extended through different ways. For example, interfaces use extends, while type aliases can combine types using intersections.

Interface should be used for public object contracts, class implementation requirements, and declarations intended for extension or merging. Type aliases should be chosen for unions, tuples, and conditional types. While for a simple object shape, both are valid.

In conclusion, both are useful for defining types and the choice depends on the structure and design of the project.