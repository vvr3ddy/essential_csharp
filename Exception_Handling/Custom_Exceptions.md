# Custom Exceptions in C#

While C# provides a wide range of built-in exception types, there are scenarios where creating custom exceptions can provide more clarity and control in error handling. Custom exceptions allow for more specific error descriptions and can include additional information pertinent to the error.

## Contents

- [Creating Custom Exceptions](#creating-custom-exceptions)
- [Best Practices for Custom Exceptions](#best-practices-for-custom-exceptions)
- [Using Custom Exceptions](#using-custom-exceptions)

### Creating Custom Exceptions

To create a custom exception, you typically inherit from the `Exception` class or one of its subclasses.

- **Basic Structure:**
  ```csharp
  public class MyCustomException : Exception
  {
      public MyCustomException() { }

      public MyCustomException(string message)
          : base(message) { }

      public MyCustomException(string message, Exception inner)
          : base(message, inner) { }

      // Add any additional custom properties or methods here
  }
  ```

- **Adding Custom Properties:**
  Custom properties can provide additional information about the exception.
  ```csharp
  public class MyCustomException : Exception
  {
      public int ErrorCode { get; }

      public MyCustomException(string message, int errorCode)
          : base(message)
      {
          ErrorCode = errorCode;
      }
  }
  ```

### Best Practices for Custom Exceptions

- **Inheritance:** Always inherit from the `Exception` class or one of its derived classes.
- **Meaningful Names:** Name your custom exceptions clearly to indicate their specific purpose.
- **Constructor Overloads:** Provide various constructors to mimic the `Exception` class's flexibility.
- **Serialization:** If your exceptions need to be serialized (e.g., for remoting), make them serializable.

### Using Custom Exceptions

You use a custom exception in the same way you would use a built-in exception type. 

- **Throwing a Custom Exception:**
  ```csharp
  public void MyMethod(int param)
  {
      if (param < 0)
      {
          throw new MyCustomException("Parameter must be non-negative", 1001);
      }

      // Method implementation
  }
  ```

- **Catching a Custom Exception:**
  ```csharp
  try
  {
      MyMethod(-1);
  }
  catch (MyCustomException ex)
  {
      Console.WriteLine($"Error: {ex.Message}, Code: {ex.ErrorCode}");
  }
  ```

---

Custom exceptions are a powerful tool for creating more readable and maintainable error-handling code in C#. By providing specific, tailored information about errors, they can make your code's logic clearer and more robust.

Explore more about C# exception handling:
- [Try-Catch Blocks](./Try_Catch_Blocks.md)
- [Best Practices for Exception Handling](./Exception_Handling_Best_Practices.md)

Return to [Exception Handling Main Page](./README.md)
