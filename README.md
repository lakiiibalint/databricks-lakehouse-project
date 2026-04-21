# 🚀 End-to-End Data Lakehouse on Databricks

This project demonstrates how to build a **production-style Data Lakehouse** from scratch using **Databricks** free edition and the **Medallion Architecture (Bronze → Silver → Gold)**.

It covers the full lifecycle of modern data engineering:
- Data ingestion  
- Data cleaning & transformation  
- Data modeling  
- Pipeline orchestration  

---

## 📌 Project Overview

- 🧱 Architecture: Medallion (Bronze, Silver, Gold)
- ⚙️ Platform: **Databricks (Unity Catalog + Delta Lake)**
- 🐍 Language: Python (PySpark) + SQL
- 📦 Storage: Delta Tables
- 🔄 Orchestration: Databricks Jobs 

---

## 🧠 Inspiration

This project is **independently implemented by me**, inspired by a learning concept from **[Baraa](https://github.com/DataWithBaraa)**.

--- 

## 🏗️ Layers

Raw CSV Files  
↓  
🥉 Bronze Layer (Raw Ingestion)  
↓  
🥈 Silver Layer (Cleaned & Standardized)  
↓  
🥇 Gold Layer (Business-ready Data Model)  
↓  
📊 Analytics / BI Ready

## 🥉 Bronze Layer

**Goal:** Ingest raw data without transformations

- Load CSV files into Delta tables
- Preserve raw structure
- Add source-based naming (e.g. `crm_`, `erp_`)

✔ No transformations  
✔ Raw, auditable data  

---

## 🥈 Silver Layer

**Goal:** Clean, validate, and standardize data

### Key transformations:
- Remove duplicates
- Fix null values
- Standardize formats (dates, strings)
- Trim whitespace
- Normalize business keys
- Validate numeric fields
- Rename columns for clarity

✔ Data quality improved  
✔ Consistent schema  
✔ Ready for joins  

---

## 🥇 Gold Layer

**Goal:** Build a **business-ready data model**

### Approach:
- Dimensional modeling (Star Schema)
- Create:
  - `dim_*` tables (dimensions)
  - `fact_*` tables (facts)

### Example:
- `dim_customers`
- `dim_products`
- `fact_sales`

✔ Optimized for analytics  
✔ Easy to query  
✔ Business-friendly structure  

---

## 🔄 Pipeline Orchestration

The full pipeline is automated using **Databricks Jobs**.
