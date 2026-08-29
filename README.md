# Olist E-Commerce Sales & Delivery Performance Analysis
An end-to-end data analytics project examining sales trends, product performance, regional revenue distribution, and the relationship between delivery speed and customer satisfaction — using real, anonymized order data from Olist, a Brazilian e-commerce marketplace.

## Business Problem
Olist connects small businesses to major Brazilian marketplaces. With 100k+ real orders across 27 states, this project asks:
- What's driving revenue, and where is it concentrated?
- Which product categories and regions matter most?
- Does delivery performance actually affect customer satisfaction — and by how much?
- Where should the business focus to reduce risk and unlock growth?

## Dataset
- **Source:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle)
- **Size:** ~110,000 delivered orders, September 2016 – August 2018
- **Scope:** Orders, order items, customers, products (71 categories), payments, reviews, and sellers across 27 Brazilian states
- **Note:** Real commercial data, anonymized by Olist; product categories translated from Portuguese to English for analysis

## Tools & Skills Used
| Tool | Purpose |
|---|---|
| **Python (Pandas)** | Data merging, cleaning, aggregation |
| **Matplotlib / Seaborn** | Exploratory visualizations |
| **Jupyter Notebook (Google Colab)** | Analysis environment |
| **Power BI / Tableau** | Interactive dashboard *(add link/screenshot once built)* |
| **Excel** | Cleaned dataset export for dashboarding |

**Skills demonstrated:** data cleaning, multi-table joins, exploratory data analysis (EDA), time-series trend analysis, business insight generation, data storytelling.

## Project Workflow
1. **Load & merge** — Combined 7 relational tables (orders, order items, customers, products, payments, reviews, sellers) into a single analysis-ready dataset.
2. **Clean** — Parsed timestamps, handled missing values, filtered to `delivered` orders only (110,197 of 112,650) to keep revenue figures accurate — excluding cancelled/unfulfilled orders.
3. **Engineer features** — Calculated delivery time (days) and a late-delivery flag by comparing actual vs. estimated delivery dates.
4. **Explore** — Analyzed monthly revenue trends, top categories, regional performance, average order value, payment method usage, and delivery's impact on review scores.
5. **Export** — Produced a cleaned, merged dataset (`olist_cleaned_for_dashboard.xlsx`) for use in Power BI / Tableau.

## Key Insights
- **Revenue:** Total revenue of **R$13.2M** across ~110k delivered orders. Growth was steady through 2017, peaking at **R$987.8k in November 2017** (likely a Black Friday effect), then stabilizing between R$850k–975k/month through mid-2018.

- **Product mix:** No single category dominates — `health_beauty` leads at just **9.3%** of revenue, followed by `watches_gifts` (8.8%) and `bed_bath_table` (7.7%). The catalog is diversified, which lowers risk but also means there's no single lever to pull for a quick revenue boost.

- **Regional concentration:** **São Paulo (SP) alone drives 38.3% of total revenue** — more than double the next-largest state, Rio de Janeiro (13.3%). SP + RJ + MG together account for **over 63%** of revenue, highlighting significant geographic concentration risk and untapped opportunity in underpenetrated states (GO, ES, DF each under 2.5%).

- **Delivery drives satisfaction — significantly:** This is the standout finding. On-time orders average a **4.21/5** review score, while late orders average just **2.55/5** — a **1.66-point gap**. Only 7.9% of orders arrive late, but each one carries a disproportionate hit to customer satisfaction.

- **Average Order Value:** **R$137.04** per order.

## Recommendations
1. **Invest in delivery reliability.** Even a modest reduction in the 7.9% late-delivery rate would likely produce an outsized lift in average review scores, given the steep satisfaction drop-off for late orders.
2. **Diversify regional reach.** With SP/RJ/MG accounting for the majority of revenue, a targeted expansion or marketing push into underpenetrated states (e.g. GO, ES, DF) represents a lower-risk growth opportunity than doubling down on saturated regions.
3. **Monitor category mix, not just top performers.** Because revenue is spread across many categories rather than concentrated in one, category-level strategy should focus on protecting broad performance rather than optimizing a single "hero" category.

## 📁 Repository Structure
```text
Ecommerce-Sales-Analysis/
├── .gitignore
├── LICENSE
├── requirements.txt
├── README.md
├── DAX_Measures.md
├── Olist_Sales_Analysis.ipynb
├── olist_cleaned_for_dashboard.xlsx
├── dashboard/
    ├── OLIST E-COMMERCE INTELLIGENCE.pbix
    ├── executive_summary.png
    └── logistics_deep_dive.png

## Dashboard
*(Add once built)* — An interactive Power BI / Tableau dashboard built on the cleaned dataset, covering monthly revenue trends, category performance, state-level revenue, and delivery vs. satisfaction, with filters for date range, category, and region.

## How to Reproduce
1. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).
2. Open `Olist_Sales_Analysis.ipynb` in Jupyter or [Google Colab](https://colab.research.google.com).
3. Upload the raw CSV files to the same environment.
4. Run all cells — the notebook will merge, clean, analyze, and export the final dataset.

## Author
*(Saravanan J, [LinkedIn](https://www.linkedin.com/in/saravanan-jaisankar/))*

