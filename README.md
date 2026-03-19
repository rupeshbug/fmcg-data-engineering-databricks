## Atlikon Unified Data Platform

### 🧩 Problem Statement

Atlikon, a global sporting equipment manufacturer, recently acquired Sports Bar—a fast-growing startup in the athletic nutrition space. While Atlikon operates on structured, ERP-driven systems, Sports Bar’s data is fragmented across spreadsheets, cloud storage, and informal exports.

Post-acquisition, this led to critical data challenges:

* **Schema mismatches** between structured and semi-structured data
* **Inconsistent and conflicting business metrics** across systems
* **Missing historical data** due to rapid startup growth
* **Misaligned reporting cycles** across both organizations

These issues created a major bottleneck in building unified capabilities for **supply chain, forecasting, and inventory planning**.

---

### 🎯 Project Goal

The goal of this project is to design and implement a **scalable, reliable data platform** that unifies heterogeneous data from both organizations into a **single source of truth**.

In this project, the parent company’s ERP data is already structured and analytics-ready, while the acquired startup’s data is fragmented and inconsistent. A **Medallion Architecture** is used where startup data undergoes full **Bronze → Silver → Gold** transformation, while the parent data requires minimal standardization. Both datasets are unified in the Gold layer to create a consistent data model for downstream analytics.

#### Key Objectives

* Enable **consistent and accurate analytics** across both companies
* Build a **low-complexity, maintainable data pipeline**
* Design a **scalable architecture** that supports future growth and acquisitions

The solution leverages the **Medallion Architecture (Bronze → Silver → Gold)** to progressively refine raw data into business-ready insights.

---

### 🛠️ Tech Stack

* **Databricks** – Unified data platform for processing and analytics
* **Python (PySpark)** – Data transformation and pipeline development
* **SQL** – Data querying and transformations
* **Amazon S3** – Scalable data lake storage for raw data ingestion
* **Medallion Architecture** – Layered data engineering design

---

### 🏗️ Architecture Overview

#### 🟤 Bronze Layer (Raw Data Ingestion)

* Ingest raw data from multiple sources:

  * ERP systems (Atlikon)
  * Spreadsheets & exports (Sports Bar)
* Preserve data in its original form for **traceability and auditing**

---

#### ⚪ Silver Layer (Data Cleaning & Standardization)

* Resolve schema mismatches across systems
* Standardize:

  * Column names
  * Data types
  * Business entities (e.g., products, customers)
* Handle missing values and deduplicate records
* Apply data validation and cleaning logic

---

#### 🟡 Gold Layer (Business-Ready Data)

* Build **aggregated datasets and KPIs**
* Provide a **single source of truth** for:

  * Sales performance
  * Inventory insights
  * Forecasting inputs

---

### Pipeline Orchestration

The data pipeline is orchestrated using **Databricks Jobs**, where each layer is executed as a separate task:

* Bronze Ingestion → Raw data ingestion from multiple sources
* Silver Transformation → Data cleaning and standardization
* Gold Aggregation → Business-level metrics and reporting datasets

Task dependencies are defined to ensure a sequential flow:

```text
Bronze → Silver → Gold
```

This enables reliable, repeatable, and automated pipeline execution.

---

### 📈 Outcome

This project delivers a unified and scalable data foundation that enables:

* Reliable cross-company reporting
* Consistent and trusted business metrics
* A unified data model across both organizations
* A future-ready architecture for scaling and new acquisitions

---

### Key Challenges & Solutions

#### 1. Schema Mismatch

Structured ERP data vs fragmented startup data with inconsistent column names and schemas across similar entities.
→ Resolved through schema standardization and column alignment in the **Silver layer**

---

#### 2. Inconsistent Metrics

Conflicting definitions of sales and KPIs across systems
→ Established centralized KPI definitions in the **Gold layer**

---

#### 3. Missing Data

Incomplete historical records due to rapid startup growth
→ Preserved raw data in Bronze and handled nulls systematically during transformation

---

#### 4. Misaligned Reporting Cycles

Different reporting granularities (daily vs monthly)
→ Standardized time formats and built flexible aggregations

---

#### 5. Scalability

Need to support long-term growth and future integrations
→ Designed using **Medallion Architecture with Databricks + S3**

---

### 🔮 Future Enhancements

* Implement demand forecasting using machine learning
* Add data quality monitoring and alerting layer
* Introduce incremental data processing using Change Data Feed
* Extend pipeline to support real-time data ingestion

---
