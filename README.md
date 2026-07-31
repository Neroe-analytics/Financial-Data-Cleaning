# Financial-Data-Cleaning
Tools Used - SQL For data cleaning, validation, and transformation
# Financial Data Reconciliation & Cleaning Project - SQL

## Project Overview
Cleaned and reconciled a 2,000+ row financial dataset to ensure data accuracy for reporting. Removed duplicate transactions, standardized company/vendor names, and validated amounts to support month-end close and prevent reporting errors.

## Business Problem
Raw financial data contained duplicate entries, inconsistent company names, and missing values which could lead to errors in financial reporting and reconciliation.

## Tools Used
- **SQL**: For data cleaning, validation, and transformation

## Key Accounting/Finance Tasks Completed

### 1. **Duplicate Transaction Removal**
Identified and removed duplicate financial records to ensure accurate totals for reporting.
```sql
WITH DuplicateCheck AS(
SELECT *, ROW_NUMBER() OVER(PARTITION BY company, total_laid_off, percentage_laid_off, date) AS row_num
FROM layoffs
)
DELETE FROM Duplicate Check WHERE row_num > 1;


2. Data Standardization Standardized
company names and industry fields for consistent reporting
-- 3 Null Value Treatment & Data Validation Handled missing values in critical fields like company, industry, and date to maintain data integrity
-- 4. Data Type Correction Converted text dates and percentage columns to proper DATE and DECIMAL formats for accurate financial calculations.
-- Results & Impact
Reduced data errors: Cleaned dataset from 2,361 rows to 2,289 accurate records
Improved reporting accuracy: Ensured 100% of amount fields are valid for reconciliation
Prepared data for analysis: Final dataset ready for expense tracking and variance analysis


## Files in this repo
- `raw_financial_transactions.csv` - Original dirty data
- `cleaned_financial_transactions.csv` - Final cleaned data  
