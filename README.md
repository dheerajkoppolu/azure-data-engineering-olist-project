# Azure Data Engineering – Olist Medallion Architecture Project

## 📌 Project Overview

This project implements an end-to-end Azure Data Engineering pipeline using Medallion Architecture (Bronze, Silver, Gold).

The pipeline ingests data from multiple sources, processes it using Apache Spark in Azure Databricks, and serves curated business-ready datasets through Azure Synapse Serverless SQL for reporting in Power BI.

---

## 🏗 Architecture

### Data Flow

Data Sources  
→ Azure Data Factory (Orchestration & Ingestion)  
→ ADLS Gen2 Bronze (Raw Layer)  
→ Azure Databricks (Transformation)  
→ ADLS Gen2 Silver (Cleaned Layer)  
→ Azure Databricks (Aggregation)  
→ ADLS Gen2 Gold (Business Layer)  
→ Azure Synapse Serverless SQL  
→ Power BI  

---

## 🧱 Medallion Architecture

### 🥉 Bronze Layer (Raw)

- Ingested using Azure Data Factory
- Sources:
  - GitHub (HTTP datasets)
  - Azure SQL Tables
- Stored as Parquet files in ADLS Gen2
- Raw, immutable data

---

### 🥈 Silver Layer (Cleaned)

Processed using Azure Databricks (Apache Spark):

- Schema standardization
- Data cleansing
- Deduplication
- Null handling
- Data type corrections

Output stored in ADLS Gen2 as Parquet.

---

### 🥇 Gold Layer (Business Ready)

Aggregated datasets for reporting:

- Business metrics
- Fact-style reporting tables
- Optimized for analytics queries

Stored in ADLS Gen2 (Parquet).

---

## ⚙️ Technologies Used

- Azure Data Factory (ADF)
- Azure Data Lake Storage Gen2 (ADLS)
- Azure Databricks (Apache Spark)
- Azure Synapse Analytics (Serverless SQL)
- Power BI
- GitHub (Version Control)

---

## 🔄 Orchestration Strategy

Azure Data Factory handles:

- HTTP ingestion from GitHub
- SQL table extraction
- Landing data into Bronze layer
- Triggering transformation workflows

---

## 🔍 Transformation Strategy

Azure Databricks notebooks:

- Bronze → Silver transformation
- Silver → Gold aggregation
- Parquet-based storage
- Spark-based distributed processing

---

## 📊 Data Serving

Azure Synapse Serverless SQL:

- Queries Gold layer directly from ADLS
- Uses OPENROWSET with Parquet format
- Provides analytics layer for BI tools

Power BI connects to Synapse for reporting.

---

## 🔐 Security & Access Control

- ADLS RBAC configuration
- Managed Identity access for Synapse
- Folder-level ACL permissions

---

## 🚀 CI/CD & Version Control

- Synapse and ADF integrated with GitHub
- Collaboration branch: `main`
- Publish branches:
  - `workspace_publish` (Synapse)
  - `adf_publish` (ADF)
- ARM templates generated for deployment

---

## 📂 Repository Structure
azure-data-engineering-olist-project/
│
├── synapse/
├── adf/
├── databricks/
│ └── notebooks/
├── docs/
│ └── architecture.png
├── .gitignore
└── README.md



---

## 📈 Future Improvements

- Convert Parquet to Delta Lake
- Implement partitioning strategy
- Add CI/CD pipeline using GitHub Actions
- Introduce monitoring and logging framework

---

## 👤 Author

Azure Data Engineering Portfolio Project  
Medallion Architecture Implementation

## 🖼 Architecture Diagram

![Architecture Diagram](docs/Architecture.png)
