# 🛒 Olist E-Commerce Sales & Delivery Performance Analysis
### An End-to-End Data Analytics Case Study & Executive BI Suite

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Cleaning-150458?logo=pandas)
![Power BI](https://img.shields.io/badge/Power_BI-Executive_Dashboard-yellow?logo=powerbi)
![DAX](https://img.shields.io/badge/DAX-Custom_Measures-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Project Overview
This project is an end-to-end data analytics case study examining **~110,000 real, anonymized e-commerce orders** from **Olist**, the largest online marketplace in Brazil. 

The objective of this project is to simulate the complete analytics lifecycle of a Business Intelligence Analyst:
1. **Data Engineering & Preparation:** Extracting, merging, and cleaning relational datasets in **Python (Pandas)**.
2. **Exploratory Data Analysis (EDA):** Uncovering sales trends, regional concentration, and shipping behavior in **Jupyter Notebook**.
3. **Executive Dashboard Design:** Building an interactive, two-page enterprise reporting cockpit in **Power BI Desktop** using custom **DAX measures**, container-based layouts, and smooth sidebar navigation.

---

## 📊 Executive Power BI Dashboard

The interactive report is structured into two synchronized analytical views:

### Page 1: Executive Performance Overview
*Tracks macro financial performance, product category mix, regional revenue concentration, and customer satisfaction correlations.*

![Executive Performance Overview](dashboard/executive_summary.png)

### Page 2: Logistics & Delivery Deep-Dive
*Diagnoses state-level logistics bottlenecks, shipping duration distributions, on-time delivery rates, and review score ratings.*

![Logistics & Delivery Deep-Dive](dashboard/logistics_deep_dive.png)

---

## 🎯 Key Business Questions Addressed
* **Revenue Drivers:** What drives marketplace revenue, and how seasonal are sales trends across the 2-year timeline?
* **Product Catalog Strategy:** Is revenue concentrated in a single "hero" category, or is the product mix well-diversified?
* **Geographic Distribution:** Which Brazilian states generate the bulk of marketplace activity, and where are the growth opportunities?
* **Logistics vs. Customer Satisfaction:** What is the quantifiable impact of delivery delays on customer review scores?

---

## 🛠️ Technology Stack & Tools

| Layer | Tool / Technology | Purpose |
| :--- | :--- | :--- |
| **Data Processing** | Python (`pandas`, `numpy`) | Data type parsing, relational table merges, feature engineering |
| **Exploratory Analysis** | `matplotlib`, `seaborn`, Jupyter Notebook | Statistical distributions, time-series plotting, and data validation |
| **Data Storage / Export** | Microsoft Excel (`.xlsx`), CSV | Intermediate analysis-ready dataset for downstream BI ingestion |
| **Business Intelligence** | Microsoft Power BI Desktop | Interactive 2-page report, DAX modeling, custom UI/UX design |
| **Version Control** | Git & GitHub | Project version control and documentation hosting |

---

## 🔄 End-to-End Analytics Workflow

```text
[Kaggle Raw CSVs] (9 relational tables)
       │
       ▼
[Python / Pandas] (Data Cleaning & Feature Engineering)
       │  • Merged 7 core tables on relational IDs
       │  • Filtered strictly to 'delivered' orders (110,197 rows)
       │  • Engineered: 'delivery_days' and 'late_delivery' flags
       │  • Cleaned product category Portuguese translations
       ▼
[olist_cleaned_for_dashboard.xlsx] (Exported Master Dataset)
       │
       ▼
[Power BI Modeling & DAX]
       │  • Built 5 core KPI measures & calculated columns
       │  • Configured interactive cross-filtering & custom tooltips
       ▼
[2-Page Executive Dashboard] (Executive Summary + Logistics Deep-Dive)
