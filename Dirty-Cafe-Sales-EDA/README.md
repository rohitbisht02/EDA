# Dirty Cafe Sales – Data Cleaning & Exploratory Data Analysis (EDA)

## Project Overview
This project documents the complete process of working with a messy real-world cafe sales dataset.
The work starts from **data cleaning**, moves into **data validation**, and then into **exploratory data analysis (EDA)**.

The goal was not to rush into charts, but to first understand the data properly, clean it safely, and
only then extract meaningful business insights.

---

## Dataset
The dataset (`dirty_cafe_sales.csv`) contains cafe transaction records such as:
- Transaction ID  
- Item sold  
- Quantity  
- Price per unit  
- Total spent  
- Payment method  
- Location  
- Transaction date  

The dataset contains incorrect data types, hidden missing values, and inconsistent entries.

---

## Process Followed

### 1. Initial Data Inspection
The first step was to understand the dataset:
- Viewed sample rows
- Checked column names and structure
- Verified data types
- Identified missing and invalid values

At this stage, **no changes were made** to the data.

---

### 2. Raw Data Preservation
Before any cleaning:
- A full copy of the original dataset was saved as a raw file

This ensures:
- Original data is always available
- All cleaning steps are traceable
- No irreversible changes are made

---

### 3. Cleaning Text (Categorical) Columns
For columns such as Item, Payment Method, and Location:
- Converted text to lowercase for consistency
- Removed extra spaces
- Identified placeholder values like `error`, `unknown`, `na`, `n/a`, blanks
- Replaced these placeholders with proper missing values (`NaN`)
- Created missing value indicator columns (1 = missing, 0 = not missing)

This made missing data explicit instead of hidden.

---

### 4. Cleaning Numeric Columns
For numeric columns such as Quantity, Price Per Unit, and Total Spent:
- Created backup copies of original values
- Converted columns to numeric format using safe conversion
- Invalid numeric values were converted to missing values
- Verified numeric ranges to ensure values were realistic

---

### 5. Logical Validation
A basic business rule was checked:
- **Total Spent = Quantity × Price Per Unit**

This ensured numeric data was logically consistent after cleaning.

---

## Exploratory Data Analysis (EDA)

### Key Questions Explored
The EDA focused on the following questions:
1. How much total revenue does the cafe generate?
2. Which items are sold most frequently?
3. Which items generate the most revenue?
4. How do customers prefer to pay?
5. How does missing data affect analysis?

---

### Key Observations
- The cafe generated approximately **₹88,952** in revenue.
- **9,960 valid transactions** were used for revenue analysis.
- Some items are sold frequently, but revenue contribution varies.
- Revenue is not evenly distributed across items.
- Payment methods are used almost equally among recorded transactions.
- A significant number of transactions are missing payment method data, which limits analysis.

---

## Visual Analysis
Visualizations were created to support the analysis, including:
- Revenue by item
- Sales count by item
- Payment method distribution
- Missing payment method impact

Example charts are included below.

---

## What Was Intentionally Not Done
- No rows were dropped globally.
- No missing values were guessed or filled.
- Row removal decisions were deferred to analysis time.

This approach avoids early data loss and bias.

---

## Final Output
Two datasets were produced:
- **Raw Dataset**: original, untouched data
- **Clean Dataset**: standardized missing values, corrected data types, validation checks

---

## Project Structure
Dirty-Cafe-Sales-EDA/
│
├── data/
│ ├── dirty_cafe_sales.csv
│ ├── cafe_sales_raw.csv
│ └── cafe_sales_clean.csv
│
├── notebooks/
│ ├── eda_dirty_cafe_sales.ipynb
│ └── analysis_dirty_cafe_sales.ipynb
│
├── images/
│ ├── revenue_by_item.png
│ ├── sales_by_item.png
│ ├── payment_method_distribution.png
│ └── payment_method_missing.png
│
└── README.md


---

## Next Steps
- Extend analysis with time-based trends
- Build a simple dashboard for business reporting
- Use the clean dataset for further modeling if required

---

## Summary
This project demonstrates a complete workflow from raw data inspection to
cleaning, validation, and exploratory analysis, with clear documentation
at every step.


