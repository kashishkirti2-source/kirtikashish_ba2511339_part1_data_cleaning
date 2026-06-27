# Data Cleaning Log

## Task 5 - Apply Business Rules

### Rule 1: Missing Region

* **Action:** Filled missing values with **"Unknown"**.
* **Records affected:** 25

### Rule 2: Missing Ship Mode

* **Action:** Filled missing values with **"Unknown"**.
* **Records affected:** 21

### Rule 3: Missing Discount

* **Action:** Missing discount values were replaced with **0** because all related sales fields were valid.
* **Records affected:** 18

### Rule 4: Negative Discount

* **Action:** Negative discount values were identified and flagged as invalid.
* **Records affected:** 15

### Rule 5: Discount Above Allowed Range

* **Action:** Checked for discount values greater than **1**.
* **Records affected:** 0

### Rule 6: Ship Date Before Order Date

* **Action:** Records where **ship_date** was earlier than **order_date** were flagged as **"Invalid Shipping"**.
* **Records affected:** 80

### Rule 7: Cancelled Orders

* **Action:** Cancelled orders were retained in the dataset but excluded from completed sales summaries.

### Rule 8: Failed Payments

* **Action:** Failed payment orders were retained in the dataset but excluded from completed sales summaries.

### Rule 9: Refunded Orders

* **Action:** Refunded orders were retained and reported separately in the final summary.

---

## Issues Found

The following data quality issues were identified in the dataset:

* Missing Region values
* Missing Ship Mode values
* Missing Discount values
* Invalid Order Dates and Ship Dates
* Ship Dates earlier than Order Dates
* Negative Discount values
* Duplicate rows
* Duplicate Order IDs with conflicting information
* Missing Sales and Profit calculations caused by invalid source values

---

## Cleaning Actions Performed

The following cleaning steps were applied:

* Replaced missing Region values with **"Unknown"**
* Replaced missing Ship Mode values with **"Unknown"**
* Replaced missing Discount values with **0** wherever calculations were possible
* Identified and flagged invalid dates
* Flagged records where Ship Date occurred before Order Date
* Removed exact duplicate rows
* Retained duplicate Order IDs with conflicting information and flagged them for manual review
* Created the following calculated columns:

  * cleaned_discount
  * calculated_sales
  * calculated_profit
  * profit_margin
  * shipping_delay_days
  * order_month
  * order_year
  * data_quality_flag

---

## Assumptions Made

The following assumptions were used during data cleaning:

* Unknown Region and Ship Mode values were retained instead of deleting records.
* Missing Discount values were treated as **0** only when other required values were available.
* Invalid dates were preserved and flagged rather than corrected.
* Records with calculation errors were flagged instead of manually modified.

---

## Records Removed

* Exact duplicate rows removed: **20**

---

## Records Flagged

Data quality validation results:

* **Clean Records:** 545
* **Warning Records:** 30
* **Invalid Records:** 337

Records were flagged because of:

* Invalid dates
* Invalid shipping sequence
* Negative discount values
* Duplicate Order IDs
* Calculation-related issues

---

## Limitations

* Invalid dates could not be corrected because the original values were unavailable.
* Negative discount values were flagged instead of automatically corrected.
* Sales and Profit calculations remained blank where source values were insufficient.
* Duplicate Order IDs require manual verification.
* Some business assumptions were applied where original information was missing.
