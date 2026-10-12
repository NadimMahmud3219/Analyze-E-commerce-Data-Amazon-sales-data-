# Analyze-E-commerce-Data-Amazon-sales-data-
Exploratory data analysis of Amazon e-commerce sales data using Python, Pandas, NumPy, Matplotlib, and Seaborn. This project explores sales performance, product categories, order cancellations, fulfilment methods, revenue trends, and customer geographic patterns to uncover actionable business insights.
# Amazon E-commerce Sales Analysis

## Project Overview

This project explores an Amazon e-commerce sales dataset using Python and Pandas to understand sales performance, product demand, order cancellations, and fulfilment patterns.

The goal is to transform raw sales data into meaningful business insights that can support better decision-making in revenue management, product performance, and order fulfilment.

The analysis is performed in Google Colab using Python, Pandas, NumPy, Matplotlib, and Seaborn.

## Objectives

- Clean and prepare the raw e-commerce dataset for analysis.
- Investigate missing values and duplicate records.
- Analyze order status distribution and cancellation rates.
- Examine monthly sales and cancellation trends.
- Identify high-performing product categories and SKUs.
- Compare revenue, quantity sold, and order counts across categories.
- Calculate average order value (AOV).
- Explore geographic sales distribution by state.
- Compare Amazon and merchant fulfilment performance.
- Analyze sales patterns across product sizes and B2B/B2C orders.

## Dataset

**Dataset:** Amazon Sale Report

The dataset contains order-level and product-level information, including:

| Column | Description |
|---|---|
| `Order ID` | Unique identifier for an order |
| `Date` | Order date |
| `Status` | Order status |
| `Fulfilment` | Fulfilment method |
| `Sales Channel` | Sales platform or channel |
| `Category` | Product category |
| `SKU` | Stock Keeping Unit identifier |
| `Qty` | Quantity associated with the record |
| `Amount` | Recorded order amount |
| `ship-state` | Customer shipping state |
| `ship-city` | Customer shipping city |
| `Size` | Product size |
| `B2B` | Indicates whether the order is a business order |

The original dataset contains 128,975 rows and 24 columns. An unnecessary column, `Unnamed: 22`, was removed during data cleaning.

*Note: The dataset's source and licensing details should be documented separately if required by the original publisher.*

## Tools and Technologies

- **Python** — Data analysis and processing
- **Pandas** — Data manipulation and aggregation
- **NumPy** — Numerical operations
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualization
- **Google Colab** — Notebook environment
- **Google Drive** — Dataset storage and access

## Project Workflow

### 1. Data Understanding

- Inspected the dataset dimensions, columns, and data types.
- Examined order statuses, product categories, fulfilment methods, and sales channels.
- Checked duplicate records and missing values.

### 2. Data Cleaning

- Converted the `Date` column to datetime format.
- Removed the unnecessary `Unnamed: 22` column.
- Checked for duplicate rows.
- Calculated missing-value percentages for each column.
- Investigated missing `Amount` values and their relationship with order statuses.

Missing amounts were concentrated among cancelled orders. These values were investigated rather than automatically replaced with zero.

### 3. Order Status and Cancellation Analysis

- Examined the distribution of order statuses.
- Calculated the cancellation rate.
- Compared cancellation rates across product categories.
- Compared cancellation rates between Amazon and merchant fulfilment.
- Examined monthly cancellation trends.
- Investigated cancellation rates by category and fulfilment method.

### 4. Revenue Analysis

A separate `revenue_df` dataset was created using the following statuses:

- `Shipped`
- `Shipped - Delivered to Buyer`
- `Shipped - Picked Up`

The analysis then explored:

- Monthly revenue trends.
- Revenue by product category.
- Revenue, quantity, and order counts by category.
- Average order value by category.

**Important:** This status-based selection is an initial analytical definition, not a verified accounting measure of realized revenue. Returned orders, refunds, delivery outcomes, and missing amounts should be reviewed before reporting final revenue figures.

### 5. Geographic Analysis

- Ranked states by recorded sales amount.
- Compared states by the number of distinct orders.
- Explored geographic differences in sales performance.

### 6. Product Performance Analysis

- Identified top-performing SKUs by revenue.
- Compared revenue, quantity, and order counts.
- Examined sales by product size.

### 7. B2B vs. B2C Analysis

- Compared revenue between business and non-business orders.
- Compared order counts and quantities.
- Calculated average order value for each segment.

## Key Findings

The notebook has identified several preliminary observations:

- **Cancellation rate:** Approximately 14.21% of dataset rows have a `Cancelled` status.
- **Fulfilment performance:** Merchant-fulfilled records have a cancellation rate of approximately 17.47%, compared with 12.79% for Amazon-fulfilled records.
- **Missing amounts:** Approximately 97% of records with missing `Amount` values are associated with cancelled orders.
- **Category revenue:** Set and Kurta are identified as leading revenue-generating categories in the current analysis.
- **Average order value:** Saree is identified in the notebook as generating the highest revenue per order.

These findings should be validated against the complete analysis outputs before being used in business reporting. Cancellation rates currently represent the proportion of rows marked as cancelled, not necessarily the proportion of unique orders cancelled.

## Repository Structure

```text
amazon-ecommerce-sales-analysis/
│
├── E_commerce.ipynb
├── README.md
├── data/
│   └── Amazon Sale Report.csv
└── visualizations/
    ├── monthly-revenue.png
    ├── revenue-by-category.png
    └── monthly-cancellation-rate.png
```

The `data/` and `visualizations/` directories are suggested project structure elements. They can be added when the dataset and exported charts are organized locally.

## How to Run the Project

1. Clone or download this repository.
2. Open `E_commerce.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required libraries if they are not already available:

   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

4. Upload the dataset or mount Google Drive.
5. Update the CSV file path in the notebook to match your environment.
6. Run the notebook cells in order to reproduce the analysis.

## Future Improvements

- Validate the revenue calculation against delivered orders and return/refund information.
- Improve missing-value handling and document the treatment of each important column.
- Analyze cancellation rates using distinct order IDs.
- Investigate cancellation patterns by category, fulfilment method, and geographic region.
- Explore monthly revenue growth and seasonality.
- Identify top products by revenue, quantity, and order frequency.
- Build an interactive Power BI dashboard.
- Develop a concise set of business recommendations based on validated findings.

## Conclusion

This project demonstrates a practical application of exploratory data analysis to e-commerce sales data. It combines data cleaning, aggregation, visualization, and business-focused investigation to understand product performance, revenue patterns, and order cancellations.

The next stage is to validate the business metrics, strengthen the analysis, and present the findings through a polished dashboard and actionable recommendations.

## Author

**Nadim Mahmud**

Aspiring Data Analyst | Python | Pandas | Data Visualization | Business Analytics
