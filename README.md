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
*Monitors macro revenue trends, category mix, regional concentration, and delivery impact on customer reviews.*

![Executive Performance Overview](Dashboard/Executive%20Summary.png)

### Page 2: Logistics & Delivery Deep-Dive
*Diagnoses state-level shipping bottlenecks, delivery duration distribution, and satisfaction drop-off.*

![Logistics & Delivery Deep-Dive](Dashboard/Logistics%20Deep-Dive.png)

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




💡 Key Business Insights
1. Revenue Dynamics & Black Friday Surge
Total Revenue: Reached R$ 13.22M across 96,096 unique delivered orders (110,197 order-item records) with an Average Order Value (AOV) of R$ 137.04.

Seasonality: Monthly revenue climbed steadily throughout 2017, achieving an all-time peak of R$ 987.8K in November 2017 driven by Black Friday demand, before stabilizing between R$ 850K–975K per month.

2. Balanced Product Catalog
The marketplace displays healthy catalog diversification without high reliance on any single category:

Health & Beauty: 9.3% of revenue (R$ 1.23M)

Watches & Gifts: 8.8% of revenue (R$ 1.17M)

Bed, Bath & Table: 7.7% of revenue (R$ 1.02M)

Sports & Leisure: 7.2% of revenue (R$ 0.95M)

Computers & Accessories: 6.7% of revenue (R$ 0.89M)

3. Southeast Geographic Concentration
São Paulo (SP) is the dominant hub, accounting for 38.3% of total revenue (R$ 5.07M).

SP, Rio de Janeiro (RJ), and Minas Gerais (MG) together generate over 63% of total sales, indicating heavy reliance on the Southeast corridor.

4. The Critical Delivery Gap (Standout Finding)
On-Time Deliveries: Average review score is 4.21 / 5.00.

Late Deliveries: Average review score collapses to 2.55 / 5.00 (a 1.66-star drop).

Business Takeaway: While only 8.1% of orders arrive late, each delayed shipment causes a disproportionate drop in customer satisfaction and brand trust.

🚀 Strategic Recommendations
Carrier SLA & Delivery Optimization (High Leverage):

High-delay states in the North and Northeast (e.g., Alagoas with a 23.9% late rate, Maranhão with 19.7%, and Roraima averaging 27.8 delivery days) require targeted fulfillment hubs or regional 3PL partnerships.

Regional Market Diversification:

Expand marketing and seller acquisition in underpenetrated states (e.g., Goiás, Espírito Santo, and Distrito Federal — each currently representing <2.5% of revenue) to reduce over-dependency on São Paulo.

Broad Catalog Curation:

Maintain wide promotional support across top product lines rather than over-investing in a single category.
[Power BI Modeling & DAX]
       │  • Built 5 core KPI measures & calculated columns
       │  • Configured interactive cross-filtering & custom tooltips
       ▼
[2-Page Executive Dashboard] (Executive Summary + Logistics Deep-Dive)



Metric Name,DAX Formula,Description
Total Revenue - SUM('olist_cleaned_for_dashboard'[price]) - Calculates gross sales from delivered orders.
Total Orders - DISTINCTCOUNT('olist_cleaned_for_dashboard'[order_id]) - Counts unique delivered orders.
Avg Order Value - "DIVIDE([Total Revenue], [Total Orders], 0)" - Computes average revenue per order.
Late Delivery Rate - "DIVIDE(CALCULATE(COUNTROWS('olist_cleaned_for_dashboard'), 'olist_cleaned_for_dashboard'[late_delivery] = TRUE), COUNTROWS('olist_cleaned_for_dashboard'), 0)" - Calculates the percentage of delayed deliveries.
Avg Review Score - AVERAGE('olist_cleaned_for_dashboard'[review_score]) - Computes average customer rating (1–5 scale).

(For the complete DAX documentation including helper columns, see DAX_Measures.md).


Ecommerce-Sales-Analysis/
├── .gitignore                         # Git ignore rules for Python & Power BI
├── LICENSE                            # MIT open-source license
├── requirements.txt                   # Python package dependencies
├── README.md                          # Project documentation and write-up
├── DAX_Measures.md                    # Detailed DAX formulas reference
├── Olist_Sales_Analysis.ipynb         # Jupyter Notebook (ETL & EDA pipeline)
├── olist_cleaned_for_dashboard.xlsx   # Cleaned master dataset for BI tools
├── dashboard/
│   ├── OLIST E-COMMERCE INTELLIGENCE.pbix  # Two-page Power BI dashboard
│   ├── executive_summary.png          # Page 1 high-resolution screenshot
│   └── logistics_deep_dive.png        # Page 2 high-resolution screenshot
└── docs/
    └── Olist_Project_Documentation.docx    # Full technical project write-up


⚙️ How to Reproduce This Project

1. Clone the Repository
git clone [https://github.com/Saro-07/Ecommerce-Sales-Analysis.git](https://github.com/Saro-07/Ecommerce-Sales-Analysis.git)
cd Ecommerce-Sales-Analysis

2. Set Up the Python Environment
pip install -r requirements.txt

3. Run the Data Pipeline
Open and run Olist_Sales_Analysis.ipynb in Jupyter Notebook or Google Colab.

The notebook merges the raw tables, performs cleaning and exploratory visualization, and exports olist_cleaned_for_dashboard.xlsx.

4. Open the Power BI Dashboard
Open dashboard/OLIST E-COMMERCE INTELLIGENCE.pbix in Microsoft Power BI Desktop.

If prompted to update data source paths, point to your local copy of olist_cleaned_for_dashboard.xlsx.



👤 Author
Saravanan Jaisankar
GitHub: @Saro-07
Project: Olist Brazilian E-Commerce Analytics Case Study


