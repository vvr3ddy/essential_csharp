Certainly! Here's a markdown document titled "Executing Commands" that focuses on how to execute SQL commands using ADO.NET in C#.

```markdown
# Executing Commands in ADO.NET

In ADO.NET, executing commands is a fundamental operation for interacting with a database. This involves running SQL queries or stored procedures to retrieve, insert, update, or delete data. This document covers how to execute commands using the ADO.NET framework.

## Contents

- [SqlCommand for SQL Server](#sqlcommand-for-sql-server)
- [OleDbCommand for Other Databases](#oledbcommand-for-other-databases)
- [Executing Queries](#executing-queries)
- [Executing Non-Query Commands](#executing-non-query-commands)
- [Using Stored Procedures](#using-stored-procedures)

### SqlCommand for SQL Server

The `SqlCommand` object is used to execute SQL statements or stored procedures against a SQL Server database.

#### Example Usage:

```csharp
using System.Data.SqlClient;

string connectionString = "your_connection_string_here";
using (SqlConnection connection = new SqlConnection(connectionString))
{
    SqlCommand command = new SqlCommand("SELECT * FROM YourTable", connection);
    connection.Open();

    using (SqlDataReader reader = command.ExecuteReader())
    {
        while (reader.Read())
        {
            Console.WriteLine(reader["ColumnName"].ToString());
        }
    }

    connection.Close();
}
```

### OleDbCommand for Other Databases

For databases that support OLE DB, such as Access or Oracle, the `OleDbCommand` is used.

#### Example Usage:

```csharp
using System.Data.OleDb;

string connectionString = "your_oledb_connection_string_here";
using (OleDbConnection connection = new OleDbConnection(connectionString))
{
    OleDbCommand command = new OleDbCommand("SELECT * FROM YourTable", connection);
    connection.Open();

    using (OleDbDataReader reader = command.ExecuteReader())
    {
        while (reader.Read())
        {
            // Process the data
        }
    }

    connection.Close();
}
```

### Executing Queries

To retrieve data from a database, you can execute a query using `ExecuteReader` method of the command object, which returns a `DataReader`.

### Executing Non-Query Commands

For insert, update, or delete operations, use the `ExecuteNonQuery` method. This method does not return any data but gives the number of rows affected by the command.

```csharp
command.CommandText = "INSERT INTO YourTable (Column1, Column2) VALUES (Value1, Value2)";
int affectedRows = command.ExecuteNonQuery();
```

### Using Stored Procedures

To execute a stored procedure, set the `CommandType` of the command object to `CommandType.StoredProcedure` and set the command text to the stored procedure name.

```csharp
command.CommandType = CommandType.StoredProcedure;
command.CommandText = "YourStoredProcedureName";
// Add any required parameters
command.ExecuteNonQuery();
```

---

Executing commands effectively is key to interacting with databases using ADO.NET. Whether you're querying data, updating records, or calling stored procedures, understanding these operations is essential for building data-driven applications in C#.

Explore more about ADO.NET:
- [Data Retrieval and DataSets](./Data_Retrieval_and_DataSets.md)
- [Transactions and Data Manipulation](./Transactions_and_Data_Manipulation.md)

Return to [ADO.NET Main Page](./README.md)
```

This document provides a comprehensive guide on executing SQL commands using ADO.NET in C#. It covers executing both queries and non-query commands, as well as working with stored procedures, offering a solid foundation for database operations in C# applications.
