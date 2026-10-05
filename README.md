# DATA TRANSFORM SQL

### Corporate Data Analysis System \| MySQL · phpMyAdmin

> **Project README & Submission Guide**\
> A practical SQL project focused on customer insights, order analysis,
> employee performance, joins, subqueries, date functions, string
> functions, window functions, and conditional logic.

------------------------------------------------------------------------

## 01 · Project Overview

**Data Transform SQL** simulates a small corporate data environment. It
brings together customer, order, and employee records so that business
questions can be answered using SQL.

### Project goals

-   Connect related records using different types of `JOIN`.
-   Analyze order values and employee salaries using subqueries and
    aggregate functions.
-   Transform dates and text into useful reporting formats.
-   Apply window functions to calculate running totals and rankings.
-   Classify orders and salaries using conditional logic.

## 02 · Database Design

Create a database named `corporate_analysis_db` (or use the database
name specified by your instructor).

### Tables and fields

  -----------------------------------------------------------------------
  Table                   Fields                  Purpose
  ----------------------- ----------------------- -----------------------
  `customers`             `CustomerID` (PK),      Stores customer profile
                          `FirstName`,            information
                          `LastName`, `Email`,    
                          `RegistrationDate`      

  `orders`                `OrderID` (PK),         Stores customer
                          `CustomerID` (FK),      purchases
                          `OrderDate`,            
                          `TotalAmount`           

  `employees`             `EmployeeID` (PK),      Stores employee and
                          `FirstName`,            salary information
                          `LastName`,             
                          `Department`,           
                          `HireDate`, `Salary`    
  -----------------------------------------------------------------------

**Relationship:** `orders.CustomerID` refers to `customers.CustomerID`.
One customer may have multiple orders. Employees are analyzed
independently unless the project is extended.

### Sample records from the project brief

**Customers**

    CustomerID FirstName   LastName   Email                  RegistrationDate
  ------------ ----------- ---------- ---------------------- ------------------
             1 John        Doe        john.doe@email.com     2022-03-15
             2 Jane        Smith      jane.smith@email.com   2021-11-02

**Orders**

    OrderID   CustomerID OrderDate      TotalAmount
  --------- ------------ ------------ -------------
        101            1 2023-07-01          150.50
        102            2 2023-07-03          200.75

**Employees**

    EmployeeID FirstName   LastName   Department   HireDate         Salary
  ------------ ----------- ---------- ------------ ------------ ----------
             1 Mark        Johnson    Sales        2020-01-15     50000.00
             2 Susan       Lee        HR           2021-03-20     55000.00

*These are illustrative sample rows. Your output will depend on the
records entered in your database.*

## 03 · SQL Skills Demonstrated

  -----------------------------------------------------------------------
  SQL concept                         What it does in this project
  ----------------------------------- -----------------------------------
  `INNER JOIN`                        Shows orders that have matching
                                      customers

  `LEFT JOIN`                         Keeps all customers, including
                                      those without orders

  `RIGHT JOIN`                        Keeps all orders and their matching
                                      customer details

  `FULL OUTER JOIN`                   Combines matched and unmatched
                                      rows; emulate in MySQL with `UNION`
                                      if needed

  Subqueries                          Compare orders or salaries against
                                      an average

  Date functions                      Extract month, calculate date
                                      differences, format dates

  String functions                    Join names, replace text, change
                                      case, trim spaces

  Window functions                    Calculate running totals and rank
                                      orders

  `CASE`                              Apply discounts and categorize
                                      salary levels
  -----------------------------------------------------------------------

## 04 · Tasks to Complete

Use this checklist to track the required work. Add the SQL query and its
result screenshot beneath each task in your final submission.

-   [ ] **01 --- INNER JOIN:** Retrieve order and customer details where
    a matching customer exists.
-   [ ] **02 --- LEFT JOIN:** Retrieve all customers and their
    corresponding orders, if any.
-   [ ] **03 --- RIGHT JOIN:** Retrieve all orders and corresponding
    customer details, if any.
-   [ ] **04 --- FULL OUTER JOIN:** Retrieve all customers and all
    orders, including unmatched records. In MySQL, use a suitable
    `UNION` approach.
-   [ ] **05 --- Order subquery:** Find customers who placed orders
    worth more than the average order amount.
-   [ ] **06 --- Salary subquery:** Find employees whose salary is above
    the average salary.
-   [ ] **07 --- Month extraction:** Extract the month from each order
    date.
-   [ ] **08 --- Date difference:** Calculate the number of days between
    each order date and the current date.
-   [ ] **09 --- Date formatting:** Display `OrderDate` in `YYYY-MM-DD`
    format.
-   [ ] **10 --- Full name:** Concatenate `FirstName` and `LastName`.
-   [ ] **11 --- Text replacement:** Replace a space in a name with
    another string (for example, `John Doe` → `Johnathan Doe`, as
    specified by the exercise).
-   [ ] **12 --- Case conversion:** Convert first names to uppercase and
    last names to lowercase.
-   [ ] **13 --- Email cleanup:** Remove leading and trailing spaces
    from email values.
-   [ ] **14 --- Running total:** Calculate a cumulative total of order
    amounts.
-   [ ] **15 --- Order ranking:** Rank orders by `TotalAmount` using
    `RANK()`.
-   [ ] **16 --- Discount logic:** Assign a discount based on order
    amount (for example, above 100 = 10%; above 50 = 5%). Confirm the
    exact threshold interpretation with your instructor.
-   [ ] **17 --- Salary category:** Classify employee salaries as High,
    Medium, or Low. State the salary cut-offs you assume.

## 05 · How to Run in phpMyAdmin

1.  Open **phpMyAdmin** in your browser and sign in to your local
    server.
2.  Create or select the project database.
3.  Open the **SQL** tab and run the table-creation statements.
4.  Insert the sample or instructor-approved records into each table.
5.  Run each task query individually, or in small groups, to make errors
    easier to identify.
6.  Check the result grid. Confirm column names, row counts, and values.
7.  Capture a screenshot showing the query and its output. Keep the task
    number visible in your document.
8.  Save your final SQL script and this README with the project files.

> **Compatibility note:** MySQL does not support `FULL OUTER JOIN`
> directly. Use a `LEFT JOIN` combined with a `RIGHT JOIN` using `UNION`
> (or another instructor-approved equivalent). Window functions such as
> `RANK()` require MySQL 8.0+.

## 06 · Assumptions & Data Notes

-   Use consistent table and column names throughout the SQL script.
    This README uses lowercase table names and the field names shown in
    the brief.
-   `CustomerID`, `OrderID`, and `EmployeeID` should uniquely identify
    records.
-   `orders.CustomerID` should reference an existing customer when
    enforcing a foreign key.
-   Store dates in a MySQL `DATE` or appropriate date/time type, and
    store money values in `DECIMAL` rather than floating-point types.
-   The exercise does not specify salary bands or every discount
    boundary. Clearly document any assumptions used in your queries.
-   If your MySQL version differs from the one assumed, adjust
    unsupported syntax and mention the change.

## 07 · Results & Evidence

For a strong submission, include evidence for **every task**, not just
the final database screen.

Suggested format for each task:

**Task 01 --- INNER JOIN**

-   **Objective:** Retrieve order details with matching customer
    information.
-   **SQL Query:** Paste the exact query used in phpMyAdmin.
-   **Output:** Insert a screenshot of the result grid.
-   **Observation:** Write one or two lines describing what the result
    shows.

Repeat this block for Tasks 02--17. Ensure screenshots are readable and
correspond to the query directly above them.

## 08 · Suggested Folder Structure

``` text
Data-Transform-SQL/
├── README.md
├── sql/
│   ├── 01_create_database_tables.sql
│   ├── 02_insert_sample_data.sql
│   └── 03_analysis_tasks.sql
└── screenshots/
    ├── task-01-inner-join.png
    ├── task-02-left-join.png
    └── ... task-17-salary-category.png
```

## 09 · Project Summary

This project demonstrates how SQL can turn related raw records into
useful business information. It combines relational querying, data
transformation, analysis, and reporting techniques in a single practical
workflow using MySQL and phpMyAdmin.

### Final submission checklist

-   [ ] Database and all three tables created
-   [ ] Sample or approved data inserted
-   [ ] All 17 task queries tested
-   [ ] SQL file saved and organized
-   [ ] Query and output screenshot added for each task
-   [ ] Assumptions documented
-   [ ] README reviewed for clarity
-   [ ] Project uploaded to GitHub, if required by the instructor

------------------------------------------------------------------------

**Prepared for academic project submission**\
*Write original queries, verify every result in your own database, and
follow your instructor's submission and citation rules.*
