# Azure_DE_Project_2

# 🚀 Azure Data Engineering Project: End-to-End ETL Pipeline

This project showcases a modern end-to-end Data Engineering pipeline built on Microsoft Azure, designed to ingest, transform, and serve data for analysis and reporting. The architecture follows the **Medallion Architecture** (Bronze → Silver → Gold) model, implementing real-world data engineering concepts using the Azure ecosystem.

---

### 📌 Project Objective

To build a scalable, secure, and efficient data pipeline that:

- Ingests data from external sources.  
- Transforms and cleans the data using PySpark.  
- Stores data in structured formats using Delta Lake.  
- Enables rich visualizations for analytics and reporting.  

---
![image alt](https://github.com/ChetanDaharwal/Azure_DE_project_2/blob/e045fd0911f1c998b856c93c0f83cb1503269748/1748729843590.jpeg)

### 🧱 Architecture Overview

      [External API Source]
              |
      Azure Data Factory (Validation + Ingestion)
              |
    Azure Data Lake Storage Gen2 (Raw File Container)
    ┌─────────────┬─────────────┬─────────────┐
    [Bronze Layer] [Silver Layer] [Gold Layer]
              |
     Azure Databricks (Auto Loader + PySpark)
              |
    Delta Live Tables + Unity Catalog (Governance)
              |
    Azure Synapse Analytics (External Tables + Views)
              |
        Power BI Dashboard (Visual Insights)


---

### 🔧 Tools & Technologies

| Tool                     | Purpose                                         |
|--------------------------|-------------------------------------------------|
| **Azure Data Factory**   | Data ingestion, pipeline orchestration          |
| **Azure Data Lake Gen2** | Scalable, secure cloud-based storage            |
| **Azure Databricks**     | Data transformation with PySpark & Auto Loader |
| **Delta Lake**           | ACID-compliant data storage                     |
| **Unity Catalog**        | Centralized governance and metadata management |
| **Delta Live Table**     | implementing delta live table on top od deltalake |

---

## 🗂️ Project Breakdown

### 1️⃣ Data Ingestion (Bronze Layer)

- **Validation activity** in ADF ensures pipeline only runs when new files are dropped into the raw container.  
- Used **ADF** to pull Netflix metadata (cast, category, countries, directors) from an HTTP API and SQL source.  
- Data was streamed into **Bronze Layer** using **Databricks Auto Loader** with checkpointing to prevent duplication.  

### 2️⃣ Data Transformation (Silver Layer)

- Parameterized **Databricks notebooks** triggered through **ForEach activity** in Data Bricks for scalable notebook execution.  
- Data copied from Bronze to Silver using Auto Loader and written in Delta format.  
- Applied **PySpark transformations**, cleaned datasets and managed schema evolution.  

### 3️⃣ Gold Delta Table (Gold Layer)

- Built **Delta Live Tables (DLT)** on top of Silver Layer for structured, query-optimized data.  
- Unity Catalog used at **administrator level** to manage and govern data assets centrally.   

---

### 💡 Key Learnings

- Mastered Medallion Architecture implementation using Azure-native tools.  
- Leveraged **checkpointing and Auto Loader** to implement **real-time streaming** with deduplication.  
- Implemented **parameterized notebooks** and **loop-driven automation** for modular ETL design.  
- Managed secure service-to-service connections using **Microsoft Entra ID** (App ID, Secret, Tenant ID).  
- Built **Unity Catalog-based governance** for better control over metadata and lineage.  
- Used **Delta Live Tables** for efficient and reliable gold layer modeling.   

---

### 📸 Project Demo & References

- [Azure Data Factory Documentation](https://learn.microsoft.com/en-us/azure/data-factory/)  
- [Azure Databricks Quickstart](https://learn.microsoft.com/en-us/azure/databricks/)  
- [Delta Lake Guide](https://delta.io/)  
- [Unity Catalog Overview](https://learn.microsoft.com/en-us/azure/databricks/data-governance/unity-catalog/)  
- [Synapse Analytics Overview](https://learn.microsoft.com/en-us/azure/synapse-analytics/)  

---


        
