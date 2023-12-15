# Parameters, Return Types, and Overloading in C#

In C#, functions can be designed with a variety of parameters, return types, and even multiple versions (overloads) to handle different scenarios. This document provides insight into these aspects of functions in C#.

## Contents

- [Function Parameters](#function-parameters)
- [Return Types](#return-types)
- [Function Overloading](#function-overloading)

### Function Parameters

Parameters allow you to pass data to functions. There are several types of parameters in C#:

1. **Value Parameters:**
   - Pass a copy of the value to the function.
   - Modifications inside the function do not affect the original value.
   - Example:
     ```csharp
     public void AddOne(int number)
     {
         number += 1;
     }
     ```

2. **Reference Parameters (`ref` keyword):**
   - Pass a reference to the value.
   - Modifications inside the function affect the original value.
   - Example:
     ```csharp
     public void AddOne(ref int number)
     {
         number += 1;
     }
     ```

3. **Output Parameters (`out` keyword):**
   - Used to return multiple values from a function.
   - Example:
     ```csharp
     public void GetValues(out int val1, out int val2)
     {
         val1 = 5;
         val2 = 10;
     }
     ```

### Return Types

The return type of a function specifies the type of value that the function is expected to return. 

- If a function does not return any value, the return type is `void`.
- Otherwise, it must return a value that matches the specified return type.
- Example:
  ```csharp
  public int Square(int number)
  {
      return number * number;
  }
  ```

### Function Overloading

Function overloading allows you to have multiple functions with the same name but different parameters (number, types, or order).

- Overloaded functions must differ in the number or type of parameters.
- The return type cannot be used to differentiate overloaded functions.
- Example:
  ```csharp
  public void Display(string message)
  {
      Console.WriteLine(message);
  }

  public void Display(int number)
  {
      Console.WriteLine(number);
  }
  ```

Understanding these concepts is key to writing flexible and efficient C# code. Proper use of parameters, return types, and overloading can greatly enhance the functionality and readability of your code.

---

Explore more about C# functions:
- [Defining and Invoking Functions](./Defining_and_Invoking_Functions.md)
- [Extension Methods](./Extension_Methods.md)

Return to [Functions Main Page](./README.md)
