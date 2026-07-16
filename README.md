<div align="center">

# ☁️ Azure Data Engineering Projects

### Hands-on Azure Data Engineering Projects using Azure Data Factory, Azure SQL Database, Azure Data Lake Storage Gen2 & Azure Blob Storage

![Azure](https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![ADF](https://img.shields.io/badge/Azure%20Data%20Factory-FFB900?style=for-the-badge)
![Azure SQL](https://img.shields.io/badge/Azure%20SQL%20Database-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![ADLS](https://img.shields.io/badge/ADLS%20Gen2-0089D6?style=for-the-badge)
![SQL](https://img.shields.io/badge/SQL-025E8C?style=for-the-badge)

</div>

---

# 📖 Overview

This repository contains a collection of practical Azure Data Engineering projects completed during my learning journey. The projects focus on building end-to-end ETL pipelines using Microsoft Azure services.

The assignments include:

- Azure Storage configuration
- Azure SQL Database creation
- Azure Data Factory pipeline development
- Data ingestion from SQL Database to ADLS
- SQL JOIN operations
- Conditional pipeline execution
- CSV and JSON data generation
- Lookup and If Condition activities
- Storage management and recovery

These projects helped me understand how data is stored, transformed, and moved across Azure services in real-world data engineering workflows.

---

# 📚 Table of Contents

- Project Architecture
- Technologies Used
- Assignment 1 – Azure Storage
- Assignment 2 – Azure SQL Database
- Assignment 3 – Azure Data Factory
- Assignment 4 – Azure Data Factory Pipelines
- Assignment 5 – Advanced Azure Data Factory Pipelines
- Azure Data Factory Activities Used
- SQL Concepts Used
- Repository Structure
- Learning Outcomes
- Future Improvements
- Screenshots
- Author

---

# 🏗 Project Architecture

```text
Azure SQL Database
        │
        ▼
Azure Data Factory
        │
        ▼
Lookup Activities
        │
        ▼
If Condition Activities
        │
        ▼
Copy Activity
        │
        ▼
Azure Data Lake Storage Gen2
        │
        ├── CSV
        ├── JSON
        ├── Address
        ├── CSV_Pipe
        └── CSV2
```

---

# 🚀 Technologies Used

- Microsoft Azure
- Azure Data Factory
- Azure SQL Database
- Azure Data Lake Storage Gen2
- Azure Blob Storage
- SQL
- JSON
- CSV

---

# 📦 Assignment 1 – Azure Storage

## Question 1 – Azure Data Lake Storage Gen2

### Implemented

- Created Azure Data Lake Storage Gen2 account
- Configured Soft Delete
- Created public container (**landing**)
- Created private container (**raw**)
- Created Practice-1 directory
- Uploaded files
- Deleted files
- Restored deleted files

### Concepts Learned

- ADLS Gen2
- Containers
- Directories
- Public vs Private Containers
- Soft Delete
- File Recovery

---

## Question 2 – Azure Blob Storage

### Implemented

- Created Azure Blob Storage account
- Enabled Blob Versioning
- Created landing container
- Uploaded blobs
- Uploaded blobs using virtual folders
- Tested folder deletion
- Verified folder behaviour after blob deletion

### Concepts Learned

- Blob Storage
- Blob Versioning
- Virtual Folders
- Blob Management

---

# 🗄 Assignment 2 – Azure SQL Database

### Implemented

- Created Azure SQL Server
- Created Azure SQL Database
- Loaded AdventureWorks Sample Database
- Connected SQL Database with Azure Data Factory

### Concepts Learned

- Azure SQL Server
- Azure SQL Database
- Sample Database
- Database Connectivity

---

# ⚙ Assignment 3 – Azure Data Factory

### Implemented

- Created Azure Data Factory
- Created Linked Services
- Created Datasets
- Connected SQL Database
- Connected ADLS Gen2
- Executed pipelines

### Concepts Learned

- Linked Services
- Datasets
- Pipelines
- Copy Activity

---

# 🔄 Assignment 4 – Azure Data Factory Pipelines

## Pipeline 1 – Copy_ProductTable_To_CSV

**Objective**

Copy Product table from Azure SQL Database to CSV.

**Destination**

```
landing/CSV
```

---

## Pipeline 2 – Copy_Customer_To_JSON

**Objective**

Copy Customer table into JSON format.

**Destination**

```
landing/JSON
```

---

## Pipeline 3 – Copy_Customer_JSON_To_Folder

**Objective**

Copy an existing file from one ADLS folder to another.

**Source**

```
landing/CSV
```

**Destination**

```
landing/CSV2
```

---

## Pipeline 4 – Copy_Customer_To_CSV_Pipe

**Objective**

Copy Customer table into CSV using Pipe (|) delimiter instead of comma (,).

**Destination**

```
landing/CSV_Pipe
```

---

# 🚀 Assignment 5 – Advanced Azure Data Factory Pipelines

## Pipeline 1 – Ingestion_Customer_SQLDB_ADLS

Copy Customer table into CSV.

---

## Pipeline 2 – Ingestion_Customer_SQLDB_ADLS_Folder

Copy Address table into

```
landing/Address
```

as CSV.

---

## Pipeline 3 – Ingestion_Customer_JOIN_ADLS

Join the following tables:

- SalesLT.Customer
- SalesLT.CustomerAddress
- SalesLT.Address

Generate a CSV containing customer names along with their addresses.

---

## Pipeline 4 – Ingestion_Product_To_JSON

### Workflow

```
Lookup Product Count
        │
        ▼
If Product Count > 10
        │
        ▼
Copy Product Table
        │
        ▼
Generate JSON
```

### SQL Used

```sql
SELECT COUNT(*) AS ProductCount
FROM SalesLT.Product;
```

```sql
SELECT *
FROM SalesLT.Product;
```

---

## Pipeline 5 – Ingestion_Product_Address_To_JSON

### Workflow

```
Lookup Product Count
        │
        ▼
If Product Count > 10
        │
        ▼
Copy Product JSON
        │
        ▼
Lookup Address Count
        │
        ▼
If Address Count > 100
        │
        ▼
Copy Address CSV
```

### SQL Used

```sql
SELECT COUNT(*) AS ProductCount
FROM SalesLT.Product;
```

```sql
SELECT *
FROM SalesLT.Product;
```

```sql
SELECT COUNT(*) AS AddressCount
FROM SalesLT.Address;
```

```sql
SELECT *
FROM SalesLT.Address;
```

---

# 🛠 Azure Data Factory Activities Used

- Copy Activity
- Lookup Activity
- If Condition
- Linked Services
- Datasets
- Mapping
- Pipeline Validation
- Debug
- Publish

---

# 💻 SQL Concepts Used

- SELECT
- COUNT()
- INNER JOIN
- Aliasing
- Conditional Queries
- SQL Query as Dataset Source



---

# 🎯 Learning Outcomes

Through these assignments, I gained practical experience in:

- Azure Storage Management
- Azure SQL Database
- Azure Data Factory
- Data Ingestion
- ETL Pipeline Design
- Lookup Activity
- If Condition Activity
- SQL JOIN Operations
- JSON Dataset Creation
- CSV Dataset Creation
- Conditional Data Movement
- Azure Storage Management

---

# 📷 Screenshots

You can find screenshots of each assignment inside their respective folders.

Example:

```
Assignment-ADF-1,2,3&4/
    └── Screenshots/

Assignment-5/
    └── Screenshots/
```

---

# 🚀 Future Improvements

- Parameterized Pipelines
- Dynamic File Names
- Incremental Loading
- Metadata-driven Pipelines
- Trigger-based Execution
- Logging
- Error Handling
- Monitoring

---

# 👨‍💻 Author

## Lokendra Khadka

Azure Data Engineering Enthusiast

This repository documents my practical learning journey in Azure Data Engineering using Microsoft Azure services, Azure Data Factory, Azure SQL Database, Azure Data Lake Storage Gen2, and Azure Blob Storage.

---
