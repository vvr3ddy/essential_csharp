# Encapsulation and Abstraction in C#

Encapsulation and abstraction are fundamental principles of Object-Oriented Programming in C#. Encapsulation involves bundling data and methods operating on the data within one unit, while abstraction involves hiding complex implementation details and exposing only necessary functionalities.

## Contents

- [Encapsulation](#encapsulation)
- [Abstraction](#abstraction)

### Encapsulation

Encapsulation is about keeping the internal state of an object private and exposing only what is necessary. This is achieved using access modifiers.

#### Implementing Encapsulation

- **Private Fields:** Fields are usually declared as private to restrict direct access from outside the class.
- **Public Properties:** Public properties provide controlled access to the private fields.
- **Example:**
  ```csharp
  public class BankAccount
  {
      private double balance; // Private field

      public double Balance // Public property
      {
          get { return balance; }
          private set { balance = value; }
      }

      public void Deposit(double amount)
      {
          if (amount > 0)
          {
              Balance += amount;
          }
      }
  }
  ```

In this example, the `balance` field is encapsulated within the `BankAccount` class. External access to `balance` is controlled through the `Balance` property and the `Deposit` method.

### Abstraction

Abstraction is the concept of hiding complex reality while exposing only the necessary parts. It is closely related to encapsulation.

#### Implementing Abstraction

- **Abstract Classes and Methods:** Used to define a base class with abstract methods that must be implemented by derived classes.
- **Interfaces:** Define a contract that implementing classes must follow.
- **Example:**
  ```csharp
  public interface IDriveable
  {
      void Drive();
  }

  public class Car : IDriveable
  {
      public void Drive()
      {
          // Implementation of driving a car
      }
  }
  ```

In this example, `IDriveable` is an interface that abstracts the concept of driving. The `Car` class provides a specific implementation of the `Drive` method.

---

Encapsulation and abstraction work together to create robust and maintainable code. Encapsulation protects the internal state of objects, while abstraction reduces complexity by hiding implementation details.

Explore more about C# OOP:
- [Inheritance and Polymorphism](./Inheritance_and_Polymorphism.md)
- [Interfaces and Abstract Classes](./Interfaces_and_Abstract_Classes.md)

Return to [OOP Main Page](./README.md)
