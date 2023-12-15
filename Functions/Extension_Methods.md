# Extension Methods in C#

Extension methods in C# provide a way to add new methods to existing types without altering the type's original source code or creating a new derived type. This document explores how to create and use extension methods in C#.

## Contents

- [Creating Extension Methods](#creating-extension-methods)
- [Using Extension Methods](#using-extension-methods)
- [Best Practices and Rules](#best-practices-and-rules)

### Creating Extension Methods

To create an extension method:

1. **Define a Static Class:** Extension methods must be defined in a static class.
2. **Create a Static Method:** The method must be static and the first parameter specifies the type the method extends, prefixed with the `this` modifier.
3. **Example:**
   ```csharp
   public static class StringExtensions
   {
       public static int WordCount(this string str)
       {
           return str.Split(new char[] { ' ', '.', '?' }, 
                            StringSplitOptions.RemoveEmptyEntries).Length;
       }
   }
   ```

### Using Extension Methods

Once defined, extension methods can be called as if they were instance methods on the extended type.

- **Example Usage:**
  ```csharp
  string phrase = "Hello, World!";
  int wordCount = phrase.WordCount(); // Use the extension method
  Console.WriteLine($"Word Count: {wordCount}");
  ```

### Best Practices and Rules

- **Namespace Consideration:** The namespace where the extension method is defined should be included in the file where it's used, or the method won't be available.
- **Avoid Conflicts:** If an extension method has the same signature as a method in the type it extends, the type's method is always called.
- **Clarity and Readability:** Use extension methods to enhance readability and maintainability of your code. They are particularly useful for adding methods to types you don't own (like .NET framework classes) or types you cannot modify.
- **Logical Grouping:** Group related extension methods within the same static class and namespace.

Extension methods are a powerful feature in C#. They enable you to write cleaner and more maintainable code by extending existing types with custom functionality.

---

Explore more about C# functions:
- [Defining and Invoking Functions](./Defining_and_Invoking_Functions.md)
- [Parameters, Return Types, and Overloading](./Parameters_Return_Types_Overloading.md)

Return to [Functions Main Page](./README.md)
