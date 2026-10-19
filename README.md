# E-Commerce Transactions: Data Cleaning and Exploratory Data Analysis

## Project Overview

This project demonstrates an end-to-end data analytics workflow using an online retail transactions dataset. Using Python and Pandas, I assessed data quality, cleaned and validated transaction records, performed exploratory data analysis (EDA), calculated key performance indicators (KPIs), and translated findings into business insights.

The analysis focused on sales performance, customer purchasing behaviour, product performance, geographic market concentration, and transaction trends between December 2010 and December 2011.

## Business Objectives

- Assess data quality and identify missing values, duplicate records, and unusual transactions.
- Apply business-aware data cleaning and validation rules.
- Distinguish standard sales from cancellations, returns, accounting adjustments, and other non-standard records.
- Analyse sales trends across time, products, customers, and markets.
- Calculate sales and customer performance KPIs.
- Communicate findings, limitations, and potential business recommendations.

## Dataset

- **Dataset:** Online Retail Transactions
- **Source:** Kaggle
- **Original dataset size:** 541,909 rows and 8 columns
- **Analysis period:** 1 December 2010 – 9 December 2011

The dataset contains transaction-level information, including invoice identifiers, product codes, quantities, unit prices, invoice dates, customer identifiers, and countries.

## Tools and Technologies

- **Python** — data analysis and processing
- **Pandas** — data cleaning, transformation, validation, grouping, and aggregation
- **NumPy** — numerical operations
- **Matplotlib and Seaborn** — data visualisation
- **Jupyter Notebook** — analytical workflow and documentation
- **GitHub** — version control and portfolio presentation

## Data Analyst Workflow

### 1. Data Understanding and Profiling

Inspected the dataset structure, dimensions, column names, data types, missing values, and duplicate records to understand the quality and limitations of the raw data.

### 2. Data Cleaning and Validation

- Removed 5,268 exact duplicate rows.
- Converted `InvoiceDate` to a datetime data type.
- Standardised selected fields.
- Investigated missing customer identifiers and product descriptions.
- Examined negative quantities, zero and negative prices, cancellations, returns, accounting adjustments, and extreme quantities.
- Applied business-aware rules to distinguish standard sales from non-standard transactions.
- Created a calculated `sales_value` field using quantity multiplied by unit price.

Rather than treating every unusual value as an error, I investigated its potential business meaning before deciding how it should be handled in the sales analysis.

### 3. Exploratory Data Analysis

Explored sales performance across time, products, customers, and countries to identify patterns, concentrations, and unusual transactions.

### 4. KPI Development

Calculated sales and customer metrics to support performance analysis and comparisons.

### 5. Business Insights and Recommendations

Interpreted the results, documented data limitations, and identified opportunities for further investigation and business improvement.

## Key Performance Indicators

The standard-sales analysis produced the following results:

| Metric | Result |
|---|---:|
| Standard-sales transaction lines | 524,877 |
| Total standard-sales value | 10,631,048.74 |
| Unique invoices | 19,959 |
| Identified customers | 4,338 |
| Average transaction-line value | 20.25 |
| Top 10 identified customers' share of sales | 17.30% |

*Sales values are expressed in the monetary units recorded in the source dataset. Transaction lines represent individual product lines; a single invoice may contain multiple lines. The top 10 customer share relates to sales attributed to customers with an identified `CustomerID`.*

## Key Business Insights

### 1. Sales Performance and Trends

November 2011 recorded the highest complete-month sales value, at approximately 1.50 million, and the highest transaction-line volume, at 82,004 lines. The increase appears primarily volume-driven and warrants further investigation into its underlying causes.

December 2011 covers only the period through 9 December and should not be compared directly with complete months without accounting for the partial reporting period.

### 2. Geographic Market Concentration

The United Kingdom generated approximately 8.73 million in product sales, substantially exceeding other markets. The Netherlands, EIRE, Germany, and France were the next largest markets.

This concentration highlights the importance of the UK market while providing a basis for investigating opportunities in other markets.

### 3. Customer Sales Concentration

The top 10 identified customers contributed 17.30% of sales attributed to customers with an identified `CustomerID`.

This indicates a meaningful contribution from high-value customers and supports further investigation into customer retention and purchasing behaviour.

### 4. Product Performance and Outlier Investigation

`REGENCY CAKESTAND 3 TIER` generated approximately 174,156.54 in sales.

`PAPER CRAFT, LITTLE BIRDIE` also ranked highly but was heavily influenced by an 80,995-unit transaction. This extreme quantity was investigated rather than interpreted automatically as normal product demand.

The finding demonstrates why product rankings and averages should be considered alongside transaction-level anomalies.

### 5. Data Quality and Reliability

Missing `CustomerID` values, cancellations, accounting adjustments, zero-priced records, and extreme quantities required careful investigation and business-aware treatment.

These checks helped establish a more appropriate basis for standard-sales analysis while making the limitations of the data explicit.

## Data Limitations

- Approximately 25.16% of records have a missing `CustomerID`, limiting customer-level analysis.
- December 2011 is a partial month, with data available only through 9 December.
- Extreme transactions may influence averages, rankings, and apparent product demand.
- The dataset does not include customer demographics, marketing channels, or customer acquisition costs.
- The results depend on the business rules used to distinguish standard sales from non-standard transactions.

## Business Recommendations

Based on the observed patterns, the business could:

- Investigate the drivers of the September–November sales increase.
- Monitor performance in the UK while evaluating opportunities in other markets.
- Explore retention strategies for high-value customers.
- Review high-performing products to support inventory and promotional planning.
- Improve the capture of customer identifiers to strengthen customer-level reporting.
- Continue monitoring unusual transactions to distinguish genuine demand from data or operational anomalies.

These recommendations identify areas for further investigation; the analysis does not establish the causes of the observed patterns.

## Project Deliverables

- **Jupyter Notebook:** Data cleaning, validation, exploratory analysis, calculations, and visualisations.
- **Cleaned CSV:** `OnlineRetail_cleaned.csv`
- **Insight Report:** `ecommerce_eda_insight_report.pdf`

## Repository Structure

```text
data-cleaning-eda/
├── data/
│   └── OnlineRetail_cleaned.csv
├── notebooks/
│   └── 01_ecommerce_data_cleaning_eda.ipynb
├── reports/
│   └── ecommerce_eda_insight_report.pdf
├── .gitignore
└── README.md
```

## Conclusion

This project demonstrates practical data analytics skills across data profiling, data cleaning, validation, exploratory data analysis, KPI development, data visualisation, and business insight communication.

It highlights the importance of investigating data quality issues, understanding the business meaning of transaction records, validating analytical assumptions, and communicating findings with appropriate limitations.

The resulting dataset provides a stronger foundation for further sales, product, market, and customer analysis.
