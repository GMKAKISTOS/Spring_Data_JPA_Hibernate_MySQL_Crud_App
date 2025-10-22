# Spring Data JPA Hibernate MySQL CRUD Application

This repository contains a command-line interface (CLI) application built with Spring Boot, Spring Data JPA, and Hibernate. It demonstrates full CRUD (Create, Read, Update, Delete) operations on a MySQL database for managing companies, departments, tasks, and employee information.

## Features

- **Comprehensive CRUD Operations:** Perform Create, Read, Update, and Delete operations for all entities.
- **Relational Data Model:** Manages relationships between entities (Company, Department, Task, Employee).
- **Interactive CLI:** A user-friendly command-line menu to interact with the application.
- **JPA & Hibernate:** Utilizes Java Persistence API (JPA) with Hibernate as the persistence provider for object-relational mapping.
- **Advanced SQL Schema:** Includes a detailed SQL script with table definitions, constraints, triggers, stored procedures, and scheduled events for database setup.
- **Data Validation:** Implements input validation both in the application logic and at the database level with constraints and triggers.

## Database Schema

The application uses a relational schema with four main tables: `company`, `department`, `task`, and `information`.

-   A `Company` has a one-to-many relationship with `Department`.
-   A `Department` has a one-to-many relationship with `Task` and `Information` (employees).
-   A `Task` can be assigned to multiple employees (one-to-many relationship with `Information`).

The `Application.sql` file contains the complete schema definition, including:
-   Table creation with constraints.
-   Database triggers for data formatting and integrity (e.g., capitalizing company names).
-   Stored procedures for maintenance tasks (e.g., resetting auto-increment values).
-   Scheduled events for periodic data updates (e.g., updating employee ages).

## Technologies Used

-   **Java 24**
-   **Spring Boot**
-   **Spring Data JPA**
-   **Hibernate**
-   **MySQL**
-   **Maven**

## Prerequisites

-   Java JDK 24 or later
-   Maven
-   MySQL Server

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/panoschron97/Spring_Data_JPA_Hibernate_MySQL_Crud_App.git
    cd Spring_Data_JPA_Hibernate_MySQL_Crud_App
    ```

2.  **Database Setup:**
    -   Ensure your MySQL server is running.
    -   Execute the `Application.sql` script located in the root directory. This will create the `application` database, tables, triggers, and stored procedures. You can use a MySQL client like MySQL Workbench or the command line:
        ```bash
        mysql -u your_username -p < Application.sql
        ```

3.  **Configure Database Connection:**
    -   Open the `crud/src/main/resources/application.properties` file.
    -   Update the following properties to match your MySQL configuration:
        ```properties
        spring.datasource.url=jdbc:mysql://localhost:3306/application
        spring.datasource.username=root
        spring.datasource.password=your_password
        ```

4.  **Build and Run the Application:**
    -   Navigate to the `crud` directory:
        ```bash
        cd crud
        ```
    -   Build the project using Maven:
        ```bash
        mvn clean install
        ```
    -   Run the application:
        ```bash
        mvn spring-boot:run
        ```

## Usage

Once the application is running, it will display a menu of options in the console. Enter the number corresponding to the action you want to perform.

**Menu Options:**

1.  Add a new company.
2.  Add a new company along with a department.
3.  Add a new department to an existing company.
4.  Add a new task to a department.
5.  Add a new employee.
6.  View all companies and their departments.
7.  View all companies.
8.  View all departments.
9.  View all tasks.
10. View all employees.
11. View a specific department and its associated company.
12. View a specific company and its list of departments.
13. Update a company's details.
14. Delete a company.
15. Update a department's details.
16. Delete a department.
17. Update a task's details.
18. Delete a task.
19. Update an employee's details (e.g., assign to a new task).
20. Delete an employee.
21. View a specific task and its associated department.
22. View a specific employee with their department and task details.
23. Exit the application.
