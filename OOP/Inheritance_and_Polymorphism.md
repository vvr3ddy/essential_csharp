# Inheritance and Polymorphism in C#

Inheritance and polymorphism are crucial concepts in C# Object-Oriented Programming. They allow for creating hierarchical class structures and flexible interfaces. Here, we provide code snippets to illustrate these concepts.

## Contents

- [Types of Inheritance in C#](#types-of-inheritance-in-c)
- [Polymorphism: Dynamic and Static](#polymorphism-dynamic-and-static)

### Types of Inheritance in C#

C# supports various forms of inheritance, each offering a different way to establish relationships between classes.

1. **Single Inheritance:**
   - A class inherits from one base class.
   - Example:
     ```csharp
     public class Vehicle {
         public void StartEngine() { /* ... */ }
     }

     public class Car : Vehicle {
         public void HonkHorn() { /* ... */ }
     }
     ```

2. **Multilevel Inheritance:**
   - Involves a hierarchy of classes inheriting from each other.
   - Example:
     ```csharp
     public class ElectricCar : Car {
         public int BatteryLevel { get; set; }
     }
     ```

3. **Hierarchical Inheritance:**
   - Multiple classes inherit from a single base class.
   - Example:
     ```csharp
     public class Motorcycle : Vehicle {
         public void RevEngine() { /* ... */ }
     }
     ```

### Polymorphism: Dynamic and Static

Polymorphism in C# can be classified into dynamic and static polymorphism.

1. **Dynamic (Runtime) Polymorphism:**
   - Achieved through method overriding.
   - Example:
     ```csharp
     public class Vehicle {
         public virtual void StartEngine() {
             Console.WriteLine("Starting engine of Vehicle.");
         }
     }

     public class Car : Vehicle {
         public override void StartEngine() {
             Console.WriteLine("Starting engine of Car.");
         }
     }

     Vehicle myVehicle = new Car();
     myVehicle.StartEngine(); // Outputs: Starting engine of Car.
     ```

2. **Static (Compile Time) Polymorphism:**
   - Achieved through method overloading.
   - Example:
     ```csharp
     public class Calculator {
         public int Add(int a, int b) {
             return a + b;
         }

         public int Add(int a, int b, int c) {
             return a + b + c;
         }
     }
     ```

Understanding these OOP concepts with code examples can provide a clearer picture of how they are applied in C# to create flexible and maintainable software designs.

---

Explore more about C# OOP:
- [Encapsulation and Abstraction](./Encapsulation_and_Abstraction.md)
- [Interfaces and Abstract Classes](./Interfaces_and_Abstract_Classes.md)

Return to [OOP Main Page](./README.md)
