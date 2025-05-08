# NextLevelAssignment_1


# Understanding TypeScript: Key Differences Between Interfaces and Types, and How to Use Union and Intersection Types

Today In this blog post, we will explore the differences between interfaces and types in TypeScript, and also will take a good look at how union and intersection types can help us create more flexible and amazing code.

---

## 1. Interfaces vs. Types

At First let’s discuss about difference between interfaces and types. Both interfaces and types can define object structures, but there are some key differences.

### 🔄 Declaration Merging

Interfaces support declaration merging, meaning we can declare the same interface many times, and TypeScript will merge them. But In Types we can not do that support merging and It will give an error if defined more than once.

#### Example: Interface Merging

```ts
interface Car {
  brand: string;
}

interface Car {
  model: string;
}

const myCar: Car = { brand: "Toyota", model: "Corolla" };
```

---

### 🧩 Way of Extending

- **Interfaces** use `extends`.
- **Types** use the intersection operator `&`.

#### Example of Extending:

```ts
// Using type
type Vehicle = { wheels: number };
type Car = Vehicle & { brand: string };

// Using interface
interface Vehicle {
  wheels: number;
}

interface Car extends Vehicle {
  brand: string;
  model: string;
}
```

---

### 🎯 Use Case

Use interfaces when dealing with objects or class contracts. Use types when dealing with more complex structures like unions, intersections, or primitives.


Now let’s explore Union and Intersection Types in TypeScript. 

TypeScript allows us to combine types in powerful ways:


## 2. Union and Intersection Types

### ➕ Union Types

A union type allows a variable to accept values of multiple types. This is useful when a variable can have different types depending on the situation. We use the pipe (|) to define a type.

#### Example of Union Type:

```ts
type Status = "active" | "inactive";

function display(status: Status) {
  console.log(status);
}
```

---

### 🔗 Intersection Types

An intersection type allows us to combine multiple types into a single type. This is helpful when we want an object or value to satisfy multiple type definitions at the same time.We use the ampersand (&) to combine multiple types into one.

#### Example of Intersection Type:

```ts
type Animal = { name: string };
type Pet = { age: number };
type Dog = Animal & Pet & { breed: string };

const myDog: Dog = { name: "Buddy", age: 3, breed: "Golden Retriever" };
```

---

These types help us create more robust, scalable, and type-safe code structures in TypeScript.
