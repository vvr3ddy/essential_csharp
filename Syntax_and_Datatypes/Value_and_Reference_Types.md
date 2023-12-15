# Value Types vs. Reference Types in C#

Understanding the difference between value types and reference types is crucial in C# as it affects how variables store their data and how they are passed around in your code. This document provides an overview of these two types and their implications in C# programming.

## Contents

- [What are Value Types?](#what-are-value-types)
- [What are Reference Types?](#what-are-reference-types)
- [Differences and Implications](#differences-and-implications)

### What are Value Types?

Value types are types that hold their data directly. They are stored in the stack, which makes access to these types fast. Common value types include:

- **Primitive Types:** `int`, `double`, `byte`, `bool`, etc.
- **Structs:** Custom value types defined by the user.
- **Enumerations:** Defined using the `enum` keyword.

When you assign a value type variable to another, it copies the value directly. Modifications to one variable do not affect the other.

Example:
```csharp
int x = 10;
int y = x; // Copies the value of x into y
y = 20; // Modifying y does not affect x
```

### What are Reference Types?

Reference types store a reference to their data, which is stored in the heap. This means that the variable holds a pointer to the location in memory where the actual data is stored. Common reference types include:

- **Classes:** Including `string` and other user-defined classes.
- **Arrays:** Even if they are arrays of value types.
- **Delegates:** Reference types that hold references to methods.

When you assign a reference type variable to another, it copies the reference, not the actual data. Thus, changes to one variable can affect another.

Example:
```csharp
var arr1 = new int[] { 1, 2, 3 };
var arr2 = arr1; // Copies the reference of arr1 into arr2
arr2[0] = 10; // Modifying arr2 also affects arr1
```

### Differences and Implications

- **Memory Allocation:** Value types are allocated on the stack, which can be more efficient. Reference types are allocated on the heap, which can handle larger and more complex objects.
- **Lifetime:** Value types have a short lifetime as they reside in the stack, while reference types have a longer lifetime managed by the garbage collector.
- **Performance:** Copying value types is generally faster for small types. However, for large structures, copying can be costly.
- **Nullability:** By default, value types cannot be null (unless marked as nullable), while reference types can be null.

Understanding these differences is key to writing efficient and bug-free C# code, especially when dealing with large data structures or performance-critical applications.

---

Explore more about C#:
- [Primitive and Non-Primitive Data Types](./Primitive_and_Non_Primitive_Datatypes.md)

Return to [Syntax and Datatypes Main Page](./README.md)
