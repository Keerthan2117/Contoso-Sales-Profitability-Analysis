Data Cleaning and Preparation

Overview

The Contoso dataset was prepared in Power Query before building the Power BI data model. The focus was on correcting data types, handling missing information, and preparing the tables for analysis.

Data Preparation Steps

1. Data Types

- Reviewed column data types across the Sales, Product, Customer, Store, and Date tables.
- Converted price and cost columns to appropriate numeric types.
- Changed the customer ZIP code column to Text because postal codes are identifiers rather than quantities.

2. Customer Data

- The ZIP code conversion initially produced errors when the column was treated as numeric.
- Changed the column to Text to preserve postal-code values and avoid numeric conversion issues.
- Retained the customer records rather than deleting rows because of these conversion errors.

3. Store Data

- Reviewed missing values in the Store table's CloseDate and Status columns.
- Where both CloseDate and Status were missing or blank, assigned the status Operational.
- This was a data-preparation rule, not an independent confirmation of each store's current operating status.

4. Product Data

- Checked ProductKey and ProductCode for uniqueness.
- Converted price and cost fields to numeric data types where appropriate.

5. Validation

- Reviewed key columns and relationships before building the model.
- Kept the Date table extending into 2026, even though the available Sales data ends in 2025.
- Used the report's date filters to focus analysis on periods with sales.

Notes and Limitations

- Sales records include a StoreKey value of "999999". This key should be investigated to confirm whether it represents an online channel, an unknown store, or another business rule before making assumptions about it.
- CurrencyCode and ExchangeRate are present in the Sales data. Currency aggregation and reporting denomination should be confirmed before assigning a currency symbol to financial measures.

Tools

- Power Query in Power BI
- Data type conversion
- Missing-value handling
- Data validation
