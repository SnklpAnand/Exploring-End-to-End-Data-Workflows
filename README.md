📌 Overview

This project demonstrates a complete end-to-end data platform built using Microsoft Fabric, covering data ingestion, transformation, storage, modeling, and analytics.
The goal was to simulate a real-world enterprise data workflow using modern lakehouse architecture and Fabric-native tools.

<img width="827" height="913" alt="1 2 - Sankalp Fabric Workspace" src="https://github.com/user-attachments/assets/8355c1e2-7cb8-4c38-8817-592ab0fc7da4" />



## 🏗️ Architecture Overview

<img width="586" height="358" alt="1 1 - Fabric Architecture" src="https://github.com/user-attachments/assets/75845de2-0d02-4c71-b83a-a68e7d67d702" />


### Flow:
Data Sources → Data Factory → OneLake → Lakehouse → Transformation → Warehouse → Power BI

---

## 🔧 Key Components

### 1. Data Ingestion
- Fabric Data Factory pipelines
- Sources:
  - GitHub API (CSV files)
  - Azure Data Lake Storage Gen2
- Dynamic pipelines using:
  - Lookup Activity
  - ForEach Activity

---

### 2. Data Storage
- OneLake (central storage)
- Lakehouse:
  - Files (raw data)
  - Tables (processed data)

---

### 3. Data Transformation

#### Data Flow Gen2
- Join datasets
- Filter and clean data
- Create derived columns

<img width="1522" height="473" alt="1 1 - Data Flow Gen 2" src="https://github.com/user-attachments/assets/ed8e057c-dad9-4c53-873a-c7846cdf057f" />


#### PySpark Notebooks
- Data ingestion using Spark
- Column transformations
- Dataset union and processing

---

### 4. Medallion Architecture

<img width="1128" height="432" alt="1 2 - Medallion Architecture" src="https://github.com/user-attachments/assets/e40707cc-65bc-45dd-a0d4-f98b17f94cbb" />


- Bronze → Raw data
- Silver → Cleaned data
- Gold → Business-ready data

---

### 5. Data Warehouse (Gold Layer)

- Schema-based modeling
- Fact and Dimension tables
- CTAS (Create Table As Select)

---

### 6. Data Modeling

- Star Schema implementation
- Fact table: sales
- Dimension tables:
  - customers
  - products
  - calendar

- Slowly Changing Dimensions (Type 1 & Type 2)

---

### 7. Automation & Orchestration

- Parent Pipeline
- Trigger-based execution
- Dependency handling

---

### 8. Monitoring & Alerting

- Pipeline monitoring dashboard
- Email alerts on failure

---

### 9. CI/CD Deployment

- Fabric Deployment Pipeline
- Dev → Test → Production workflow

---

### 10. Data Science

- AutoML model training
- Data Wrangler for transformations

---

### 11. Data Governance

- Lineage tracking
- Dataset endorsement

---

### 12. Performance Optimization

- Delta format
- OPTIMIZE (file compaction)
- VACUUM (cleanup)

---

## ⚡ Data Access Modes

| Mode | Description |
|------|------------|
| Import | Loads full data into memory |
| Direct Query | Queries source in real-time |
| Direct Lake | Reads data directly from Delta Lake |

---

## 📊 Key Learnings

- Built scalable data pipelines using Fabric Data Factory
- Implemented metadata-driven pipeline design
- Designed lakehouse-based architecture using the Medallion model
- Applied dimensional modeling for analytics
- Optimized data storage and query performance

---

## 🧠 Challenges Faced

- Managing multiple data sources
- Designing dynamic pipelines without hardcoding
- Understanding Direct Lake vs Direct Query behavior

---

## 📌 Conclusion

This project demonstrates how Microsoft Fabric simplifies modern data architecture by unifying data engineering, warehousing, and analytics into a single platform.


