# Conditionals, Looping Constructs in C#

Control flow in C# is managed using conditional statements and loops. This section provides an overview of these essential constructs, including if-else statements, switch-case, and different types of loops.

## Contents

- [If-Else Statements](#if-else-statements)
- [Switch-Case](#switch-case)
- [Loops](#loops)
  - [For Loop](#for-loop)
  - [Foreach Loop](#foreach-loop)
  - [While Loop](#while-loop)
  - [Do-While Loop](#do-while-loop)

### If-Else Statements

If-else statements are used to execute different blocks of code based on a condition.

```csharp
int number = 10;
if (number > 0) {
    Console.WriteLine("Number is positive.");
} else if (number < 0) {
    Console.WriteLine("Number is negative.");
} else {
    Console.WriteLine("Number is zero.");
}
```

### Switch-Case

Switch-case is used for multiple conditional branches based on the value of a variable.

```csharp
int day = 4;
switch (day) {
    case 1:
        Console.WriteLine("Monday");
        break;
    case 2:
        Console.WriteLine("Tuesday");
        break;
    // ... other cases ...
    default:
        Console.WriteLine("Invalid day");
        break;
}
```

### Loops

Loops are used for repeating a block of code multiple times.

#### For Loop

For loops are used when you know in advance how many times you want to execute a statement or a block of statements.

```csharp
for (int i = 0; i < 5; i++) {
    Console.WriteLine(i);
}
```

#### Foreach Loop

Foreach loops are used to iterate over the elements of a collection (like an array or a list).

```csharp
string[] names = { "Alice", "Bob", "Charlie" };
foreach (string name in names) {
    Console.WriteLine(name);
}
```

#### While Loop

While loops are used when you want a loop to execute as long as a specified condition is true.

```csharp
int i = 0;
while (i < 5) {
    Console.WriteLine(i);
    i++;
}
```

#### Do-While Loop

Do-while loops are similar to while loops, but the loop will always run at least once.

```csharp
int i = 0;
do {
    Console.WriteLine(i);
    i++;
} while (i < 5);
```

Understanding these control flow constructs is essential for creating effective and efficient C# programs.

---

Explore more about C#:
- [Basic Syntax and Structure of C# Code](../Basic_Syntax_and_Structure/README.md)

Return to [Main Page](../README.md)
