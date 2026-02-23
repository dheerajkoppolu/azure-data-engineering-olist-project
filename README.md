# Azure Data Engineering – Olist Medallion Project

## 📌 Overview
This project implements a complete end-to-end Azure Data Engineering pipeline using Medallion Architecture (Bronze, Silver, Gold).

## 🏗 Architecture
Data Sources → Azure Data Factory → ADLS Gen2 (Bronze)  
Transformation → Silver Layer  
Business Aggregation → Gold Layer  
Synapse Serverless SQL → Power BI

## ⚙️ Tech Stack
- Azure Data Factory (Orchestration)
- Azure Data Lake Gen2 (Storage)
- Azure Synapse Analytics (Serverless SQL)
- Parquet Format
- GitHub (Version Control)

## 🧱 Data Layers
### Bronze
Raw ingestion from:
- GitHub (HTTP datasets)
- Azure SQL tables

### Silver
- Schema standardization
- Data cleaning
- Deduplication

### Gold
- Aggregated business metrics
- Reporting-ready tables

## 🚀 Deployment
Synapse artifacts are version-controlled using GitHub integration.  
Publish branch generates ARM templates for CI/CD deployment.

## Architecture Diagram

![Architecture](docs/Architecture.png)
