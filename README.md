# QNB-Sentinel-AI-Driven-SME-Portfolio-Risk-Analytics
Developed an end-to-end SME risk engine for QNB using ADF-style ETL and SQL-based modeling. The system automates credit scoring by analyzing 10,000+ transactions via Python, applying AI anomaly detection to flag fraud. It transforms raw data into a 4-tier Power BI dashboard, enabling proactive, data-led financial decisions.

---

## 📌 Project Overview

QNB-Sentinel is an **end-to-end credit risk intelligence system** designed to support:

- Automated loan decisioning  
- Proactive SME portfolio monitoring  

The system integrates:

- **Azure Data Factory (ADF)** for orchestration  
- **SQL Server Star Schema** for structured storage  
- **Python-based risk scoring engine** for analytics  

This enables the transition from **manual reviews → real-time AI-driven risk management**.

---

## 🔗 View Live Demo

👉 **[View Power BI Dashboard](https://app.powerbi.com/)**  
> *(Replace with your actual Power BI report link)*

---

## Business Problem

QNB faces key challenges in SME lending:

- **Operational Inefficiency:** Manual credit assessments take **5–10 days**  
- **Hidden Liquidity Crises:** Difficulty detecting *Technical Defaults*  
- **Data Silos:** Disconnected customer and transaction datasets  
- **Fraud Risk:** Hard to detect anomalies across high-volume transactions  

---

## Project Objectives

- Build a **WIMS-style automated risk analytics system**  
- Design a **high-performance SQL Star Schema** (10,000+ records)  
- Develop an **ADF-based ETL pipeline**  
- Implement **Python-based behavioral risk scoring**  
- Deliver insights via **Power BI dashboards**  

---

## Data Sources

Synthetic datasets designed to mimic real banking systems:

- **SME Master Data (`Dim_SME_Master`):**
  - Industry, Location, Legal Status, Years in Business  

- **Transaction Ledgers (`Fact_SME_Transactions`):**
  - 10,000+ daily records  
  - Credits, Debits, Status (Completed/Failed)  

- **Risk Layer:**
  - Derived outputs from scoring engine  
  - Cash-flow stability and risk indicators  

---

## Architecture & Data Modeling

Built using **Star Schema Architecture**:

- **Database:** SQL Server  
- **Orchestration:** Azure Data Factory  
- **Relationship:** One-to-Many (`1:N`) via `BusinessID`  

**Modeling Logic:**
- Transaction-level data (**Fact**) drives  
- Risk status of SME entities (**Dimension**)  

---

## ⚙️ ETL & Data Ingestion (ADF Pipeline)

### 1. Ingestion
- ADF **Copy Activity** loads raw data into staging tables  

---

### 2. Scoring
- ADF triggers Python scripts to compute:
  - `Final_Risk_Score`  
  - Based on:
    - Cash-flow volatility  
    - Transaction failure rates  

---

### 3. Validation
- SQL Stored Procedures:
  - Enforce referential integrity  
  - Detect orphan records  

---

### 4. Refresh
- ADF triggers Power BI API  
- Dashboards update with latest risk tiers  

---

## ✅ Data Quality & Business Rules

### Quality Controls

- **Primary/Foreign Key Enforcement:** Ensures relational consistency  
- **Constraint Validation:** Non-negative transactions, valid QAR format  
- **Deduplication:** Prevents duplicate transaction IDs  

---

### Business Rules

- **Failure Penalty:**  
  - Failure rate **> 10%** → Risk downgrade  

- **Liquidity Rule:**  
  - Negative cash flow over **90 days** → *Maroon (Extreme Risk)*  

- **Automation Rule:**  
  - Score **≥ 70** → Fast-track loan approval  

---

## 📈 Power BI Dashboard

### Page 1 – Executive SME Risk Overview

- **Audience:** CRO, Senior Leadership  
- **Purpose:** Portfolio monitoring  

**Key Visuals:**
- Risk Tier Donut (Green / Amber / Red / Maroon)  
- Industry Heatmap  
- Approval Funnel  

---

### Page 2 – Transactional Failure & Anomaly Analysis

- **Audience:** Risk Analysts, Fraud Team  
- **Purpose:** Root-cause analysis & fraud detection  

**Key Visuals:**
- AI Anomaly Scatter Plot  
- Inflow vs Outflow Time Series  
- SME Watchlist  

---

## 🛠️ Tools & Technologies

- **Azure Data Factory (ADF):** Pipeline orchestration  
- **SQL Server:** Star schema & relational modeling  
- **Python (Pandas, NumPy):** Risk scoring engine  
- **Power BI:** Visualization, DAX, anomaly detection  

---

## Role & Scope

**Role:** Data & Risk Analytics Consultant  

### Key Contributions

- Designed **enterprise ETL pipeline (ADF-style)**  
- Built **SQL Star Schema architecture**  
- Developed **Python-based risk scoring models**  
- Translated complex transaction data into **executive insights**  

---

## 📁 Project Structure

```text
project-root/
│
├── data/                # Synthetic SME datasets
├── notebooks/           # Python analysis & scoring scripts
├── pipelines/           # ADF pipeline definitions
├── dashboards/          # Power BI reports (.pbix)
├── images/              # Dashboard screenshots
└── README.md            # Project documentation
