## Understanding TypeScript Better: Two Core Concepts Explained

TypeScript helps us write safer and more maintainable JavaScript code by adding type support. In this post, we’ll explore two important TypeScript topics that are often asked in interviews and used in real projects.

---

### 1. What are some differences between **interfaces** and **types** in TypeScript?

Both **interfaces** and **type aliases** are used to describe the shape of objects, but they have some key differences:

#### Common Differences:

| Feature            | Interface                              | Type Alias                             |
|--------------------|-----------------------------------------|----------------------------------------|
| Usage              | Best for defining object shapes         | Can define objects, unions, tuples etc.|
| Extendable         | Can be extended with `extends`          | Can be combined using `&`              |
| Declaration Merging| Supports merging with same name         | Does not support merging               |

#### Example:

```ts
// Interface
interface User {
  name: string;
  age: number;
}

// Type
type Admin = {
  name: string;
  role: string;
};

// Combining types
type SuperUser = User & Admin;
```

#### When to use what?

- Use **interface** if you're only defining object shapes.
- Use **type** when working with unions, tuples, or need advanced combinations.

---

### 2. Example of **union** and **intersection** types in TypeScript

There are two main ways to combine types in TypeScript:

- **Union type (`|`)** means a value can be one of several types.

- **Intersection type (`&`)** means a value has all properties from multiple types.

#### Union Type Example:
```ts
type Status = "success" | "error" | "loading";

function showStatus(status: Status) {
  console.log("Status is:", status);
}

showStatus("success");
```

#### Intersection Type Example:
```ts
type Name = { name: string };
type Age = { age: number };

type Person = Name & Age;

const person: Person = {
  name: "Masud",
  age: 25
};
```

#### When to use what?
- Use **union types** when a value can be one of several types.
- Use **intersection types** when you want to combine multiple types into one.

---

## Conclusion

Understanding `interface` vs `type` and `union` vs `intersection` will help you write better and safer TypeScript code. These are simple but powerful tools for building clear and scalable applications.
