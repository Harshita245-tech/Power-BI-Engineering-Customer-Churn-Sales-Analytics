# 📊 Power BI Engineering | Customer Churn & Sales Analytics



## 📌 Project Overview

This project focuses on developing a Power BI analytics solution using SQL Server, Power Query, DAX, and interactive visualizations. It covers five exercises involving data ingestion, ETL, dimensional modelling, analytical calculations, report development, and deployment-related concepts.

The project also includes a **Customer Churn & Sales Analytics Dashboard**, which brings together customer counts, churn probability, spending clusters, and churn risk tiers in a single report page.

The main objective was to gain practical experience in preparing data, building a structured data model, creating reusable measures, and presenting business information through interactive dashboards.

## 🎯 Project Objectives

- 📥 Connect Power BI to different data sources.
- 🧹 Perform data cleaning and transformation using Power Query.
- 🗄️ Create and validate database tables using SQL Server.
- 🧩 Build a dimensional data model using fact and dimension tables.
- 🔗 Configure relationships between tables.
- 🧮 Develop reusable DAX measures and time-intelligence calculations.
- 📈 Create interactive visualizations and analytical reports.
- 👥 Analyse customer counts, spending clusters, and churn-related indicators.
- 🚀 Understand Power BI deployment, refresh, gateway, and security concepts.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| 📊 Power BI Desktop | Data modelling, visualization, and report development |
| 🔄 Power Query | Data ingestion, cleaning, and transformation |
| 🧮 DAX | Analytical measures and time-intelligence calculations |
| 🗄️ SQL Server | Relational data storage and database operations |
| 💻 SQL Server Management Studio | SQL queries, table creation, and data validation |
| 📄 CSV and Excel | File-based data sources |

---

# 🧪 Exercise 1: Data Ingestion and Power Query ETL

### 📌 Objective

To connect to multiple data sources and prepare structured, reliable data for reporting and analysis.

### ⚙️ Implementation

- 📥 Imported sales order data from CSV files.
- 📑 Worked with customer data from an Excel source.
- 🗄️ Connected Power BI to SQL Server tables.
- 🧹 Applied data-cleaning and transformation operations in Power Query.
- 🔤 Combined customer name fields and cleaned text values.
- 🗓️ Reviewed date columns and assigned appropriate data types.
- 🔎 Inspected filtering and source-query operations for product data.
- 🔄 Prepared monthly forecast data for analysis by transforming month columns.
- ⚙️ Reviewed parameters and query organization for source configuration and transformation management.

### ✅ Outcome

This exercise provided practical experience with the ETL workflow: extracting data from different sources, transforming it into a consistent structure, and preparing it for analytical modelling.

---

# 🧪 Exercise 2: Dimensional Modelling and Relationships

### 📌 Objective

To organize the data into a dimensional model that supports efficient analysis and reporting.

### 🧩 Core Tables

- **FactInternetSales:** Stores sales-related measures and keys used for analysis.
- **DimDate:** Provides date attributes for calendar-based reporting.
- **DimProduct:** Stores product information and category attributes.
- **DimCustomer:** Stores customer identifiers and descriptive information.
- **DimTerritory:** Provides territory and regional attributes.

### ⚙️ Implementation

- 🔗 Established one-to-many relationships between dimension tables and the fact table.
- ➡️ Used single-direction filtering for the core dimension-to-fact relationships.
- 🗓️ Prepared a date dimension covering 1 January 2023 through 31 December 2026.
- 🧮 Validated the date dimension using SQL queries.
- 📅 Marked `DimDate` as the official date table in Power BI.
- 🔄 Configured an active order-date relationship and an inactive ship-date relationship for alternative date analysis.

### ✅ SQL Validation Results

| Validation | Result |
|---|---|
| Total date records | 1,461 |
| Start date | 2023-01-01 |
| End date | 2026-12-31 |

### ✅ Outcome

This exercise strengthened my understanding of dimensional modelling, fact and dimension tables, relationship cardinality, filter direction, and date-dimension preparation.

---

# 🧪 Exercise 3: DAX Measures and Time Intelligence

### 📌 Objective

To create reusable analytical measures for revenue analysis, profitability, customer ranking, and time-based comparisons.

A dedicated `_Measures` table was created to organize the explicit DAX measures separately from the underlying data tables.

### 🧮 Measures Implemented

| Measure | Purpose |
|---|---|
| 💰 Total Revenue | Calculates total sales revenue |
| 💸 Total Cost | Calculates total product cost |
| 📈 Gross Margin | Calculates revenue minus cost |
| 📊 Margin % | Calculates gross margin as a percentage of revenue |
| 🚚 Sales by Ship Date | Calculates revenue using the ship-date relationship |
| 📅 Revenue YTD | Calculates year-to-date revenue |
| 🔙 Prior Year Sales | Calculates revenue for the corresponding prior-year period |
| 📉 YoY Growth % | Calculates year-over-year revenue growth |
| 🔄 Rolling 12M Sales | Evaluates revenue over a rolling twelve-month period |
| 🏆 Customer Rank | Ranks customers according to revenue |

### ⚙️ Implementation Highlights

- Created explicit measures in the `_Measures` table.
- Used `CALCULATE` and `USERELATIONSHIP` for alternative date-context analysis.
- Used `TOTALYTD` for year-to-date calculations.
- Used `SAMEPERIODLASTYEAR` for prior-year comparisons.
- Used `DATESINPERIOD` for rolling twelve-month calculations.
- Used `RANKX` for customer ranking.
- Tested measures in tables, cards, and charts.

### ✅ Outcome

This exercise provided practical experience with DAX, reusable calculation logic, filter context, time intelligence, financial measures, and customer-level analytics.

---

# 🧪 Exercise 4: Interactive Reporting and Visual Analytics

### 📌 Objective

To present analytical results through clear and interactive Power BI visuals.

### 📊 Reporting Components

- 💳 KPI cards for summary measures.
- 📋 Date-wise revenue table.
- 📈 Rolling twelve-month sales trend.
- 🏆 Customer ranking table.
- 🌳 Revenue decomposition tree.
- 👥 Customer-focused reporting.
- 🔍 Visual-level fields and tooltips.
- ↪️ Drill-through configuration for customer-level analysis.

### ⚙️ Implementation Highlights

The revenue decomposition tree was configured to analyse Total Revenue using explanatory fields such as product category and region. The customer-level table combines customer identifiers, names, revenue, and rank to support comparisons between customers.

The report work focused on presenting information in a readable format and selecting visualizations appropriate to each analytical requirement.

### ✅ Outcome

This exercise strengthened my skills in report layout, visualization selection, KPI presentation, customer-level analysis, and interactive report configuration.

---

# 🧪 Exercise 5: Deployment and Operational Readiness

### 📌 Objective

To understand the operational requirements involved in preparing a Power BI solution for use beyond the development environment.

### 🚀 Areas Covered

- ☁️ Power BI Service publishing concepts.
- 🔄 Scheduled refresh configuration.
- 🔌 Gateway requirements for on-premises data sources.
- 🔐 Row-level security (RLS).
- 🔑 Data source credentials and refresh dependencies.
- ✅ Report validation and operational-readiness considerations.

### ⚙️ Implementation Focus

This exercise addressed the considerations required to move a report from local development toward operational use. These include data-source connectivity, refresh dependencies, access control, and validation of report behaviour.

### ✅ Outcome

The exercise developed my understanding of Power BI deployment concepts, refresh requirements, gateway usage, and report security considerations.

**Note:** Publishing, scheduled refresh, gateway configuration, and RLS should be described as completed implementation tasks only when their successful configuration and testing have been verified in the target environment.

---

# 📊 Customer Churn & Sales Analytics Dashboard

### 🎯 Dashboard Overview

The Customer Churn & Sales Analytics Dashboard was developed to explore customer counts, churn-related indicators, spending clusters, and risk-tier distributions through a single Power BI report page.

The dashboard uses a dark-blue background, a prominent title, and white visual containers to organize the analytical components.

### 📌 Dashboard Visualizations

**1. 📈 Churn Probability by Spending Cluster**

Compares customer counts and average churn probability across the displayed spending clusters.

**2. 📋 Customer Count by Churn Risk Tier**

Displays customer counts for the risk tier represented in the data.

**3. 🗂️ Customer-Level Details**

Shows fields such as ProductKey, ShipDate, and CustomerKey for reviewing individual records.

**4. 📊 Churn Probability Summary**

Compares average churn probability and customer counts by spending cluster.

**5. 🍩 Customer Distribution**

Uses a donut chart to display customer distribution across the represented spending clusters.

**6. 🎚️ Churn Risk Tier Slicer**

Provides High, Low, and Medium options for interactive filtering.

**7. 💳 KPI Cards**

Displays average churn probability and customer counts for selected spending clusters.

**8. 📉 Spending-Cluster Comparison**

Uses bar-chart visuals to compare customer counts and average churn probability across spending clusters.

### 💡 Business Value

The dashboard combines multiple analytical views to help users explore customer segments and compare spending clusters. KPI cards provide quick summaries, charts reveal patterns, and the slicer allows users to examine the displayed data under different risk-tier selections.

The dashboard demonstrates how Power BI can be used to combine customer-level information, summary metrics, and interactive visualizations in a business-oriented report.

---

# 🗄️ SQL Server Implementation and Validation

SQL Server and SQL Server Management Studio were used to prepare and validate database objects supporting the Power BI model.

### ⚙️ Key Activities

- 🏗️ Created dimensional table structures.
- 🔑 Defined primary keys and data types.
- 🗓️ Populated the date dimension.
- 🔎 Queried product attributes using SQL.
- 🧮 Validated date record counts and date boundaries.
- 🔗 Prepared data for use in Power BI.

### ✅ Date Dimension Validation

The SQL validation confirmed the intended date range and record count.

| Check | Result |
|---|---|
| Record count | 1,461 |
| Minimum date | 2023-01-01 |
| Maximum date | 2026-12-31 |

These checks helped confirm that the date dimension covered the required reporting period.

---

# 🧠 Skills Demonstrated

- 📥 Data ingestion and ETL fundamentals
- 🧹 Power Query transformations
- 🗄️ SQL querying and table creation
- 🧩 Dimensional modelling
- 🔗 Data relationships and filter direction
- 🧮 DAX measure development
- 📅 Time-intelligence calculations
- 💰 Revenue and margin analysis
- 🏆 Customer ranking
- 📊 Power BI visualization and report development
- 🎚️ Interactive slicers and report configuration
- 👥 Customer segmentation and churn-related analysis
- ✅ Data validation and reporting documentation
- 🚀 Understanding of deployment and security concepts

---



---

# 🔍 How to Review the Project

1. 📖 Read the project report for an overview of all five exercises.
2. 🖼️ Review the screenshots to see the actual implementation.
3. 🗄️ Examine the SQL scripts to understand database creation and validation.
4. 📊 Open the `.pbix` file, if included, to inspect the data model, measures, and visuals.
5. 👥 Explore the Customer Churn & Sales Analytics Dashboard to review the customer and spending-cluster analysis.

---

# 🏁 Conclusion

This project provided practical experience across the Power BI analytics workflow, including data ingestion, ETL, dimensional modelling, DAX calculations, interactive reporting, and deployment-related concepts.

The Customer Churn & Sales Analytics Dashboard brought together customer counts, churn probability, risk tiers, and spending-cluster comparisons in a single report. The project strengthened my understanding of SQL-based data preparation, analytical modelling, business metrics, and interactive dashboard development.

As a **Data Engineering Trainee at Nexturn**, this work helped me connect data engineering fundamentals with business intelligence requirements and develop practical skills in preparing, modelling, analysing, and presenting data.

---

