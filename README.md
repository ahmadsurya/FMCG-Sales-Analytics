# FMCG Sales Analytics Project

## Overview
This repository contains an **end-to-end FMCG Sales analytics project** designed to simulate how a **professional Data Analyst** delivers business-ready insights in a large, multi-brand FMCG organization.

The project covers the full analytics lifecycle:
**business context → data modeling → data quality → KPI governance → dashboard → business insights**.

The focus is not on tool complexity, but on **analytics maturity, trust, and decision support**.

---

## Business Objective
The primary objective of this project is to:
- Provide a **single source of truth** for sales and profitability KPIs
- Enable **monthly business reviews (MBR)** for executives and brand managers
- Identify **growth drivers, profitability quality, and portfolio risks**

This analytics setup reflects **real-world FMCG decision workflows**, not academic exercises.

---

## Key Stakeholders & Decisions
- **Executive Management**  
  Business health, growth, and profitability monitoring

- **Brand Managers**  
  Brand performance, pricing effectiveness, and margin quality

- **Commercial / Strategy Team**  
  Growth sustainability and revenue concentration risk

---

## KPI Framework (Summary)
All KPIs are defined once in the **SQL semantic layer** and consumed consistently across tools.

### Core KPIs
- Total Revenue  
- Gross Profit  
- Gross Margin %  
- Total Orders  
- Quantity Sold  
- Average Order Value (AOV)  
- MoM Revenue Growth %

### Advanced (Maturity) KPIs
- Revenue Contribution %  
- Profit per Unit  

> **Important:**  
> KPIs are calculated in **SQL Views**, not in Power BI or Tableau.

---

## Analytics Architecture (High Level)

<pre>
CSV Files (Raw)
↓
Python Preprocessing (Light ETL)
↓
PostgreSQL Analytics Schema
↓
SQL Views (Semantic Layer)
↓
Dashboard & Business Insights
</pre>

This architecture ensures **consistency, traceability, and governance**.

---

## Repository Structure
📍 **THIS IS WHERE THE FINAL GITHUB PROJECT STRUCTURE IS PLACED**

The structure below serves as a **map of the repository** and is the first reference point for reviewers.
<pre>
fmcg-sales-analytics/
│
├── README.md
│   # Project overview, business objective, architecture summary
│
├── data/
│   ├── raw/
│   │   ├── fact_sales.csv
│   │   ├── dim_product.csv
│   │   ├── dim_customer.csv
│   │   ├── dim_channel.csv
│   │   └── dim_date.csv
│   │
│   └── processed/
│       └── fact_sales_ready.csv
│
├── sql/
│   ├── schema/
│   │   ├── 01_create_schema.sql
│   │   ├── 02_create_dimension_tables.sql
│   │   ├── 03_create_fact_sales.sql
│   │   ├── 04_add_dim_date.sql
│   │   └── 05_create_indexes.sql
│   │
│   ├── views/
│   │   ├── vw_sales_daily.sql
│   │   ├── vw_sales_monthly.sql
│   │   ├── vw_sales_brand_monthly.sql
│   │   └── vw_brand_kpi_summary.sql
│   │
│   └── validation/
│       └── data_quality_checks.sql
│
├── src/
│   ├── data_load/
│   │   ├── generate_dim_date.py
│   │   └── preprocess_fact_sales.py
│   │
│   ├── eda/
│   │   ├── eda_overview.py
│   │   ├── eda_brand.py
│   │   ├── eda_growth.py
│   │   └── eda_customer.py
│   │
│   └── utils/
│       └── db_connection.py
│
├── dashboards/
│   ├── powerbi/
│   │   └── paragon_fmcg_dashboard.pbix
│   │
│   └── tableau/
│       └── paragon_fmcg_dashboard.twb
│
├── docs/
│   ├── 01_business_context.md
│   │   # Stakeholder needs & KPI framework
│   │
│   ├── 02_data_sources.md
│   │   # Data source, schema, and lineage
│   │
│   ├── 03_data_model.md
│   │   # ERD, star schema, and grain explanation
│   │
│   ├── 04_pipeline_design.md
│   │   # Analytics pipeline (Data Analyst perspective)
│   │
│   ├── 05_data_quality.md
│   │   # Data quality framework & validation checks
│   │
│   ├── 06_analytics_logic.md
│   │   # KPI & metric definitions (semantic layer)
│   │
│   └── 07_dashboard_insight.md
│       # Business insights & recommendations
│
├── assets/
│   └── dashboard_screenshots/
│       ├── page_1_executive_overview.png
│       ├── page_2_brand_performance.png
│       └── page_3_growth_contribution.png
│
├── requirements.txt
│   # Python dependencies for analytics workflow
│
└── .gitignore
    # Git ignore rules (Python, data, BI temp files)
</pre>
---

## Documentation (Detailed)
For detailed explanations, please refer to the documents below:

1. [01 Business Context](docs/01_business_context.md)  
2. [02 Data Sources & Lineage](docs/02_data_sources.md)  
3. [03 Data Model & ERD](docs/03_data_model.md)  
4. [04 Pipeline Design](docs/04_pipeline_design.md)  
5. [05 Data Quality Framework](docs/05_data_quality.md)  
6. [06 Analytics Logic (KPI Definitions)](docs/06_analytics_logic.md)  
7. [07 Dashboard Insights & Recommendations](docs/07_dashboard_insight.md)  

These documents together form a **complete analytics documentation set**.

---

## Dashboard Preview
Dashboard screenshots are available in: assets/dashboard_screenshots/


The dashboard is designed with:
- 3 pages (Executive Overview, Brand Performance, Growth & Contribution)
- KPI-first layout
- Decision-oriented visuals
- Minimal but functional tooltips

---

## How to Reproduce (High Level)
1. Review raw data in `data/raw/`
2. Run preprocessing scripts in `src/data_load/`
3. Load processed data into PostgreSQL (`analytics` schema)
4. Create SQL views from `sql/views/`
5. Open dashboard file in Power BI or Tableau

---

## Scope & Limitations
**In scope:**
- Sales performance analytics
- Profitability and growth analysis
- KPI governance and dashboarding

**Out of scope (by design):**
- Campaign ROI
- Inventory & supply chain
- Forecasting & machine learning
- Real-time pipelines

These areas are typically handled by separate teams in FMCG organizations.

---

## Final Notes
This project demonstrates how a Data Analyst:
- Translates business needs into analytics design
- Builds trust through data quality and KPI governance
- Delivers insights that support real business decisions

The emphasis is on **clarity, consistency, and business impact** rather than tool complexity.

---
