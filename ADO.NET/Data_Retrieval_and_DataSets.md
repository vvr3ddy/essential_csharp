# Data Retrieval and DataSets in ADO.NET

In ADO.NET, retrieving data from a database and manipulating it in memory is a common requirement. The DataSet, along with the DataAdapter, provides a powerful and flexible way to work with data in a disconnected manner. This document explains how to retrieve data and use DataSets in ADO.NET.

## Contents

- [Retrieving Data with DataReader](#retrieving-data-with-datareader)
- [Using DataSets and DataAdapters](#using-datasets-and-dataadapters)
- [Filling a DataSet with DataAdapter](#filling-a-dataset-with-dataadapter)
- [Manipulating Data in a DataSet](#manipulating-data-in-a-dataset)
- [Updating the Database with DataAdapter](#updating-the-database-with-dataadapter)

### Retrieving Data with DataReader

`DataReader` provides a fast, forward-only, read-only way to retrieve data from a database.

```csharp
using (SqlConnection connection = new SqlConnection(connectionString))
{
    SqlCommand command = new SqlCommand("SELECT * FROM YourTable", connection);
    connection.Open();

    using (SqlDataReader reader = command.ExecuteReader())
    {
        while (reader.Read())
        {
            Console.WriteLine(reader["ColumnName"]);
        }
    }
}
```

### Using DataSets and DataAdapters

- **DataSet:** An in-memory representation of data. It can contain one or more DataTables.
- **DataAdapter:** Acts as a bridge between a DataSet and a data source for retrieving and saving data.

### Filling a DataSet with DataAdapter

DataAdapter can fill a DataSet with data from a database, allowing you to work with the data in a disconnected manner.

```csharp
DataSet dataSet = new DataSet();
using (SqlConnection connection = new SqlConnection(connectionString))
{
    SqlDataAdapter adapter = new SqlDataAdapter("SELECT * FROM YourTable", connection);
    adapter.Fill(dataSet, "YourTable");
}
```

### Manipulating Data in a DataSet

Once a DataSet is filled with data, you can manipulate it as if it were connected to the database.

```csharp
DataTable table = dataSet.Tables["YourTable"];
foreach (DataRow row in table.Rows)
{
    // Manipulate DataRow here
}
```

### Updating the Database with DataAdapter

Changes made to the DataSet can be persisted back to the database using the DataAdapter.

```csharp
using (SqlConnection connection = new SqlConnection(connectionString))
{
    SqlDataAdapter adapter = new SqlDataAdapter("SELECT * FROM YourTable", connection);

    SqlCommandBuilder builder = new SqlCommandBuilder(adapter);
    adapter.UpdateCommand = builder.GetUpdateCommand();
    adapter.InsertCommand = builder.GetInsertCommand();
    adapter.DeleteCommand = builder.GetDeleteCommand();

    adapter.Update(dataSet, "YourTable");
}
```

---

Understanding how to retrieve and manipulate data with DataSets and DataAdapters is key for developing data-driven applications in C#. These ADO.NET components provide a powerful way to interact with data sources in a disconnected environment.

Explore more about ADO.NET:
- [Executing Commands](./Executing_Commands.md)
- [Transactions and Data Manipulation](./Transactions_and_Data_Manipulation.md)

Return to [ADO.NET Main Page](./README.md)
