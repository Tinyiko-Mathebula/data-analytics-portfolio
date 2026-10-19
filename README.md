# E-Commerce Transactions: Data Cleaning and Exploratory Data Analysis

## Project Overview

This project analyzes an online retail transactions dataset to demonstrate practical data analytics skills, including data quality assessment, data cleaning, validation, exploratory data analysis (EDA), KPI calculation, and business insight development.

The goal was to transform raw transaction records into a reliable dataset for analysis and identify patterns in sales performance, customer purchasing behavior, and geographic sales distribution.

## Business Objectives

- Assess and improve the quality of raw transaction data.
- Identify and distinguish standard sales from cancellations, returns, and accounting adjustments.
- Calculate key sales and customer performance indicators.
- Explore sales trends over time and across countries.
- Translate analytical findings into actionable business insights.

## Dataset

**Source:** [Online Retail Dataset — Kaggle](https://www.kaggle.com/datasets/vijayuv/onlineretail)

The original dataset contains **541,909 transaction records and 8 columns**:

| Column | Description |
|---|---|
| `InvoiceNo` | Transaction invoice identifier |
| `StockCode` | Product identifier |
| `Description` | Product description |
| `Quantity` | Number of units in the transaction line |
| `InvoiceDate` | Date and time of the transaction |
| `UnitPrice` | Price per unit |
| `CustomerID` | Customer identifier |
| `Country` | Customer's country as recorded in the dataset |

## Tools and Technologies

- **Python** — data analysis and processing
- **Pandas** — data cleaning, transformation, validation, and aggregation
- **Jupyter Notebook** — documenting the analysis and workflow
- **GitHub** — version control and portfolio presentation

## Data Cleaning and Validation

The cleaning process focused on understanding the data before making changes and ensuring that business calculations used appropriate records.

Key activities included:

- Inspecting dataset structure, column names, data types, and missing values.
- Identifying and removing **5,268 exact duplicate rows**.
- Standardizing column names and text values.
- Converting transaction dates to datetime format and validating numeric fields.
- Investigating missing customer identifiers and product descriptions.
- Examining negative quantities, zero prices, negative prices, cancellations, returns, and accounting adjustments.
- Separating standard sales transactions from non-standard records for sales analysis.
- Creating a calculated `sales_value` field using quantity multiplied by unit price.

The analysis distinguished between data-quality problems and records that could be legitimate business events. For example, negative quantities may represent cancellations or returns rather than incorrect data.

## Key Performance Indicators

The standard-sales analysis produced the following results:

| KPI | Result |
|---|---:|
| Standard sales transaction lines | 524,877 |
| Total standard sales value | 10,631,048.74 |
| Unique invoices | 19,959 |
| Identified customers | 4,338 |
| Average transaction-line value | 20.25 |
| Share of sales contributed by the top 10 identified customers | 17.30% |

*The sales value and average line value use the monetary units recorded in the source dataset. Transaction lines, invoices, and customers represent different levels of measurement and should not be treated as interchangeable.*

## Key Business Insights

### 1. Monthly Sales Performance

November 2011 recorded the highest monthly sales value in the analysis, at approximately 1.50 million. December 2011 contains data only through December 9, so it represents a partial month and should not be compared directly with complete months without accounting for the difference in coverage.

### 2. Geographic Sales Concentration

The United Kingdom generated approximately 8.73 million in sales value, indicating that sales in this dataset were heavily concentrated in the UK market.

### 3. Customer Sales Concentration

The top 10 identified customers contributed 17.30% of standard sales value. This provides a useful starting point for examining customer concentration and the importance of retaining high-value customers.

The findings are descriptive of the available dataset and do not, by themselves, establish the causes of sales patterns or predict future performance.

## Project Deliverables

- **Jupyter Notebook:** Data profiling, cleaning, validation, EDA, calculations, and visualizations.
- **Cleaned CSV:** A dataset prepared for standard-sales analysis.
- **Insight report:** A concise business-focused report summarizing key findings and implications.

## Limitations and Considerations

- Some transaction records have missing customer identifiers, limiting customer-level analysis to identifiable customers.
- Cancellations, returns, and accounting adjustments require careful treatment to avoid misleading sales calculations.
- December 2011 is only partially represented in the dataset.
- Historical sales patterns describe the observed period and should not automatically be interpreted as current market conditions.
- The results depend on the cleaning rules and business definitions applied during the analysis.

## Conclusion

This project demonstrates an end-to-end analytical workflow, from inspecting and validating raw transaction data to preparing a clean analytical dataset, calculating business KPIs, and communicating findings.

It emphasizes the importance of understanding the business meaning of transaction records before cleaning them and making decisions based on the resulting analysis.

## Repository Structure

```text
data-cleaning-eda/
├── data/
│   ├── OnlineRetail.csv
│   └── OnlineRetail_cleaned.csv
├── notebooks/
│   └── 01_ecommerce_data_cleaning_eda.ipynb
├── reports/
│   └── ecommerce_eda_insight_report.pdf
└── README.md



