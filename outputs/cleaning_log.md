# Data Cleaning Log

## Task 5 - Apply Business Rules

### Rule 1: Missing Region
- Action: Filled missing values with "Unknown".
- Records affected: 25

### Rule 2: Missing Ship Mode
- Action: Filled missing values with "Unknown".
- Records affected: 21

### Rule 3: Missing Discount
- Action: Missing discount values were replaced with 0 because all related sales fields were valid.
- Records affected: 18

### Rule 4: Negative Discount
- Action: Negative discount values were identified and flagged as invalid.
- Records affected: 15

### Rule 5: Discount Above Allowed Range
- Action: Checked for discount values greater than 1.
- Records affected: 0

### Rule 6: Ship Date Before Order Date
- Action: Records where ship_date was earlier than order_date were flagged as "Invalid Shipping".
- Records affected: 80

### Rule 7: Cancelled Orders
- Action: Cancelled orders were retained in the dataset but excluded from completed sales summaries.

### Rule 8: Failed Payments
- Action: Failed payment orders were retained in the dataset but excluded from completed sales summaries.

### Rule 9: Refunded Orders
- Action: Refunded orders were retained and will be reported separately in the final summary.
