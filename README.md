# Electricity Billing System

A Java Swing desktop application for managing electricity customers, meter information, billing, and bill payments. The project uses MySQL to store application data.

## Features

- User login and signup
- Customer registration and customer information management
- Meter information management
- Electricity bill calculation and generation
- Bill viewing and payment workflow
- Deposit and billing details
- GUI built with Java Swing

## Technologies

- Java
- Java Swing / AWT
- JDBC
- MySQL
- `rs2xml` (used by `net.proteanit.sql.DbUtils` for displaying database query results in tables)

## Project Structure

```text
.
├── database/
│   └── mysql.sql
└── src/
    ├── electricity/
    │   └── billing/
    │       └── system/
    │           ├── Splash.java
    │           ├── Login.java
    │           ├── Project.java
    │           └── ... application classes
    └── icon/
        └── ... application images
```

## Prerequisites

Install the following before running the application:

- JDK (Java Development Kit)
- MySQL Server
- MySQL Connector/J (JDBC driver)
- `rs2xml` / `DbUtils` library, which provides `net.proteanit.sql.DbUtils`
- An IDE such as IntelliJ IDEA, Eclipse, or NetBeans (optional, but recommended)

## Database Setup

1. Start your MySQL server.
2. Open `database/mysql.sql` in a MySQL client.
3. Execute the SQL script to create the `ebs` database and its tables.
4. Ensure the MySQL account used by the application has permission to access the database.

> **Important:** The current `Conn.java` uses a local MySQL connection with username `root` and password `password`. Update the connection settings in `src/electricity/billing/system/Conn.java` to match your local MySQL configuration.

## Configure Dependencies

Add the MySQL Connector/J and `rs2xml` JAR files to the project's classpath in your IDE.

The source imports `net.proteanit.sql.DbUtils`, so the `rs2xml` dependency is required for the customer, deposit, and bill detail table views.

## Run

1. Open the project in your Java IDE.
2. Configure the required libraries.
3. Set up the MySQL database using the SQL script.
4. Verify the database connection settings in `Conn.java`.
5. Run the `electricity.billing.system.Splash` class.

The splash screen should open first, followed by the login screen.

## Notes

- This project is a desktop application; it is not a web application.
- Database credentials are currently configured in source code. For a real deployment, move credentials into a configuration file or environment variables and avoid committing secrets.
- The SQL script contains table creation and sample tax configuration statements. Review it before running against any existing database.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
