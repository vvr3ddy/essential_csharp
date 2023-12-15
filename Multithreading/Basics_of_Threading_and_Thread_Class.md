# Basics of Threading and Thread Class in C#

Threading in C# enables you to perform concurrent operations, making your applications more efficient and responsive. The `Thread` class in the `System.Threading` namespace is a fundamental part of this. This document covers the basics of threading and how to use the `Thread` class in C#.

## Contents

- [What is a Thread?](#what-is-a-thread)
- [Using the Thread Class](#using-the-thread-class)
- [Thread Lifecycle and States](#thread-lifecycle-and-states)
- [Thread Priorities](#thread-priorities)

### What is a Thread?

A thread is the smallest sequence of programmed instructions that can be managed independently by a scheduler. In the context of C#, a thread is an entity within a process that can be scheduled for execution.

### Using the Thread Class

The `Thread` class is used to create and control a thread. Here's a basic example of creating and starting a thread:

```csharp
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        Thread thread = new Thread(new ThreadStart(WriteY)); // Creating the Thread
        thread.Start(); // Starting the Thread

        for (int i = 0; i < 1000; i++) Console.Write("x");
    }

    static void WriteY()
    {
        for (int i = 0; i < 1000; i++) Console.Write("y");
    }
}
```

In this example, the `WriteY` method runs on a separate thread.

### Thread Lifecycle and States

A thread in C# goes through various states:

- **Unstarted State:** After a thread is created but before `Start` is called.
- **Ready State:** Ready to run and waiting for CPU time.
- **Running State:** The thread is currently running.
- **Wait/Sleep/Join State:** The thread is not active because it’s waiting for some condition to occur or complete.
- **Dead State:** The thread has completed execution or has been aborted.

### Thread Priorities

Thread priority can be set, which influences the order in which threads are scheduled. However, it's important to use this feature judiciously to avoid issues like thread starvation.

```csharp
thread.Priority = ThreadPriority.Highest;
```

---

Understanding threads and how to manage them is essential for developing sophisticated applications in C#. This introduction to the `Thread` class lays the foundation for further exploration into more advanced threading concepts.

Explore more about C# multithreading:
- [Task Parallel Library (TPL)](./Task_Parallel_Library_TPL.md)
- [Synchronization and Thread Safety](./Synchronization_and_Thread_Safety.md)

Return to [Multithreading Main Page](./README.md)
