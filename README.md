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
