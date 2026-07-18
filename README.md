# Credit Card Financial Analytics Dashboard

## 📊 Project Overview
This project delivers a comprehensive, enterprise-level credit card portfolio analytics solution. By engineering a robust data pipeline to ingest, clean, and model relational credit card database schemas, this system tracks a high-scale portfolio capturing over **657K total transactions**. The resulting interactive Power BI dashboard provides stakeholders with actionable insights to optimize risk management, streamline lifecycle tracking, and accelerate revenue growth.

---

## 🏗️ Repository Structure
Based on the production files deployed in this repository:
* `SQL Query - Financial Dashboard.sql`: Core script handling database initialization, ETL staging, and complex data transformations.
* `credit_card.csv` & `customer.csv`: Initial baseline transaction and demographic portfolios.
* `cc_add.csv` & `cust_add.csv`: Batch update datasets simulating ongoing incremental data ingestion.
* `Credit Card Financial Dashboard.pbix`: The core Power BI application containing data models, DAX measures, and interactive reporting views.

---

## ⚡ Tech Stack & Architecture
* **Data Engineering & ETL:** SQL (Schema design, data ingestion, data type formatting, and exploratory partitioning).
* **Business Intelligence & Analytics:** Power BI Desktop.
* **Data Modeling:** Relational Star Schema (Fact and Dimension table optimization).
* **Analytical Computations:** Advanced DAX (Data Analysis Expressions) for time-intelligence and segmentation calculations.

---

## 🔍 Key Business Insights

### 💳 Customer Segmentation & Utilization
* **Dominant Tiers:** **Blue & Silver card tiers** serve as the primary foundational drivers of account activity, generating **93% of all portfolio transactions**.

### 📍 Geographic & Revenue Concentration
* **High-Yield Markets:** Portfolio revenue is heavily localized, with just three core states—**Texas (TX), New York (NY), and California (CA)**—generating **68% of the $55.4M total revenue**.

### 📈 Growth Velocity & Portfolio Health
* **WoW Momentum:** Successfully captured and highlighted a **28.8% Week-over-Week (WoW) revenue growth surge**, providing leadership with real-time feedback on marketing campaigns and transaction velocity.
* **Lifecycle Engagement:** Monitored a **57.5% customer activation rate**, establishing a baseline KPI to optimize ongoing credit risk assessment and proactive lifecycle tracking.

---

## 🛠️ Data Modeling & DAX Showcase

### 1. Relational Data Modeling
The underlying architecture leverages a optimized **Star Schema**, forming clean relationships between transaction fact tables and customer dimension tables to ensure high-performance cross-filtering.

### 2. Time-Intelligence DAX Calculation Example
To track the dynamic weekly revenue velocity without relying purely on standard visual filters, the following advanced DAX logic was implemented to isolate Week-over-Week performance:

```dax
Revenue_WoW_Growth = 
VAR Current_Week_Revenue = [Total_Revenue]
VAR Previous_Week_Revenue = CALCULATE([Total_Revenue], DATEADD('Calendar'[Date], -7, DAY))
RETURN
IF(
    ISBLANK(Previous_Week_Revenue), 
    BLANK(), 
    DIVIDE(Current_Week_Revenue - Previous_Week_Revenue, Previous_Week_Revenue)
)
🖼️ Dashboard Visualizations
(Replace the placeholder paths below with your actual screenshot images once uploaded to your repository)

1. Transaction & Revenue Overview
2. Customer Demographics & Risk Analysis
🔒 Data Privacy & Compliance Notice
Anonymization Statement: All transaction records, customer details, and financial parameters utilized across these dataset files are completely synthetic or thoroughly anonymized. No real Personally Identifiable Information (PII) or proprietary financial data is hosted within this repository.
