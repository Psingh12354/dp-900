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

## 📌 What is a Relational Database?
A **Relational Database (RDBMS)** is a structured collection of data organized into tables with predefined relationships. It follows **ACID** (Atomicity, Consistency, Isolation, Durability) properties to ensure data reliability.



## 📌 Table
A **Table** is a structured collection of related data stored in a database. It consists of rows (records) and columns (fields), where each column has a specific data type.

- A table consists of **rows (records)** and **columns (attributes)**.
- Each row represents a unique entry, and each column holds specific data types.

#### **Example:** Customer Table
| CustomerID | Name     | Email           | Age |
|------------|---------|----------------|-----|
| 101        | Alice   | alice@email.com | 30  |
| 102        | Bob     | bob@email.com   | 25  |


### 🛠 Query:
```sql
CREATE TABLE Employees (  
    EmployeeID INT PRIMARY KEY,  
    Name VARCHAR(100),  
    Age INT,  
    Department VARCHAR(50)  
);
``

##  Azure Tools for Relational Databases

| **Azure Tool** | **Description** |
|--------------|----------------|
| **Azure SQL Database** | Managed relational database with scalability |
| **Azure Database for PostgreSQL** | Fully managed PostgreSQL database |
| **Azure Database for MySQL** | Fully managed MySQL database |
| **Azure Synapse Analytics** | Supports relational data for analytics |`

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
# 📌 Normalization in Databases

Normalization is the process of organizing data in a database to **eliminate redundancy** and **ensure data integrity** by breaking large tables into smaller ones while maintaining relationships.

## 🔹 Why is Normalization Important?
- ✅ Reduces **data redundancy** (no duplicate data).
- ✅ Improves **data consistency and integrity**.
- ✅ Makes queries **more efficient**.
- ✅ Prevents **data anomalies** (insertion, update, deletion errors).

---
---

## 🔹 Forms of Normalization

### 1️⃣ First Normal Form (1NF) - Ensure Atomicity
🔹 **Rule:** Each column should contain atomic (indivisible) values, and there should be no duplicate columns.

#### ❌ Bad Example (Not in 1NF)
```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100),
    PhoneNumbers VARCHAR(255) -- ❌ Multiple phone numbers in one field
);
```
#### 🚨 Problem:
- Storing multiple phone numbers in a single column breaks atomicity.

#### ✅ Fix (Convert to 1NF)
```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100)
);

CREATE TABLE CustomerPhones (
    CustomerID INT,
    PhoneNumber VARCHAR(15),
    PRIMARY KEY (CustomerID, PhoneNumber),
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```
---

### 2️⃣ Second Normal Form (2NF) - Remove Partial Dependencies
🔹 **Rule:** Every **non-key** column should depend on the **entire primary key**, not just part of it.

#### ❌ Bad Example (Not in 2NF)
```sql
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    CustomerName VARCHAR(100), -- ❌ Depends only on CustomerID, not OrderID
    OrderDate DATE
);
```

#### 🚨 Problem:
- `CustomerName` depends **only** on `CustomerID`, not on `OrderID`.

#### ✅ Fix (Convert to 2NF - Separate Customers Table)
```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    Name VARCHAR(100)
);

CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    OrderDate DATE,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```
---

### 3️⃣ Third Normal Form (3NF) - Remove Transitive Dependencies
🔹 **Rule:** **Non-key** attributes should depend **only** on the **primary key** (not other non-key columns).

#### ❌ Bad Example (Not in 3NF)
```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(100),
    DepartmentID INT,
    DepartmentName VARCHAR(100) -- ❌ Depends on DepartmentID, not EmployeeID
);
```
#### 🚨 Problem:
- `DepartmentName` **depends on `DepartmentID`**, not `EmployeeID`.

#### ✅ Fix (Convert to 3NF - Separate Departments Table)
```sql
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(100)
);

CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(100),
    DepartmentID INT,
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```
---

### 4️⃣ Boyce-Codd Normal Form (BCNF) - Strengthened 3NF
🔹 **Rule:** Every determinant (column that determines another column) must be a **candidate key**.

#### ❌ Bad Example (Not in BCNF)
```sql
CREATE TABLE StudentCourses (
    StudentID INT,
    CourseID INT,
    Instructor VARCHAR(100), -- ❌ Instructor depends on CourseID, not StudentID
    PRIMARY KEY (StudentID, CourseID)
);
```
#### 🚨 Problem:
- `Instructor` is determined by `CourseID`, not by `(StudentID, CourseID)`.

#### ✅ Fix (Convert to BCNF - Separate Instructors Table)
```sql
CREATE TABLE Courses (
    CourseID INT PRIMARY KEY,
    Instructor VARCHAR(100)
);

CREATE TABLE StudentCourses (
    StudentID INT,
    CourseID INT,
    PRIMARY KEY (StudentID, CourseID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);
```
---

### 5️⃣ Fourth Normal Form (4NF) - Remove Multivalued Dependencies
🔹 **Rule:** A table should not contain **two or more independent multi-valued** attributes.

#### ❌ Bad Example (Not in 4NF)
```sql
CREATE TABLE StudentActivities (
    StudentID INT,
    Hobby VARCHAR(100), -- ❌ Multi-valued
    Skill VARCHAR(100)  -- ❌ Multi-valued
);
```
#### 🚨 Problem:
- A student may have multiple hobbies **and** multiple skills, leading to redundancy.

#### ✅ Fix (Convert to 4NF - Create Separate Tables)
```sql
CREATE TABLE Hobbies (
    StudentID INT,
    Hobby VARCHAR(100),
    PRIMARY KEY (StudentID, Hobby)
);

CREATE TABLE Skills (
    StudentID INT,
    Skill VARCHAR(100),
    PRIMARY KEY (StudentID, Skill)
);
```
---

### 6️⃣ Fifth Normal Form (5NF) - Remove Join Dependencies
🔹 **Rule:** A table should not have **unnecessary joins** that can be broken down into smaller tables.

#### ❌ Bad Example (Not in 5NF)
```sql
CREATE TABLE Sales (
    SalespersonID INT,
    ProductID INT,
    CustomerID INT,
    PRIMARY KEY (SalespersonID, ProductID, CustomerID)
);
```
#### 🚨 Problem:
- A salesperson may sell **many products** to **many customers**, creating complex dependencies.

#### ✅ Fix (Convert to 5NF - Break into Multiple Tables)
```sql
CREATE TABLE Salespersons (
    SalespersonID INT PRIMARY KEY
);

CREATE TABLE Products (
    ProductID INT PRIMARY KEY
);

CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY
);

CREATE TABLE SalesDetails (
    SalespersonID INT,
    ProductID INT,
    CustomerID INT,
    PRIMARY KEY (SalespersonID, ProductID, CustomerID),
    FOREIGN KEY (SalespersonID) REFERENCES Salespersons(SalespersonID),
    FOREIGN KEY (ProductID) REFERENCES Products(ProductID),
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```
---

## 🎯 Summary of Normalization Forms
| Normal Form | Rule |
|-------------|-------------------------------------------------------------|
| **1NF** | Ensure atomicity (no multiple values in a single column). |
| **2NF** | No partial dependencies (every non-key column depends on the full primary key). |
| **3NF** | No transitive dependencies (every non-key column depends only on the primary key). |
| **BCNF** | Every determinant must be a candidate key. |
| **4NF** | No multi-valued dependencies. |
| **5NF** | No unnecessary joins. |

---
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

---

## 📌 Managing relational databases
Managing relational databases involves tasks like provisioning, security, backup, monitoring, and optimization to ensure smooth database operations in Azure.

---

## 1. Database Provisioning
Provisioning involves setting up a new database with necessary configurations.

### **Azure Tools for Database Provisioning**
- **Azure SQL Database** – Fully managed relational database.
- **Azure Database for PostgreSQL** – Open-source PostgreSQL as a managed service.
- **Azure Database for MySQL** – Managed MySQL database service.

### **Example: Provisioning an Azure SQL Database**
- Navigate to **Azure Portal** → **Create a resource** → **Azure SQL Database**.
- Choose the **server name, pricing tier**, and **compute resources**.
- Configure **backup and redundancy** options.

---

## 2. Security & Access Management
Ensuring data security through authentication, authorization, and encryption.

### **Key Security Features**
- **Azure Active Directory (AAD)** – Centralized authentication.
- **Firewall Rules** – Restricts database access based on IP.
- **Transparent Data Encryption (TDE)** – Encrypts database files.
- **Always Encrypted** – Protects sensitive data at the column level.

### **Example: Setting Up Firewall Rules**
```sql
EXEC sp_set_firewall_rule @name = 'AllowClientIP', @start_ip_address = '192.168.1.1', @end_ip_address = '192.168.1.1';
```

---

## 3. Backup & Restore
Ensuring business continuity through automated backups and point-in-time restores.

### **Backup Options in Azure**
- **Automated Backups** – Full, differential, and transaction log backups.
- **Geo-Redundant Backups** – Stored in multiple Azure regions.
- **Point-in-Time Restore** – Recover database to a specific point.

### **Example: Restoring an Azure SQL Database**
- Navigate to **Azure Portal** → **Azure SQL Database** → **Backups** → **Restore**.

---

## 4. Performance Monitoring & Optimization
Improving database performance using built-in tools.

### **Azure Performance Tools**
- **Azure SQL Query Performance Insights** – Analyzes slow queries.
- **Automatic Tuning** – Suggests and applies performance improvements.
- **Indexing & Partitioning** – Optimizes query execution.

### **Example: Enabling Automatic Tuning**
```sql
ALTER DATABASE myDB SET AUTOMATIC_TUNING = AUTO;
```

---

## 5. High Availability & Disaster Recovery
Ensuring databases are highly available and resilient against failures.

### **Azure Solutions for High Availability**
- **Geo-Replication** – Replicates database to another region.
- **Failover Groups** – Automated failover between databases.
- **Zone-Redundant Databases** – Distributed across multiple availability zones.

### **Example: Enabling Geo-Replication**
- Navigate to **Azure SQL Database** → **Geo-Replication** → **Enable**.

---

## 🔥 Summary Table
| Feature | Description | Azure Tools |
|---------|-------------|-------------|
| **Provisioning** | Setting up a new database | Azure SQL Database, PostgreSQL, MySQL |
| **Security** | Access control & encryption | AAD, Firewall, TDE, Always Encrypted |
| **Backup & Restore** | Automated & manual recovery options | Azure Backup, Geo-Replication |
| **Performance Optimization** | Query tuning & indexing | Query Insights, Automatic Tuning |
| **High Availability** | Ensuring uptime & resilience | Failover Groups, Zone Redundancy |

---


## 🔹 1. Managing an Azure Account
Azure account management involves handling subscriptions, resource groups, and access control.

### 🔹 **Key Components:**
- **Azure Subscription:** Required to access Azure services.
- **Resource Groups:** Logical containers for organizing resources.
- **Role-Based Access Control (RBAC):** Provides permissions based on roles.
- **Azure Portal, CLI, and PowerShell:** Used for managing accounts and resources.

### **Example:** Creating a Resource Group using Azure CLI
```sh
az group create --name MyResourceGroup --location eastus
```
📌 **Reference:** [Create a Resource Group](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/manage-resource-groups-portal)

---

## 🔹 2. Azure Blob Storage
Blob Storage is used for storing unstructured data like images, videos, and backups.

### 🔹 **Key Features:**
- Stores large amounts of unstructured data.
- Supports Hot, Cool, and Archive tiers.
- Provides public and private access levels.

### **Example:** Upload a file to Blob Storage using Azure CLI
```sh
az storage blob upload --account-name mystorageaccount --container-name mycontainer --name myfile.txt --file myfile.txt
```
📌 **Reference:** [Azure Blob Storage Overview](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction)

### **Steps to Create a Blob Storage:**
1. Navigate to **Azure Portal** → **Storage Accounts** → **Create Storage Account**
2. Choose **Performance**, **Replication**, and **Access tier**
3. Click **Review + Create**

📌 **Reference:** [Create Azure Blob Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal)

---

## 🔹 3. Azure File Storage
Azure File Storage provides fully managed file shares accessible via SMB and NFS protocols.

### 🔹 **Key Features:**
- Supports SMB and NFS for file sharing.
- Can be mounted on Windows, Linux, and macOS.
- Offers snapshots for backup and recovery.

### **Example:** Mounting Azure File Share on Windows
```sh
net use Z: \\storageaccount.file.core.windows.net\fileshare /user:storageaccount storagekey
```
📌 **Reference:** [Azure File Storage Overview](https://learn.microsoft.com/en-us/azure/storage/files/storage-files-introduction)

### **Steps to Set Up Azure File Storage:**
1. Go to **Azure Portal** → **Storage Accounts** → **File Shares**
2. Click **+ File Share** → Provide a name and quota
3. Click **Create** and mount it using SMB/NFS

📌 **Reference:** [Create an Azure File Share](https://learn.microsoft.com/en-us/azure/storage/files/storage-how-to-create-file-share)

---

## 🔹 4. Azure Table Storage
Azure Table Storage is a NoSQL key-value store designed for semi-structured data.

### 🔹 **Key Features:**
- Provides fast and scalable key-value storage.
- Supports OData queries.
- Low-cost storage option for structured data.

### **Example:** Insert data into Azure Table Storage using PowerShell
```powershell
Add-AzTableRow -TableName "MyTable" -PartitionKey "Partition1" -RowKey "001" -Property @{ Name="John Doe"; Age=30 }
```
📌 **Reference:** [Azure Table Storage Overview](https://learn.microsoft.com/en-us/azure/storage/tables/table-storage-overview)

### **Steps to Create a Table Storage:**
1. Navigate to **Azure Portal** → **Storage Accounts** → **Tables**
2. Click **+ Table** → Provide a name
3. Start adding entities using **Azure Table Explorer**

📌 **Reference:** [Create Azure Table Storage](https://learn.microsoft.com/en-us/azure/storage/tables/table-storage-design-guide)

---

## 🔹 What are Non-Relational Databases?
A **Non-Relational Database** (also called **NoSQL Database**) is a type of database that does not store data in a traditional **table-based relational structure**. Instead, it uses **flexible schema models** for high **scalability** and **performance**.

### ✅ **Key Benefits**
- **Schema Flexibility** – No fixed structure, ideal for dynamic data.  
- **High Scalability** – Supports horizontal scaling (adding more servers).  
- **Fast Read & Write** – Optimized for high-speed transactions.  
- **Unstructured & Semi-Structured Data Support** – Stores JSON, XML, key-value, graphs, etc.  

---

## 🔹 Non-Relational Data Types
Unlike relational databases (SQL) that store structured tabular data, non-relational databases store **unstructured** and **semi-structured** data.

| Data Type | Description | Examples |
|-----------|------------|----------|
| **Key-Value** | Simple key-value pairs for ultra-fast lookups | Redis, DynamoDB |
| **Document** | Stores JSON, XML, or BSON documents | MongoDB, CouchDB |
| **Column-Family** | Optimized for large-scale analytics with column-based storage | Apache Cassandra, HBase |
| **Graph** | Stores complex relationships between data entities | Neo4j, Azure Cosmos DB (Graph API) |

---

## 🔹 NoSQL Database Models  
NoSQL databases are categorized into **four main types**, each designed for specific use cases.

### 1️⃣ **Key-Value Databases**
- 🔹 **Data Structure:** Simple key-value pairs.
- 🔹 **Best for:** Caching, real-time analytics, session management.
- 🔹 **Examples:** Redis, Amazon DynamoDB, Riak.

#### ✅ **Example Key-Value Storage in Redis**
```sql
SET user:1 "John Doe"
GET user:1
```

---

### 2️⃣ **Document Databases**
- 🔹 **Data Structure:** JSON, BSON, or XML documents.
- 🔹 **Best for:** Flexible data storage, content management, catalogs.
- 🔹 **Examples:** MongoDB, CouchDB, Firebase Firestore.

#### ✅ **Example Document Storage in MongoDB**
```sql
db.users.insertOne({
    "_id": 1,
    "name": "Alice",
    "email": "alice@example.com",
    "orders": [1001, 1002, 1003]
})
```

---

### 3️⃣ **Column-Family Databases**
- 🔹 **Data Structure:** Stores data in columns instead of rows.
- 🔹 **Best for:** Large-scale analytics, data warehousing, real-time big data.
- 🔹 **Examples:** Apache Cassandra, Google Bigtable, HBase.

#### ✅ **Example Column-Family Storage in Cassandra**
```sql
CREATE TABLE Users (
    userID UUID PRIMARY KEY,
    name TEXT,
    email TEXT
);
```

INSERT INTO Users (userID, name, email) VALUES (uuid(), 'Bob', 'bob@example.com');

---

### 4️⃣ **Graph Databases**
- 🔹 **Data Structure:** Nodes (entities) and Edges (relationships).
- 🔹 **Best for:** Social networks, fraud detection, recommendation engines.
- 🔹 **Examples:** Neo4j, Amazon Neptune, Azure Cosmos DB (Graph API).

#### ✅ **Example Graph Query in Neo4j**
```sql
CREATE (Alice:Person {name:"Alice"})  
CREATE (Bob:Person {name:"Bob"})  
CREATE (Alice)-[:FRIENDS_WITH]->(Bob)
```
---

## 🔹 Azure Non-Relational Database Options
Microsoft Azure provides multiple **NoSQL database solutions** for different workloads.

| Azure Service | Database Type | Best For |
|--------------|--------------|----------|
| **Azure Cosmos DB** | Multi-model (Key-Value, Document, Column-Family, Graph) | Global-scale apps, IoT, analytics |
| **Azure Table Storage** | Key-Value Store | NoSQL storage for structured data |
| **Azure Blob Storage** | Unstructured Data | Storing images, videos, logs, backups |
| **Azure Data Lake Storage** | Big Data File Storage | Large-scale analytics, data lakes |
| **Azure Cache for Redis** | Key-Value Store (In-memory) | Caching, real-time processing |

---

## 🔹 When to Use Non-Relational Databases?  
Use **NoSQL** when:  
✅ Data structure is **dynamic** or **schema-free** (e.g., JSON).  
✅ High-speed **read/write** operations are required.  
✅ **Horizontal scaling** (sharding) is needed for **large-scale applications**.  
✅ Handling **big data**, **real-time analytics**, or **graph-based relationships**.  

---

## 🎯 **Summary: SQL vs NoSQL**  
| Feature | SQL (Relational DB) | NoSQL (Non-Relational DB) |
|---------|---------------------|---------------------------|
| **Data Model** | Tables (Rows & Columns) | Key-Value, Document, Column-Family, Graph |
| **Schema** | Fixed schema | Flexible schema |
| **Scaling** | Vertical (scale-up) | Horizontal (scale-out) |
| **Best For** | Structured data, transactions | Unstructured/Semi-structured data, Big Data |

---

## 📌 Conclusion  
- **Non-Relational Databases (NoSQL)** are **highly scalable** and ideal for handling **big data** and **dynamic applications**.  
- **Azure Cosmos DB** is a **fully managed NoSQL service** that supports **multi-model** (document, key-value, graph, and column-family).  
- **Azure Table Storage & Redis** are great for **fast key-value lookups**.  
- **Blob Storage & Data Lake** are used for **unstructured data**.  

---


