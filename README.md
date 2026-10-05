#📊 Data Transformer — Advanced SQL Analytics System
#🎯 Project Overview
Data Transformer is a comprehensive SQL project designed to demonstrate advanced database management, analytical querying, and data manipulation skills.

This project simulates a Corporate Data Analysis System with three core functional areas:

👤 Customer Information Management

🛒 Sales Transaction Processing

💼 Employee Performance Data

🗄️ Database Schema & Sample Data
1️⃣ Customers Table
Stores core customer demographics and registration metadata.

Field	Type	Description
CustomerID	Primary Key	Unique identifier for each customer
FirstName	Varchar	Customer's first name
LastName	Varchar	Customer's last name
Email	Varchar	Unique customer email address
RegistrationDate	Date	Date when the account was created
📄 Sample Data:
CustomerID	FirstName	LastName	Email	RegistrationDate
1	John	Doe	john.doe@email.com	2022-03-15
2	Jane	Smith	jane.smith@email.com	2021-11-02
2️⃣ Orders Table
Tracks customer transactional history and purchasing volume.

Field	Type	Description
OrderID	Primary Key	Unique identifier for each order
CustomerID	Foreign Key	References Customers(CustomerID)
OrderDate	Date	Date when order was placed
TotalAmount	Decimal	Total order value
📄 Sample Data:
OrderID	CustomerID	OrderDate	TotalAmount
101	1	2023-07-01	$150.50
102	2	2023-07-03	$200.75
3️⃣ Employees Table
Contains organizational data, compensation details, and hiring timelines.

Field	Type	Description
EmployeeID	Primary Key	Unique identifier for each employee
FirstName	Varchar	Employee's first name
LastName	Varchar	Employee's last name
Department	Varchar	Assigned department
HireDate	Date	Date of employment start
Salary	Decimal	Annual compensation amount
📄 Sample Data:
EmployeeID	FirstName	LastName	Department	HireDate	Salary
1	Mark	Johnson	Sales	2020-01-15	$50,000.00
2	Susan	Lee	HR	2021-03-20	$55,000.00
⚡ SQL Analytical Tasks & Implementation
The project covers a wide range of advanced SQL techniques across 17 specialized queries:

🔗 Joins & Set Operations
INNER JOIN: Retrieve matching records between orders and customers.

LEFT JOIN: Fetch all customers including those without order history.

RIGHT JOIN: Fetch all orders and associated customer details.

FULL OUTER JOIN: Combine all records from both customers and orders tables.

🔍 Subqueries & Aggregations
Identify customers who placed orders higher than the overall average order amount.

Filter employees earning above the department/overall average salary.

📅 Date & Time Manipulations
Extract Year and Month components from OrderDate.

Calculate age/tenure using Date Differences (OrderDate vs Current Date).

Reformat dates into human-readable strings (e.g., DD-MMM-YYYY).

🔤 String Transformation Functions
CONCAT(): Merge FirstName and LastName into full names.

REPLACE(): Substitute character strings (e.g., replacing "John" with "Jonathan").

UPPER() / LOWER(): Standardize text case sensitivity across datasets.

TRIM(): Strip unwanted leading and trailing whitespace.

📈 Advanced Window Functions & Business Logic
Running Totals: Calculate cumulative sum of TotalAmount for order history.

Ranking Functions: Apply RANK() over orders ordered by revenue size.

Tiered Discount Schemes: Assign discounts using conditional CASE statements:

TotalAmount > $1000 ➡️ 10% Off

TotalAmount > $500 ➡️ 5% Off

Categorization: Group employee salary brackets into Low, Medium, or High.

🛠️ How to Run the Queries
Clone the Repository:

Bash
git clone https://github.com/vaibhavonsigra/SQL-Project.git
cd SQL-Project
Initialize Database:
Import and run the creation script in your SQL environment (MySQL / PostgreSQL / SQL Server):

SQL
SOURCE schema.sql;
SOURCE data.sql;
Execute Analytics Script:
Execute queries individually or run the complete transformation module:

SQL
SOURCE data_transformer.sql;
📌 Submission & Guidelines Compliance
Originality: All queries are written originally and tested for accuracy.

Modularity: Structured logic adheres strictly to standard relational database design patterns.

Designed
