# azure-lakehouse-project

ruth kumar <ruthkmr27@gmail.com>
6:11 PM (28 minutes ago)
to me

# Azure Data Lakehouse Project (Bronze → Silver → Gold)

## 📌 Project Overview
This project demonstrates a modern Azure Data Engineering pipeline using:
- Azure Data Lake Gen2
- Azure Synapse Analytics
- PySpark
- Delta Lake
- Medallion Architecture (Bronze, Silver, Gold)

---

## 📂 Project Structure

azure-lakehouse-project/
│
├── notebooks/
│ ├── NB_BronzeToSilver.ipynb
│ ├── NB_SilverToGold.ipynb
│ ├── NB_Gold_DimModel.ipynb
│
├── screenshots/
│ ├── bronze_folder.png
│ ├── silver_folder.png
│ ├── gold_folder.png
│ ├── synapse_workspace.png
│ ├── spark_pool.png
│
└── README.md

## 🧱 Medallion Architecture

### Bronze Layer
- Raw data ingestion (CSV)
- No transformations applied

### Silver Layer
- Cleaned, deduplicated data
- Column renaming + type standardization
- Stored as Delta

### Gold Layer
- Business-ready dimensional model
- Derived metrics (BMI, height class, etc.)
- Stored as Delta tables
