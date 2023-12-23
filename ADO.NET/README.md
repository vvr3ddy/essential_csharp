# ADO.NET in C#

ADO.NET (ActiveX Data Objects for .NET) is a set of classes in the .NET framework that provides access to relational databases and various data sources. It is a key component for database-driven application development in C#. This section covers the fundamentals of ADO.NET, including connection handling, command execution, data retrieval, and transaction management.

## Contents

- [Understanding ADO.NET Components](./Understanding_ADO_NET_Components.md)
- [Establishing Database Connections](./Establishing_Database_Connections.md)
- [Executing Commands](./Executing_Commands.md)
- [Data Retrieval and DataSets](./Data_Retrieval_and_DataSets.md)
- [Transactions and Data Manipulation](./Transactions_and_Data_Manipulation.md)

## Overview

### Understanding ADO.NET Components

ADO.NET provides various components for different data operations:

- **Connection:** Manages the connection to a database.
- **Command:** Executes SQL commands or stored procedures.
- **DataReader:** Reads data from the database in a forward-only, read-only manner.
- **DataSet:** An in-memory representation of data, independent of any data sources.

### Establishing Database Connections

A fundamental aspect of ADO.NET is establishing connections to a database using the `SqlConnection` (for SQL Server) or other database-specific connection classes.

- Example of a connection string:
  ```csharp
  string connectionString = "Server=myServerAddress;Database=myDataBase;User Id=myUsername;Password=myPassword;";
  ```

### Executing Commands

With ADO.NET, you can execute SQL commands or stored procedures using the `SqlCommand` class.

- Executing a simple SQL command:
  ```csharp
  using (SqlConnection connection = new SqlConnection(connectionString))
  {
      SqlCommand command = new SqlCommand("SELECT * FROM MyTable", connection);
      connection.Open();
      SqlDataReader reader = command.ExecuteReader();
      // Process data...
  }
  ```

### Data Retrieval and DataSets

DataSets provide a way to store data in memory. You can fill a DataSet with data from a database, work with the data, and then reconcile changes back to the database.

- Filling a DataSet:
  ```csharp
  using (SqlConnection connection = new SqlConnection(connectionString))
  {
      SqlDataAdapter adapter = new SqlDataAdapter("SELECT * FROM MyTable", connection);
      DataSet ds = new DataSet();
      adapter.Fill(ds, "MyTable");
      // Work with DataSet...
  }
  ```

### Transactions and Data Manipulation

ADO.NET supports transactions for executing multiple operations in an atomic way.

- Implementing transactions:
  ```csharp
  using (SqlConnection connection = new SqlConnection(connectionString))
  {
      connection.Open();
      SqlTransaction transaction = connection.BeginTransaction();
      SqlCommand command = connection.CreateCommand();
      command.Transaction = transaction;

      try
      {
          // Execute commands within the transaction
          transaction.Commit();
      }
      catch
      {
          transaction.Rollback();
          throw;
      }
  }
  ```

---

ADO.NET is a versatile and powerful tool for database interaction in C#. Understanding its components and usage is essential for developing data-driven applications in C#.

Explore more about ADO.NET:
- [Understanding ADO.NET Components](./Understanding_ADO_NET_Components.md)
- [Establishing Database Connections](./Establishing_Database_Connections.md)

Return to [Main Page](/README.md)
