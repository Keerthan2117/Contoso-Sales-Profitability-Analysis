*Data Model

*Overview

The Contoso Power BI report uses a star schema, with the Sales table as the central fact table and Product, Customer, Store, and Date as dimension tables.

This structure supports sales, profitability, customer, and geographic analysis while keeping relationships clear and easy to maintain.

*Tables

- Sales: Contains order-level line items, quantities, prices, costs, dates, and keys linking transactions to the dimensions.
- Product: Contains product information used for product-level sales and profitability analysis.
- Customer: Contains customer details used to analyse customer revenue and concentration.
- Store: Contains store information used for geographic and store-level analysis.
- Date: Provides calendar dates for monthly, quarterly, yearly, and time-intelligence calculations.

*Relationships

The model uses one-to-many relationships from each dimension to Sales, with single-direction filtering.

Dimension table| Dimension key| Sales key| Cardinality
Product| ProductKey| ProductKey| One-to-many
Customer| CustomerKey| CustomerKey| One-to-many
Store| StoreKey| StoreKey| One-to-many
Date| Date| OrderDate| One-to-many

*Why This Model?

- Allows users to analyse Sales by product, customer, store, and date.
- Supports consistent filtering across report pages.
- Reduces unnecessary complexity compared with connecting every table directly to every other table.
- Supports DAX measures and time-based comparisons.

*Date Table

The Date table extends into 2026, while the available Sales data runs from 18 May 2016 to 31 December 2025. The report focuses on periods with sales, without removing future dates from the calendar table.

Validation

*Before using the report, the relationships were checked for the expected keys, cardinalities, and filter directions. The StoreKey value "999999" in Sales remains an item to investigate before assigning it a specific business meaning.
