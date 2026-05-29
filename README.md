# DECODLABS-PROJECT-1.DATA-CLEANING

## 🧹 Data Cleaning & Preparation

Before conducting the Exploratory Data Analysis (EDA), the raw dataset underwent a rigorous data cleaning to ensure data integrity, consistency, and accuracy. Below are the specific steps taken to prepare the data for analysis:

### 1. Handling Missing & Null Values
* **Analysis:** Evaluated the dataset for any missing fields across all 14 columns. 
* **Action:** Found that the `CouponCode` column contained missing values (309non-null out of 1,200 rows). Since a missing coupon code implies that the customer simply did not use a discount code during checkout, these missing values replaced with No coupon rather than being dropped, preserving the entire 1,200-row sample size.

### 2. Standardizing Data Types & Formats
To ensure calculations and time-series analyses function properly, data types were explicitly cast:
* **Temporal Tracking:** Transformed the `Date` column from a generic text string format into a standardized `YYYY-MM-DD` DateTime format.
* **Text Uniformity:** Standardized text fields like `Product`, `PaymentMethod`, `OrderStatus`, and `ReferralSource` to eliminate any hidden leading or trailing spaces that could skew categorical counts.
* ***Numerical Layouts:* Verified that quantitative metrics (Quantity, ItemsInCart) were structured as integers, while financial values (UnitPrice, TotalPrice) were formatted as  decimals.

### 3. Verification of Calculated Columns
* **Cross-Check:** Verified that the total order amount matched the core calculation: 
  $$\text{TotalPrice} = \text{Quantity} \times \text{UnitPrice}$$
  This step ensured that any applied discounts or raw pricing details reflected correct, error-free row-level valuations across the entire e-commerce dataset.

### 4. Deduplication
* **Action:** Scanned the dataset for exact duplicate records across primary keys, specifically evaluating unique identifiers like `OrderID`, `CustomerID`, and `TrackingNumber`. 
* **Result:** No duplicate entries were found, confirming that each row represented a unique, standalone customer transaction.

---
