# QNB-Sentinel-AI-Driven-SME-Portfolio-Risk-Analytics
Developed an end-to-end SME risk engine for QNB using ADF-style ETL and SQL-based modeling. The system automates credit scoring by analyzing 10,000+ transactions via Python, applying AI anomaly detection to flag fraud. It transforms raw data into a 4-tier Power BI dashboard, enabling proactive, data-led financial decisions.

## 📌 Project Overview

Developed an **end-to-end risk scoring engine and intelligence suite** for SME portfolio analysis.

- Integrated synthetic transaction ledgers with behavioral scoring models  
- Automated loan decision support  
- Identified financial anomalies in SME transactions  
- Transformed raw data into **actionable credit insights**  

---

## ⚠️ Business Problems

- **Manual Decision Bottlenecks:** SME credit reviews take weeks  
- **High Liquidity Risk:** Difficulty identifying "Technical Default" cases  
- **Limited Visibility:** Lack of drill-down into transaction-level behavior  
- **Fraud Vulnerability:** Failure to detect anomalous transaction patterns  

---

## 🎯 Project Objectives

- **Automate Risk Tiering:** Categorized **500+ SMEs** into:
  - Green  
  - Amber  
  - Red  
  - Maroon  

- **Early Warning Signals (EWS):** Detect declining financial health  
- **Transaction Monitoring:** Analyze **10,000+ transactions**  
- **Executive Reporting:** Align dashboards with enterprise standards  

---

## 📊 Data Source

Synthetic dataset generated using Python to simulate real banking systems:

- **SME Profiles:**
  - 500 entities  
  - Attributes: Industry, Establishment Date, Legal Status  

- **Transaction Ledgers:**
  - 10,000+ records  
  - Credits (Inflows), Debits (Outflows), Status  

- **Domain Realism:**
  - Qatari sectors (Construction, Energy, Tourism)  
  - Currency: QAR  

---

## 🏗️ Architecture & Data Modeling

Designed using **Star Schema Architecture**:

- **Fact Table:**  
  - `Fact_SME_Transactions`  

- **Dimension Table:**  
  - `Dim_SME_Master`  

- **Relationship:**  
  - One-to-Many (`1:∞`) via `BusinessID`  

---

## ⚙️ ETL & Data Ingestion

### 1. Extraction
- Python scripts extract SME profiles and transaction data  

---

### 2. Transformation

- **Data Cleaning:**
  - Resolved naming conflicts  
  - Ensured data integrity  

- **Scoring Logic:**
  - Calculated `Final_Risk_Score`  
  - Based on:
    - Cash-flow stability  
    - Payment success rate  

---

### 3. Loading
- Processed data loaded into Power BI (**Gold Layer**)  

---

## ✅ Data Quality & Business Rules

### Data Quality

- **Primary Key Enforcement:** `BusinessID` ensures uniqueness  
- **Range Validation:** Controlled realistic transaction limits  

---

### Business Rules

- **Failure Penalty:**  
  - Failure rate **> 10%** → Not eligible for *Green*  

- **Liquidity Rule:**  
  - Outflows > Inflows for **3 consecutive months** → *Red Flag*  

---

## 🖥️ Power BI Dashboard Analysis

### Executive SME Risk & Portfolio Overview

- **Purpose:** 30-second executive summary  
- **Key Visuals:**
  - Risk Donut Chart  
  - Sector Heatmap  

- **Insights:**
  - Exposure to **Maroon (Critical)** risk clients  
  - Sector-level financial health  

---

### Transactional Failure & Anomaly Deep-Dive

- **Purpose:** Investigation tool for Risk & Fraud teams  

- **Key Visuals:**
  - AI Anomaly Scatter Plot  
  - Cash Flow Trend Lines  

- **Insights:**
  - Detects anomalous transactions  
  - Enables **Root Cause Analysis**  
  - Flags fraud risks and early default signals  

---

## 🚀 Strategic Outcome

- Accelerated loan decision-making  
- Reduced manual intervention  
- Improved fraud detection capability  
- Enabled scalable risk analytics framework  

By combining **Python-based analytics** with **Power BI visualization**, this solution delivers a modern **FinTech risk intelligence system** for SME portfolio management.

---

## 📁 Project Structure

```text
project-root/
│
├── data/                # Synthetic SME datasets
├── notebooks/           # Python scripts & analysis
├── pipelines/           # Data processing workflows
├── dashboards/          # Power BI reports (.pbix)
├── images/              # Dashboard screenshots
└── README.md            # Project documentation
