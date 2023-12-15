# Task Parallel Library (TPL) in C#

The Task Parallel Library (TPL) is a powerful and flexible set of APIs in C# that makes parallel programming more accessible and manageable. It provides an efficient and scalable way to write asynchronous and parallel code. This document covers the key concepts and usage of TPL in C#.

## Contents

- [Understanding Tasks](#understanding-tasks)
- [Creating and Running Tasks](#creating-and-running-tasks)
- [Handling Task Results and Exceptions](#handling-task-results-and-exceptions)
- [Task Cancellation](#task-cancellation)
- [Parallel Class for Parallel Loops](#parallel-class-for-parallel-loops)

### Understanding Tasks

A Task in TPL represents an asynchronous operation. It is an object that encapsulates some work that should run concurrently with the rest of the application.

### Creating and Running Tasks

You can create and start a task using the `Task` class. Tasks can be run synchronously or asynchronously.

- **Starting a Task:**
  ```csharp
  Task myTask = Task.Run(() => {
      // Code to run asynchronously
      Console.WriteLine("Task running...");
  });
  ```

- **Waiting for Task Completion:**
  ```csharp
  myTask.Wait(); // Blocks the current thread until the task completes
  ```

### Handling Task Results and Exceptions

- **Returning Results from Tasks:**
  - Use `Task<TResult>` to return a result.
  - Example:
    ```csharp
    Task<int> calculationTask = Task.Run(() => {
        // Some calculations
        return 42;
    });
    int result = calculationTask.Result; // Blocks until task completes
    ```

- **Exception Handling in Tasks:**
  - Exceptions thrown in tasks are captured in an `AggregateException`.
  - Example:
    ```csharp
    try {
        myTask.Wait();
    }
    catch (AggregateException ae) {
        // Handle exceptions
    }
    ```

### Task Cancellation

Tasks can be canceled using the `CancellationTokenSource` and `CancellationToken`.

- **Example:**
  ```csharp
  CancellationTokenSource cts = new CancellationTokenSource();
  CancellationToken token = cts.Token;

  Task myTask = Task.Run(() => {
      while (!token.IsCancellationRequested) {
          // Task work here
      }
  }, token);

  // Cancel the task
  cts.Cancel();
  ```

### Parallel Class for Parallel Loops

The `Parallel` class provides parallel versions of `for` and `foreach` loops.

- **Parallel For Loop:**
  ```csharp
  Parallel.For(0, 10, i => {
      Console.WriteLine($"Parallel loop iteration {i}.");
  });
  ```

- **Parallel Foreach Loop:**
  ```csharp
  var items = Enumerable.Range(0, 10);
  Parallel.ForEach(items, item => {
      Console.WriteLine($"Processing item {item}");
  });
  ```

---

The TPL simplifies complex parallel and asynchronous programming models, making it easier to write efficient, scalable, and robust C# applications.

Explore more about C# multithreading:
- [Basics of Threading and Thread Class](./Basics_of_Threading_and_Thread_Class.md)
- [Synchronization and Thread Safety](./Synchronization_and_Thread_Safety.md)

Return to [Multithreading Main Page](./README.md)
