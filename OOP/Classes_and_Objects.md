# Classes and Objects in C#

Classes and objects are core concepts of object-oriented programming in C#. A class acts as a blueprint for objects, while objects are instances of classes. This document explores how to define classes and create objects in C#.

## Contents

- [Defining a Class](#defining-a-class)
- [Creating an Object](#creating-an-object)
- [Class Constructors](#class-constructors)
- [Properties and Methods](#properties-and-methods)

### Defining a Class

A class is defined with the `class` keyword, followed by the class name and a code block containing its members.

```csharp
public class Car
{
    // Fields, properties, methods, and events go here.
    public string Make;
    public string Model;
    public int Year;
}
```

In this example, `Car` is a simple class with three fields: `Make`, `Model`, and `Year`.

### Creating an Object

An object is an instance of a class. You create an object by using the `new` keyword followed by the class name and parentheses.

```csharp
Car myCar = new Car();
```

This line creates a new `Car` object named `myCar`.

### Class Constructors

A constructor is a special method in a class that is called when a new instance of the class is created. Constructors have the same name as the class and may have parameters.

```csharp
public class Car
{
    public Car(string make, string model, int year)
    {
        Make = make;
        Model = model;
        Year = year;
    }
}

Car myCar = new Car("Toyota", "Corolla", 2021);
```

This constructor allows for initializing a `Car` object with specific values at creation.

### Properties and Methods

Properties and methods are members of a class.

- **Properties:** Properties provide a mechanism to read, write, or compute private fields.
  
  ```csharp
  private int speed;

  public int Speed
  {
      get { return speed; }
      set { speed = value; }
  }
  ```

- **Methods:** Methods define actions that a class can perform.
  
  ```csharp
  public void Accelerate(int increase)
  {
      speed += increase;
  }
  ```

Understanding classes and objects is fundamental in C#. They enable you to model real-world entities in your programs, making your code more modular, flexible, and intuitive.

---

Explore more about C# OOP:
- [Inheritance and Polymorphism](./Inheritance_and_Polymorphism.md)
- [Encapsulation and Abstraction](./Encapsulation_and_Abstraction.md)

Return to [OOP Main Page](./README.md)
