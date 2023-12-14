# Primitive and Non-Primitive Data Types in C#

In C#, data types are broadly categorized into two types: primitive and non-primitive. This document aims to provide a clear understanding of these data types, which are fundamental in C# programming.

## Contents

- [Primitive Data Types](#primitive-data-types)
- [Non-Primitive Data Types](#non-primitive-data-types)

### Primitive Data Types

Primitive data types are basic types built into the language. They are also known as simple types and can be categorized as follows:

1. **Integral Types:**
   - `int`, `long`, `short`, `byte`, `sbyte`, `uint`, `ulong`, `ushort`: These types are used for representing whole numbers.
   - Example:
     ```csharp
     int age = 25;
     byte grade = 100;
     ```

2. **Floating-Point Types:**
   - `float`, `double`: Used for representing real numbers.
   - Example:
     ```csharp
     double interestRate = 0.3;
     float temperature = 25.4F;
     ```

3. **Boolean Type:**
   - `bool`: Represents a true or false value.
   - Example:
     ```csharp
     bool isCompleted = true;
     ```

4. **Character Type:**
   - `char`: Represents a single Unicode character.
   - Example:
     ```csharp
     char gradeLetter = 'A';
     ```

### Non-Primitive Data Types

Non-primitive types are more sophisticated data types in C#. They include:

1. **String:**
   - Represents a sequence of characters.
   - Example:
     ```csharp
     string name = "Alice";
     ```

2. **Object:**
   - The base type of all other types. An object can store any kind of data.
   - Example:
     ```csharp
     object obj = new { Name = "Bob", Age = 30 };
     ```

3. **Dynamic:**
   - The data type of the `dynamic` type is resolved at runtime.
   - Example:
     ```csharp
     dynamic dynamicData = "Hello, World!";
     dynamicData = 100;
     ```

4. **Composite Types:**
   - Include arrays, enums, structs, and classes.
   - Example:
     ```csharp
     int[] numbers = { 1, 2, 3, 4, 5 };
     ```

Understanding these data types is crucial for any C# developer, as they form the building blocks of more complex data structures and algorithms.

---

Explore more about C#:
- [Value Types vs. Reference Types](../Value_Types_vs_Reference_Types/README.md)

Return to [Syntax and Datatypes Main Page](./README.md)
