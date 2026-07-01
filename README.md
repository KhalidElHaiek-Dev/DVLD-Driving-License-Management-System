# DVLD - Driving & Vehicle License Management System

DVLD is a C# Windows Forms desktop application that simulates a Driving & Vehicle License Department system. It manages people, users, drivers, driving license applications, tests, local licenses, international licenses, detained licenses, and license-related services.

## Main Features

* People management with national-number based search
* User management and account settings
* Local driving license applications
* International driving license applications
* License renewal
* Replacement for lost or damaged licenses
* Detain and release detained licenses
* Drivers list and license history
* Test appointments and test results
* Application types and test types management

## Technologies Used

* C#
* Windows Forms
* SQL Server
* ADO.NET
* .NET Framework 4.8
* 3-tier architecture

## Project Architecture

The solution is organized into three main projects:

```text
DVLD/              Presentation Layer - Windows Forms UI
DVLD_Buisness/     Business Logic Layer
DVLD_DataAccess/   Data Access Layer - SQL Server / ADO.NET
```

## Solution File

Open the solution from:

```text
DVLD/DVLD.sln
```

## Database Setup

This project requires a SQL Server database named `DVLD`.

The repository includes a database backup file:

```text
database/DVLD_GitHub.bak
```

Before running the application:

1. Restore `database/DVLD_GitHub.bak` in SQL Server Management Studio.
2. Restore it with the database name `DVLD`.
3. Update the connection string in:

```text
DVLD_DataAccess/clsDataAccessSettings.cs
```

Example connection string:

```csharp
public static string ConnectionString = "Server=.;Database=DVLD;Integrated Security=True;";
```

If you restore the database using a different name, make sure to update the `Database` value in the connection string.

## Screenshots

### Login Screen

![Login Screen](screenshots/login-screen.png)

### Main Dashboard

![Main Dashboard](screenshots/main-dashboard.png)

### Applications Menu

![Applications Menu](screenshots/applications.png)

### People Management

![People Management](screenshots/people-management.png)

### Users Management

![Users Management](screenshots/users-management.png)

### Local License Application

![Local License Application](screenshots/local-license-application.png)

### Test Appointments

![Test Appointments](screenshots/test-appointments.png)

### International License Application

![International License Application](screenshots/international-license.png)

### Detained Licenses

![Detained Licenses](screenshots/detained-licenses.png)

## How to Run

1. Clone the repository.
2. Open `DVLD/DVLD.sln` in Visual Studio.
3. Restore `database/DVLD_GitHub.bak` as a SQL Server database named `DVLD`.
4. Update the connection string in `DVLD_DataAccess/clsDataAccessSettings.cs`.
5. Build the solution.
6. Run the project.
7. Login using an active user from the `Users` table.

## Login Users

After restoring the database, you can find available users by running this query in SQL Server Management Studio:

```sql
USE DVLD;
GO

SELECT UserID, UserName, Password, IsActive
FROM Users;
```

Use a user where `IsActive = 1`.

## Notes

This project was built as part of a C# desktop development learning path. It focuses on applying Windows Forms, SQL Server, ADO.NET, object-oriented programming, and layered architecture to a realistic business system.

## Future Improvements

Possible future improvements:

* Improve the UI design
* Add role-based permissions
* Add reports and dashboard statistics
* Add password hashing
* Add better validation
* Add unit tests
* Convert the system into a web application

## Demo Video

A full walkthrough video of the DVLD system will be added soon.

## Author

Developed by **Khalid El Haiek**.
