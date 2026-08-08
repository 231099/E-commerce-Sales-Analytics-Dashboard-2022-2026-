📊 Project Overview

This project analyzes an e-commerce sales dataset (originally 5,000 orders) covering order details, customer ratings, delivery performance, and revenue across product categories, regions, and payment methods. The goal was to clean and validate the raw data, then build a fully interactive Excel dashboard to explore sales trends, regional performance, and customer behavior.

Tools used: Microsoft Excel (Pivot Tables, PivotCharts, Slicers, Formulas)

🗂️ Files in this Repo
File	Description
ecommerce_sales_analytics_5000.csv	Original raw dataset (5,000 rows)
Ecommerce_Cleaned.xlsx	Cleaned dataset + pivot tables + dashboard
Dashboard.png	Final dashboard preview
🧹 Data Cleaning & Preparation Steps
Validated the revenue formula Recalculated revenue manually as (Quantity × Unit Price) − (Quantity × Unit Price × Discount) and added it as a new column, Revenue_Calculated, to cross-check against the existing revenue column. Confirmed the two matched (differences were only floating-point rounding), validating that the discount logic in the raw data was applied correctly.
Checked for duplicates Verified there were no duplicate rows and no duplicate order_id values in the dataset.
Checked data quality Confirmed there were no missing values, and that categorical fields (product_category, region, payment_method) had consistent, clean values with no typos or formatting inconsistencies.
Removed unrealistic future data The raw dataset contained sequential daily orders stretching from January 2022 all the way to September 2035. Since real order data wouldn't extend that far into the future, all rows from August 2026 onward were removed, narrowing the dataset to a realistic range (Jan 2022 – Jul 2026) and cutting the dataset from 5,000 to 1,673 rows.
Split the date column Converted order_date into three separate helper columns — Day, Month, and Year — using DAY(), TEXT(..., "mmm"), and YEAR() formulas, to make time-based grouping and slicing easier in pivot tables.
📈 Pivot Tables Built
Revenue by Product Category (with average customer rating)
Quantity and Revenue by Payment Method
Revenue and Order Volume by Region
Revenue by Month-Year (trend over time)
Average Customer Rating by Delivery Days
Top Customers by Revenue and Order Count
📊 Dashboard

The final dashboard combines six charts (bar charts, pie charts, and a time trend line) with slicers for Product Category, Region, Month, and Year — all connected via Report Connections so a single click filters every chart simultaneously.

Key visuals:

Revenue per Product Category
Customer Rating per Delivery Days
Total Revenue per Region
Number of Orders per Payment Method
Total Revenue per Month (2022–2026)
Number of Orders per Region
Total Revenue per Payment Method
![Dashboard](images/Dashboard.png)


🔍 Key Insights
Electronics generates the highest revenue among all product categories despite likely lower order volume than Clothing.
Card is the most-used payment method by both order volume and total revenue.
Regional performance is fairly balanced, with North and West slightly ahead of East and South.
Delivery speed doesn't show a strong linear relationship with customer rating in this dataset.
