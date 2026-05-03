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

#### PySpark Notebooks
- Data ingestion using Spark
- Column transformations
- Dataset union and processing

---

### 4. Medallion Architecture

![Medallion](architecture/medallion-architecture.png)

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
- Designed lakehouse-based architecture using Medallion model
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

---

## 🔗 Future Enhancements

- Power BI dashboard integration
- Advanced ML model deployment
- Real-time streaming pipeline
