# Data Cleaning Assignment

## Problem Summary

The objective of this assignment was to clean a raw sales dataset by identifying data quality issues, applying business rules, creating calculated columns, validating records, generating data quality reports, and preparing pivot summaries for business analysis.

---

# Dataset Description

The dataset contains sales order information including:

* Order ID
* Order Date
* Ship Date
* Customer Details
* Region
* State
* City
* Category
* Sub-Category
* Product Name
* Ship Mode
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Payment Status
* Order Status

The dataset initially contained missing values, duplicate records, invalid dates, incorrect discounts, and inconsistent shipping information.

---

# Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Formulas
* GitHub

---

# Cleaning Steps Performed

The following cleaning steps were completed:

* Filled missing Region values with **"Unknown"**
* Filled missing Ship Mode values with **"Unknown"**
* Replaced missing Discount values with **0** where applicable
* Removed exact duplicate rows
* Flagged duplicate Order IDs for review
* Identified invalid Order Dates and Ship Dates
* Flagged Ship Dates occurring before Order Dates
* Created calculated columns:

  * cleaned_discount
  * calculated_sales
  * calculated_profit
  * profit_margin
  * shipping_delay_days
  * order_month
  * order_year
  * data_quality_flag

---

# Business Rules Applied

* Missing Region → Unknown
* Missing Ship Mode → Unknown
* Missing Discount → 0 (when calculation was possible)
* Discount must be between 0 and 1
* Ship Date cannot be earlier than Order Date
* Cancelled, Failed, and Refunded orders were retained for reporting
* Duplicate Order IDs were flagged instead of deleted

---

# Summary of Data Quality Issues Found

| Issue                    | Records |
| ------------------------ | ------: |
| Missing Region           |      25 |
| Missing Ship Mode        |      21 |
| Missing Discount         |      18 |
| Negative Discount        |      15 |
| Invalid Shipping Records |      80 |
| Exact Duplicate Rows     |      20 |
| Duplicate Order IDs      |      24 |

Final Data Quality Status:

* Clean Records: **545**
* Warning Records: **30**
* Invalid Records: **337**

---

# Summary of Final Pivot Reports

The following pivot reports were created:

1. Sales & Profit by Region
2. Sales & Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded/Cancelled/Failed Orders by Region
6. Monthly Sales Trend

Sorting and filtering were applied to selected pivot tables for better analysis.

---

# Key Business Insights

* South region generated the highest overall sales.
* Technology and Furniture contributed significantly to revenue.
* Standard Class was the most frequently used shipping mode.
* Average profit margin remained close to 30% across all customer segments.
* Failed and Refunded orders were relatively low compared to completed transactions.
* Monthly sales varied throughout the year, with stronger performance in selected months.

---

# Assumptions and Limitations

## Assumptions

* Missing Region and Ship Mode values were replaced with **Unknown**.
* Missing Discount values were treated as **0** where calculations were possible.
* Invalid dates were preserved and flagged instead of being modified.
* Duplicate Order IDs were retained for manual review.

## Limitations

* Original values for invalid dates were unavailable.
* Negative discount values could not be corrected automatically.
* Some calculated fields remained blank due to missing source values.
* Manual verification is recommended for flagged records.

---

# Screenshots Included

The repository includes screenshots demonstrating:

* Business Rule implementation
* Cleaned Dataset
* Calculated Columns
* Data Quality Report
* Pivot Tables
* GitHub Repository Structure

---

# Project Structure

```
outputs/
│
├── cleaned_orders.xlsx
├── data_quality_report.xlsx
├── pivot_summary.xlsx
├── cleaning_log.md
└── README.md
```
