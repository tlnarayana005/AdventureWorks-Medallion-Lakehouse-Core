# AdventureWorks-Medallion-Lakehouse-Core

An enterprise-grade Modern Data Lakehouse platform built on Microsoft Azure, implementing an end-to-end **Medallion Architecture (Bronze → Silver → Gold)** to transform raw enterprise transactional data into strategic business intelligence and analytics assets.

---

## 🏛 Architecture & Tech Stack

A cloud-native, scalable modern data stack:

- **Ingestion & Orchestration**: **Azure Data Factory (ADF)** handles automated, parameter-driven ELT pipelines, coordinating reliable data movement into the Lakehouse.
- **Medallion Data Lakehouse (Azure Data Lake Storage Gen2)**:
  - **Bronze Layer**: Raw, immutable data ingestion preserving source fidelity.
  - **Silver Layer**: Curated, cleansed, enriched, and schema-enforced data via **Azure Databricks (Apache Spark / PySpark)**.
  - **Gold Layer**: Optimized dimensional models and serving views powered by **Azure Synapse Analytics**.
- **Distributed Processing**: Scalable **PySpark** notebooks for transformation, type casting, validation, and performance optimization.
- **Data Serving & Warehousing**: High-performance analytical queries using **Synapse Serverless SQL Pools** and external views.
- **Business Intelligence**: Rich reporting and executive-level analytics connected through **Power BI**.

---

## 📁 Repository Structure

```text
├── Data/                             # AdventureWorks source datasets
│   ├── AdventureWorks_Calendar.csv
│   ├── AdventureWorks_Customers.csv
│   ├── AdventureWorks_Product_Categories.csv
│   ├── AdventureWorks_Product_Subcategories.csv
│   ├── AdventureWorks_Products.csv
│   ├── AdventureWorks_Returns.csv
│   ├── AdventureWorks_Sales_2015.csv
│   ├── AdventureWorks_Sales_2016.csv
│   ├── AdventureWorks_Sales_2017.csv
│   └── AdventureWorks_Territories.csv
├── Transformation & Serving/         # Lakehouse processing code
│   ├── silver_layer_refer.ipynb      # PySpark medallion transformations
│   ├── Create Views Gold.sql         # Synapse SQL Gold layer views
│   └── git.json                      # ADF parameter mapping configuration
└── README.md
```

---

## 🚀 Getting Started

1. **Ingest to Bronze**: Use the ADF pipelines parameterized with `Transformation & Serving/git.json` to pull source CSV files into ADLS Gen2 raw storage.
2. **Transform to Silver**: Run `Transformation & Serving/silver_layer_refer.ipynb` in Databricks to clean, transform, and store Delta tables.
3. **Serve to Gold**: Execute `Transformation & Serving/Create Views Gold.sql` on Azure Synapse Serverless SQL Pool to create high-speed analytical views for Power BI.


