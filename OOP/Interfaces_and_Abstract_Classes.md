# Interfaces and Abstract Classes in C#

In C# Object-Oriented Programming, interfaces and abstract classes are crucial for designing flexible and maintainable code structures. They allow you to define contracts that classes can implement or inherit from, promoting a more abstract and less tightly coupled code base.

## Contents

- [Interfaces](#interfaces)
- [Abstract Classes](#abstract-classes)
- [Differences and Use Cases](#differences-and-use-cases)

### Interfaces

An interface in C# is a contract that can be implemented by classes and structs. Interfaces contain definitions for a group of related functionalities that a class or a struct can implement.

#### Implementing Interfaces

- Interfaces contain only the declaration of methods, properties, events, or indexers.
- A class or struct that implements the interface must implement all its members.
- Example:
  ```csharp
  public interface IShape
  {
      void Draw();
      double Area();
  }

  public class Circle : IShape
  {
      private double radius;

      public Circle(double radius)
      {
          this.radius = radius;
      }

      public void Draw()
      {
          Console.WriteLine("Drawing Circle");
      }

      public double Area()
      {
          return Math.PI * radius * radius;
      }
  }
  ```

In this example, `Circle` implements the `IShape` interface, thereby inheriting its contract to implement the `Draw` and `Area` methods.

### Abstract Classes

Abstract classes serve as a base class for other classes. They can include abstract members as well as fully implemented methods.

#### Using Abstract Classes

- Abstract classes cannot be instantiated.
- They can contain definitions for methods, properties, fields, and events.
- Abstract members in an abstract class must be implemented by derived classes.
- Example:
  ```csharp
  public abstract class Vehicle
  {
      public abstract void StartEngine();

      public void StopEngine()
      {
          Console.WriteLine("Engine stopped.");
      }
  }

  public class Car : Vehicle
  {
      public override void StartEngine()
      {
          Console.WriteLine("Car engine started.");
      }
  }
  ```

In this example, `Car` inherits from the `Vehicle` abstract class and provides an implementation for the `StartEngine` abstract method.

### Differences and Use Cases

- **Interfaces:**
  - Cannot provide any method implementations.
  - Useful for defining a common contract for unrelated classes.
  - Multiple interfaces can be implemented by a single class.

- **Abstract Classes:**
  - Can provide some method implementation.
  - Useful when creating a base class that defines a common blueprint for derived classes.
  - A class can inherit from only one abstract class.

Understanding when to use interfaces versus abstract classes is key to designing your C# applications. Interfaces offer more flexibility, whereas abstract classes allow you to define some common behaviors that can be shared across derived classes.

---

Explore more about C# OOP:
- [Encapsulation and Abstraction](./Encapsulation_and_Abstraction.md)
- [Inheritance and Polymorphism](./Inheritance_and_Polymorphism.md)

Return to [OOP Main Page](./README.md)
