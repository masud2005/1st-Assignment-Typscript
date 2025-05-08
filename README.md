## Understanding TypeScript Better: Two Core Concepts Explained

TypeScript is a superset of JavaScript that adds types to make our code safer and easier to manage. It helps catch errors during development and makes code more predictable and readable.

In this blog post, we’ll explore two important topics that are often discussed in interviews and commonly used in real-world projects:

1. The difference between interfaces and types
2. How to use union and intersection types

Let’s understand each one step by step, in a very simple way.
---

### 1. What are some differences between **interfaces** and **types** in TypeScript?

In TypeScript, both `interface` and `type alias` help us describe the shape of objects. That means we can use them to define what properties an object should have. However, they are slightly different in how they work.

#### Common Differences:

| Feature            | Interface                              | Type Alias                             |
|--------------------|-----------------------------------------|----------------------------------------|
| Usage              | Best for defining object shapes         | Objects, unions, tuples, primitives, etc.|
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

- Use **interface** when you only need to define the structure of an object.
- Use **type** when you need more power—like creating union types, tuples, or working with primitives.

So, if you’re building something like a user profile or an API response, interfaces are a great choice. If you're combining multiple types or doing advanced type operations, type aliases give you more flexibility.

---

### 2. Example of **union** and **intersection** types in TypeScript

TypeScript gives us two powerful ways to combine multiple types:

- **Union type (`|`)** means a value can be one of several types.

- **Intersection type (`&`)** means a value has all properties from multiple types.

Let’s break this down with examples.

#### Union Type Example:
```ts
type Status = "success" | "error" | "loading";

function showStatus(status: Status) {
  console.log("Status is:", status);
}

showStatus("success"); // Output: Status is: success
```

In this example, the function only accepts one of the three string values: "success", "error", or "loading". This is a union type—it can be any of the defined values.

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

Here, we created a new type called **Person** that combines **Name** and **Age**. The object **person** must have both **name** and **age**. This is an intersection type—it must satisfy both.

#### When to use what?
- Use **union types** when a value can be one of several types.
- Use **intersection types** when you want to combine multiple types into one.

---

## Conclusion

Understanding `interface` vs `type` and `union` vs `intersection` will help you write better and safer TypeScript code. These are simple but powerful tools for building clear and scalable applications.
