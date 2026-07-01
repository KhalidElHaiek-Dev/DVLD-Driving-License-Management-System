# Database

This folder contains the SQL Server database backup for the DVLD project.

## Included file

- `DVLD.bak` - SQL Server backup file for the `DVLD` database.

## Restore instructions

1. Open SQL Server Management Studio.
2. Right-click `Databases`.
3. Choose `Restore Database...`.
4. Select `Device`.
5. Browse and select `DVLD.bak`.
6. Restore the database with the name `DVLD`.
7. Update the connection string in:

```text
DVLD_DataAccess/clsDataAccessSettings.cs
```

Example:

```csharp
public static string ConnectionString = "Server=YOUR_SERVER;Database=DVLD;Integrated Security=True;";
```

## Note

For a more developer-friendly GitHub repository, a `.sql` script is usually better than a `.bak` file. This backup file is acceptable for now, especially because the project depends on a SQL Server database to run.
