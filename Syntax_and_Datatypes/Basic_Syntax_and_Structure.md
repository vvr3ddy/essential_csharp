# Basic Syntax and Structure of C# Code

C# is a statically-typed, object-oriented language known for its expressive yet straightforward syntax. This section covers the fundamental aspects of C# programming, which are essential for every C# developer.

## Contents

- [The Basic Structure of a C# Program](#the-basic-structure-of-a-c-sharp-program)
- [Understanding Namespaces and Using Directives](#understanding-namespaces-and-using-directives)
- [Data Type Declaration and Initialization](#data-type-declaration-and-initialization)
- [Control Flow Statements](#control-flow-statements)
- [Comments and Documentation](#comments-and-documentation)

### The Basic Structure of a C# Program

C# programs typically start with a `Main` method in a class within a namespace. Here's a simple structure:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
```

This example demonstrates the basic elements: `using` directives, a namespace declaration, a class definition, and the `Main` method, which is the entry point of a C# program.

### Understanding Namespaces and Using Directives

- **Namespaces:** They logically group classes and other types. For example, `System` is a namespace that includes fundamental classes and base types.
  
- **Using Directives:** These statements allow you to use types in a namespace without specifying the full namespace. For example, `using System;` enables direct use of classes in the `System` namespace.

### Data Type Declaration and Initialization

C# supports various data types. Here's how you declare and initialize them:

```csharp
int number = 5;           // Integer type
double rate = 3.14;       // Double type
bool isHappy = true;      // Boolean type
string name = "Alice";    // String type
```

### Control Flow Statements

Control flow in C# is managed using various statements:

- **If-Else Statements:**
  ```csharp
  if (number > 0) {
      Console.WriteLine("Positive");
  } else {
      Console.WriteLine("Non-positive");
  }
  ```

- **Switch Statements:**
  ```csharp
  switch (name) {
      case "Alice":
          Console.WriteLine("Name is Alice");
          break;
      default:
          Console.WriteLine("Name is not Alice");
          break;
  }
  ```

- **Loops (for, while, do-while):**
  ```csharp
  for (int i = 0; i < 5; i++) {
      Console.WriteLine(i);
  }
  ```

### Comments and Documentation

- **Single-line Comments:** Use `//` for single-line comments.
  ```csharp
  // This is a single-line comment
  ```

- **Multi-line Comments:** Use `/* */` for multi-line comments.
  ```csharp
  /*
      This is a multi-line comment
      spanning multiple lines
  */
  ```

- **XML Documentation Comments:** Use `///` for XML documentation, which can be used to generate documentation for your code.
  ```csharp
  /// <summary>
  /// This method performs an action.
  /// </summary>
  ```

---

Explore more about C#:
- [Primitive and Non-Primitive Data Types](./Primitive_and_Non_Primitive_Datatypes.md)
- [Value Types vs. Reference Types](./Value_and_Reference_Types.md)

Return to [Syntax and Datatypes Main Page](./README.md)
