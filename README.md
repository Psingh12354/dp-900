# DP-900 Exam Notes: Data Types

## 1. Structured, Unstructured, and Semi-Structured Data

### 📌 Structured Data
Structured data is highly organized and stored in relational databases with a predefined schema.

#### **Examples:**
- Customer records in a SQL database
- Employee payroll data
- Online transaction records

#### **Azure Tools for Structured Data:**
- **Azure SQL Database** – Fully managed relational database service
- **Azure Synapse Analytics** – Data warehousing and analytics
- **Azure Table Storage** – NoSQL key-value store for structured data

---

### 📌 Unstructured Data
Unstructured data lacks a predefined format and does not fit neatly into relational databases.

#### **Examples:**
- Images and videos
- Emails and social media posts
- Sensor data and logs

#### **Azure Tools for Unstructured Data:**
- **Azure Blob Storage** – Stores large amounts of unstructured data (e.g., images, videos, backups)
- **Azure Data Lake Storage** – Optimized for big data analytics
- **Azure Cognitive Services** – AI-powered analysis of unstructured data like images and text

---

### 📌 Semi-Structured Data
Semi-structured data has some organizational properties, such as key-value pairs, but does not adhere to a strict schema.

#### **Examples:**
- JSON and XML files
- CSV files with inconsistent columns
- NoSQL databases (e.g., MongoDB, Cassandra)

#### **Azure Tools for Semi-Structured Data:**
- **Azure Cosmos DB** – NoSQL database for JSON-like documents
- **Azure Data Factory** – Data integration for structured and semi-structured formats
- **Azure Synapse Analytics** – Can process semi-structured data like JSON, Parquet

---

### 🔥 Summary Table
| Data Type          | Examples                        | Azure Tools |
|--------------------|--------------------------------|-------------|
| **Structured**     | SQL databases, transaction data | Azure SQL Database, Synapse Analytics |
| **Unstructured**   | Images, videos, logs           | Azure Blob Storage, Data Lake, Cognitive Services |
| **Semi-Structured** | JSON, XML, NoSQL               | Azure Cosmos DB, Data Factory, Synapse Analytics |

---

## 2. OLTP, OLAP, and Data Warehousing

### 📌 OLTP (Online Transaction Processing)
OLTP systems handle real-time transaction processing with fast insert, update, and delete operations.

#### **Examples:**
- Banking transactions
- E-commerce order processing
- ATM withdrawals

#### **Azure Tools for OLTP:**
- **Azure SQL Database** – Managed relational database optimized for OLTP
- **Azure Cosmos DB** – NoSQL database for globally distributed applications
- **Azure Database for PostgreSQL/MySQL** – Fully managed open-source databases

---

### 📌 OLAP (Online Analytical Processing)
OLAP systems are designed for complex queries and data analysis, typically used in business intelligence.

#### **Examples:**
- Sales trend analysis
- Financial reporting
- Customer behavior analytics

#### **Azure Tools for OLAP:**
- **Azure Synapse Analytics** – Cloud-scale analytics and data warehousing
- **Azure Analysis Services** – Enterprise-grade data modeling for BI
- **Power BI** – Interactive data visualization and reporting

---

### 📌 Data Warehousing
A data warehouse is a centralized repository for structured and semi-structured data optimized for reporting and analytics.

#### **Examples:**
- Company-wide sales data warehouse
- Healthcare patient data analytics
- Supply chain performance monitoring

#### **Azure Tools for Data Warehousing:**
- **Azure Synapse Analytics** – Unified big data and data warehousing solution
- **Azure Data Factory** – Data ingestion and transformation service
- **Azure Data Lake Storage** – Scalable storage for large datasets

---

### 🔥 Summary Table
| Concept | Description | Examples | Azure Tools |
|---------|-------------|------------|-------------|
| **OLTP** | Real-time transaction processing | Banking, e-commerce, ATM transactions | Azure SQL Database, Cosmos DB, PostgreSQL/MySQL |
| **OLAP** | Analytical processing for complex queries | Sales analysis, financial reporting | Azure Synapse Analytics, Analysis Services, Power BI |
| **Data Warehouse** | Centralized repository for analytics | Sales data warehouse, healthcare analytics | Azure Synapse, Data Factory, Data Lake Storage |

---

## 3. Roles in Data & Software Engineering

| Role | Responsibilities | Relevant Azure Tools |
|------|------------------|----------------------|
| **Database Administrator (DBA)** | Manages databases, ensures performance, security, and backups | Azure SQL Database, Azure Managed Instance, Azure Monitor |
| **Data Engineer** | Designs and builds data pipelines, ETL processes, and integrations | Azure Data Factory, Azure Synapse Analytics, Azure Databricks |
| **Data Analyst** | Analyzes data for insights and reports | Power BI, Azure Synapse Analytics, Azure Analysis Services |
| **Data Scientist** | Builds machine learning models and AI solutions | Azure Machine Learning, Azure Databricks, Cognitive Services |
| **Data Architect** | Designs data solutions, structures, and governance strategies | Azure Synapse Analytics, Azure Data Lake, Azure Purview |
| **Application Developer** | Develops applications that interact with data and services | Azure App Service, Azure Functions, Azure Cosmos DB |
| **Software Engineer** | Builds scalable software solutions, APIs, and backend systems | Azure DevOps, Azure Kubernetes Service, Azure Logic Apps |

---


## 📌 Table
A **Table** is a structured collection of related data stored in a database. It consists of rows (records) and columns (fields), where each column has a specific data type.

### 🛠 Query:
```sql
CREATE TABLE Employees (  
    EmployeeID INT PRIMARY KEY,  
    Name VARCHAR(100),  
    Age INT,  
    Department VARCHAR(50)  
);
```

---

## 📌 View
A **View** is a virtual table that stores the result of a SQL query. It does not store actual data but provides a way to simplify complex queries.

### 🛠 Query:
```sql
CREATE VIEW EmployeeView AS  
SELECT Name, Department FROM Employees  
WHERE Age > 30;  
```
---

## 📌 Schema
A **Schema** is a logical container within a database that groups related objects like tables, views, and stored procedures.

### 🛠 Query:
```sql
CREATE SCHEMA Sales;  
CREATE TABLE Sales.Orders (  
    OrderID INT PRIMARY KEY,  
    Amount DECIMAL(10,2)  
);  
```
---

## 📌 Normalization
Normalization is the process of organizing data in a database to reduce redundancy and improve integrity.

### 🔹 Forms of Normalization:
1️⃣ **1NF (First Normal Form)** – Ensures atomicity by eliminating duplicate columns.  
2️⃣ **2NF (Second Normal Form)** – Removes partial dependencies by ensuring all attributes depend on the primary key.  
3️⃣ **3NF (Third Normal Form)** – Eliminates transitive dependencies.  

### 🛠 Query:
#### **Customers Table**
```sql
CREATE TABLE Customers (  
    CustomerID INT PRIMARY KEY,  
    Name VARCHAR(100),  
    Address VARCHAR(255)  
);  
```
#### **Orders Table**
```sql
CREATE TABLE Orders (  
    OrderID INT PRIMARY KEY,  
    CustomerID INT,  
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)  
);  
```
---

## 📌 SQL (Structured Query Language)
SQL is a language used to query and manipulate relational databases.

### 🛠 Query:
```sql
SELECT * FROM Employees WHERE Age > 25;  
```
---

## 📌 DDL (Data Definition Language)
DDL commands are used to define and modify the structure of database objects.

### 🛠 Query:
```sql
CREATE TABLE Customers (  
    ID INT PRIMARY KEY,  
    Name VARCHAR(100)  
);  

ALTER TABLE Customers ADD Email VARCHAR(255);  

DROP TABLE Customers;  
```
---

## 📌 DML (Data Manipulation Language)
DML commands are used to insert, update, delete, and retrieve data from tables.

### 🛠 Query:
```sql
INSERT INTO Employees (EmployeeID, Name, Age, Department)  
VALUES (1, 'John', 30, 'HR');  

UPDATE Employees SET Age = 35 WHERE EmployeeID = 1;  

DELETE FROM Employees WHERE EmployeeID = 1;  
```
---

## 📌 DCL (Data Control Language)
DCL is used to manage user access to database objects.

### 🛠 Query:
```sql
GRANT SELECT, INSERT ON Employees TO User1;  

REVOKE INSERT ON Employees FROM User1;  
```
---

## 📌 Stored Procedure
A **Stored Procedure** is a precompiled set of SQL statements.

### 🛠 Query:
```sql
CREATE PROCEDURE GetEmployee  
AS  
SELECT * FROM Employees;  

EXEC GetEmployee;  
```
---

## 📌 Index
An **Index** improves the speed of queries by allowing faster data retrieval.

### 🛠 Query:
```sql
CREATE INDEX idx_employee_name ON Employees (Name);
```
