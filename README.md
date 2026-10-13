# Power BI Engineering: Customer Churn & Sales Analytics
 
**Tools:** Microsoft Power BI Desktop, Power Query, DAX, SQL Server, SQL Server Management Studio (SSMS)

## Project Overview

This project focuses on developing a business intelligence solution using Microsoft Power BI, SQL Server, Power Query, and DAX. It covers the major stages of an analytics workflow, beginning with data ingestion and transformation, followed by dimensional modelling, analytical calculations, interactive report development, and deployment-related concepts.

The project was organized into five exercises to gain practical experience in preparing data, structuring a data model, implementing reusable measures, building interactive visualizations, and understanding the operational requirements of a Power BI solution.

A Customer Churn & Sales Analytics Dashboard was also developed to bring customer-related indicators and spending-cluster analysis together in a single report page.

## Objectives

- Connect Power BI to different data sources and prepare data for analysis.
- Perform ETL operations using Power Query.
- Work with SQL Server tables and SQL queries.
- Build a dimensional data model using fact and dimension tables.
- Establish relationships between tables for analytical reporting.
- Create reusable DAX measures for financial and time-based analysis.
- Develop customer-level and revenue-focused visualizations.
- Build an interactive Customer Churn & Sales Analytics Dashboard.
- Understand Power BI deployment, refresh, gateway, and row-level security concepts.

## Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Power BI Desktop | Data modelling, report development, and visualization |
| Power Query | Data ingestion, transformation, cleaning, and type handling |
| DAX | Measures, time intelligence, and analytical calculations |
| SQL Server | Relational database and data storage |
| SQL Server Management Studio (SSMS) | SQL queries, table creation, and data validation |
| CSV and Excel | File-based data sources |
| Power BI Visualizations | Tables, cards, charts, slicers, and analytical reports |

## Exercise 1: Data Ingestion and Power Query ETL

The first exercise focused on connecting to multiple data sources and preparing data for downstream analysis.

### Implementation

- Worked with CSV-based sales order data.
- Prepared customer data from an Excel source.
- Used SQL Server as a source for product and other dimensional data.
- Inspected and transformed data using Power Query.
- Applied data type handling and reviewed transformation steps.
- Worked with text-cleaning operations, including trimming and combining customer name fields.
- Examined filtering and source-query operations for product data.
- Worked with monthly forecast data and the transformation of month columns into an analysis-friendly structure.
- Reviewed parameters and query organization for maintaining source configuration and transformation logic.

### Outcome

This exercise provided practical exposure to the ETL process in Power BI. It demonstrated how data from different sources can be brought together, cleaned, structured, and prepared for reporting.

## Exercise 2: Dimensional Modelling and Data Relationships

The second exercise focused on preparing a dimensional model suitable for analytical queries and reporting.

### Implementation

The model included the following core tables:

- **FactInternetSales:** Sales-related measures and foreign keys used for analysis.
- **DimDate:** Date attributes for calendar-based filtering and time intelligence.
- **DimProduct:** Product information and product categories.
- **DimCustomer:** Customer identifiers and descriptive attributes.
- **DimTerritory:** Territory and regional information.

Relationships were established between the fact table and its supporting dimensions. The model used one-to-many relationships with single-direction filtering for the core dimension-to-fact connections.

The date dimension was populated and validated for the period from 1 January 2023 to 31 December 2026. The SQL validation returned 1,461 records. The date table was also marked as a date table in Power BI.

The model included an active relationship for order dates and an inactive relationship for ship dates, supporting different date contexts for analytical calculations.

### Outcome

This exercise developed an understanding of dimensional modelling, fact and dimension tables, relationship cardinality, filter direction, and date-dimension preparation.

## Exercise 3: DAX Measures and Time Intelligence

The third exercise focused on implementing reusable analytical calculations using DAX.

A dedicated `_Measures` table was created to organize explicit measures separately from the underlying data tables.

### Measures Implemented

| Measure | Purpose |
|---|---|
| Total Revenue | Calculates total sales revenue |
| Total Cost | Calculates total product cost |
| Gross Margin | Calculates revenue minus cost |
| Margin % | Calculates gross margin as a percentage of revenue |
| Sales by Ship Date | Evaluates revenue using the ship-date relationship |
| Revenue YTD | Calculates year-to-date revenue |
| Prior Year Sales | Calculates revenue for the corresponding prior-year period |
| YoY Growth % | Calculates year-over-year revenue growth |
| Rolling 12M Sales | Evaluates revenue over a rolling twelve-month period |
| Customer Rank | Ranks customers according to revenue |

### Implementation Highlights

- Used explicit DAX measures rather than relying on calculated columns in the fact table.
- Organized measures within the `_Measures` table.
- Used `CALCULATE` and `USERELATIONSHIP` for alternative date-context analysis.
- Used time-intelligence functions for year-to-date and prior-year comparisons.
- Used `DATESINPERIOD` for rolling twelve-month calculations.
- Used `RANKX` for customer ranking.
- Validated measures by placing them in tables, cards, and charts.

### Outcome

This exercise provided hands-on experience with DAX syntax, reusable measures, filter context, time intelligence, and customer-level analytical calculations.

## Exercise 4: Interactive Reporting and Visual Analytics

The fourth exercise focused on presenting business information through interactive Power BI report visuals.

### Reporting Components

- Revenue and financial KPI cards.
- Date-wise revenue tables.
- Rolling twelve-month sales trend visualization.
- Customer ranking table.
- Revenue decomposition tree.
- Customer-focused reporting using customer identifiers, names, and revenue measures.
- Visual-level fields, tooltips, and drill-through configuration.

The decomposition tree was configured to analyse Total Revenue using fields such as product category and region. The customer-level table brought customer keys, customer names, rank, and revenue together in a single visual.

The report work emphasized clear presentation, comparison of business metrics, and the use of different visual types for different analytical requirements.

### Outcome

This exercise strengthened practical skills in report layout, visual selection, analytical presentation, and configuring visuals to support business exploration.

## Exercise 5: Deployment and Operational Readiness

The fifth exercise covered deployment-related concepts and considerations for preparing a Power BI solution for operational use.

### Areas Covered

- Publishing reports to the Power BI Service.
- Understanding scheduled refresh configuration.
- Reviewing gateway requirements for on-premises data sources.
- Understanding row-level security (RLS).
- Considering data source credentials and refresh dependencies.
- Reviewing report accessibility and operational validation requirements.

Deployment readiness involves ensuring that the data model, data sources, calculations, permissions, and report interactions work correctly in the intended environment.

**Note:** The work documented in the development screenshots primarily demonstrates Power BI Desktop, Power Query, and SQL Server activities. Successful publication, scheduled refresh, gateway configuration, and RLS testing should be documented separately when verified in the target Power BI environment.

### Outcome

This exercise developed an understanding of the operational considerations involved in moving a Power BI report from local development toward controlled and maintainable use.

## Customer Churn & Sales Analytics Dashboard

An additional reporting deliverable was the **Customer Churn & Sales Analytics Dashboard**, developed to explore customer-related metrics and spending-cluster patterns.

The dashboard combines multiple visualizations on a single report page using a dark-blue background, a prominent title, and white visual containers.

### Dashboard Components

- **Churn Probability by Spending Cluster:** A line-chart visual comparing customer counts and average churn probability across spending clusters.
- **Customer Count by Churn Risk Tier:** A table showing customer counts for the displayed risk tier.
- **Customer-Level Details:** A table containing fields such as ProductKey, ShipDate, and CustomerKey.
- **Churn Probability Summary:** A visual comparing average churn probability and customer counts by spending cluster.
- **Customer Distribution:** A donut chart showing the distribution of customers across the displayed spending clusters.
- **Churn Risk Tier Slicer:** An interactive slicer with High, Low, and Medium options.
- **KPI Cards:** Summary cards displaying average churn probability and customer counts for selected spending clusters.
- **Spending-Cluster Comparison:** Bar-chart visuals comparing customer counts and average churn probability across the available clusters.

### Analytical Value

The dashboard brings customer counts, churn-related measures, risk tiers, and spending-cluster comparisons together in one place. Users can inspect customer-level details, compare segments, and use the risk-tier slicer to explore the data under different selections.

The combination of KPI cards, tables, a donut chart, and bar-chart visuals provides complementary views of customer distribution and churn-related indicators.

The dashboard demonstrates the practical application of Power BI visual analytics to a customer-focused business scenario.

## SQL Server Implementation and Validation

SQL Server and SQL Server Management Studio were used to create and validate database objects supporting the Power BI model.

The implementation included:

- Creating dimensional table structures.
- Defining keys and data types.
- Preparing date records for the date dimension.
- Querying product attributes through SQL.
- Validating the date dimension using aggregate queries.
- Checking the date range and total number of records.

The date-dimension validation returned:

| Validation | Result |
|---|---|
| Total records | 1,461 |
| Start date | 2023-01-01 |
| End date | 2026-12-31 |

These checks helped verify that the calendar dimension covered the intended reporting period.

## Skills Demonstrated

- Data ingestion and ETL fundamentals
- Power Query transformations
- SQL querying and table creation
- Relational data modelling
- Fact and dimension table design
- Primary and foreign key concepts
- Power BI relationship configuration
- DAX measure development
- Time-intelligence calculations
- Revenue and margin analysis
- Customer ranking
- Data visualization and report development
- KPI cards, tables, slicers, and charts
- Customer segmentation and churn-related analysis
- Data validation and reporting workflow documentation
- Understanding of Power BI deployment and security concepts

## Project Structure

A suggested repository structure is shown below. Keep only the folders and files that you actually add to the repository.

```text
Power-BI-Engineering-Customer-Churn-Sales-Analytics/
|
|-- README.md
|-- Report/
|   |-- PowerBI_Engineering_Project_Report.pdf
|   `-- PowerBI_Engineering_Project_Report.tex
|
|-- Screenshots/
|   `-- Original implementation screenshots
|
|-- SQL/
|   `-- SQL scripts used for table creation and validation
|
`-- PowerBI/
    `-- Power BI report file (.pbix), if included
```

## How to Review the Project

1. Read the project report to understand the five exercises and the implementation workflow.
2. Review the screenshots to see the actual Power Query, SQL Server, and Power BI work.
3. Review the SQL scripts to understand the database table definitions and validation queries.
4. Open the Power BI report file, if included, to explore the data model, measures, and visualizations.
5. Review the Customer Churn & Sales Analytics Dashboard to understand the customer segmentation and churn-related reporting approach.

## Conclusion

This project provided practical exposure to the Power BI analytics workflow, covering data ingestion, ETL, dimensional modelling, DAX measures, interactive reporting, and deployment-related concepts. It combined SQL-based data preparation with Power BI modelling and visualization to develop a structured business intelligence solution.

The Customer Churn & Sales Analytics Dashboard served as an additional reporting deliverable, bringing together customer counts, churn probability, risk tiers, and spending-cluster comparisons. Overall, the project strengthened my understanding of data preparation, analytical modelling, business metrics, and interactive dashboard development as a Data Engineering Trainee at Nexturn.

---


