# Sales & Product Data Integration using Power BI

## Project Overview

This project demonstrates how to integrate transactional sales data with product master data using Power Query in Power BI.
The objective was to enrich sales records with descriptive product information by performing a Left Outer Join on `ProductKey`, followed by structured data validation and transformation to create a clean, reporting-ready dataset.
This project simulates a real-world data analyst task involving relational data merging and ETL preparation.

---
# Business Scenario
Adventure Works stores sales transaction data and product details in separate Excel files:

- `Sales.xlsx` – Contains transaction-level data  
- `Product.xlsx` – Contains product master data  

The Sales dataset contains only `ProductKey` (a numeric identifier) but does not include the actual Product Name.
Management required a final dataset containing:

- Sales Order Number  
- Order Date  
- Product Name  
- Quantity  
- Unit Price  

To achieve this, the Sales and Product tables were merged using `ProductKey`.
---

## Project Objectives

- Import and inspect raw datasets  
- Validate join key compatibility  
- Perform a Left Outer Join using Power Query  
- Expand and extract product information  
- Remove unnecessary foreign key columns  
- Reorder and structure the final dataset  
- Validate data integrity before loading to the model  

---
## Tools Used

- Power BI Desktop  
- Power Query Editor  
- Microsoft Excel  
---
## Step-by-Step Implementation

### 1. Data Import

- Imported `Sales.xlsx` and `Product.xlsx` into Power BI  
- Opened Power Query Editor for transformation  
---

### 2. Data Inspection & Validation
Before merging, the following checks were performed:

- Confirmed `ProductKey` exists in both tables  
- Verified `ProductKey` data type is Whole Number in both tables  
- Reviewed column structure and foreign keys  

This ensures join compatibility and prevents merge errors.
---

### 3. Merge Operation
Performed the following steps:
- Selected **Sales** table  
- Clicked **Merge Queries**  
- Selected **Product** as the second table  
- Selected `ProductKey` in both tables  
- Chose **Left Outer Join**

**Why Left Outer Join?**
A Left Join ensures:
- All sales records are retained  
- Matching product details are added where available  

Row count remains unchanged after the merge.

---

### 4. Expand Product Table
After merging:

- Expanded the Product column  
- Selected only required fields  
- Removed prefix naming for clarity  

This added the Product Name to the Sales dataset.

---

### 5. Data Cleaning
Removed unnecessary columns:

- ProductKey  
- ResellerKey  
- EmployeeKey  
- SalesTerritoryKey  
- Additional unused product attributes  

Renamed:
- `Product.Product` → `Product`

Reordered final columns to:

- SalesOrderNumber  
- OrderDate  
- Product  
- Quantity  
- Unit Price  
---
### 6. Data Validation (Pre-Load Checks)

To ensure data integrity, the following validations were performed:

- Compared row count before and after merge  
- Filtered Product column for null values  
- Performed spot checks on ProductKey mappings  
- Used temporary reference queries for row count validation  

These checks confirm the accuracy of the merge operation.
---
## Final Output Structure

The final dataset contains:

| Column Name        | Description |
|-------------------|-------------|
| SalesOrderNumber | Unique sales transaction ID |
| OrderDate        | Date of transaction |
| Product          | Product name (from Product table) |
| Quantity         | Units sold |
| Unit Price       | Price per unit |

The dataset is now ready for reporting and dashboard development.
---
## Key Concepts Demonstrated

- Relational Data Modeling  
- Join Keys  
- Left Outer Join  
- Data Type Standardization  
- Data Cleaning  
- Column Transformation  
- Data Validation  
- ETL Workflow in Power Query  
---

## Business Impact
This project demonstrates how transactional data can be enriched with master data to produce meaningful business reports.
Such integration allows organizations to:

- Analyze sales by product  
- Track product performance  
- Improve reporting accuracy  
- Build executive dashboards  
---

## Repository Structure
```
powerbi-sales-product-merge-analysis/
│
├── README.md
├── Sales.xlsx
├── Product.xlsx
├── Exercise – Merging two tables.pbix
└── Screenshots/
```
Author
Vidya Vishnuvihar Geetha
