# Data Modeler – Building a Normalized Star Schema Data Model

## 📌 Project Overview
This project focuses on building a clean and optimized **Star Schema Data Model** in Power BI using Power Query and Model View.

The main objective of this project was to transform multiple raw datasets into a structured relational model that supports efficient reporting and analysis.

The project includes:
- Data cleaning and transformation
- Building fact and dimension tables
- Creating relationships manually
- Applying proper cardinality
- Implementing hierarchies
- Handling inactive relationships
- Optimizing model structure

---

# 🛠 Tools Used
- Power BI Desktop
- Power Query
- Model View

---

# 📂 Dataset Tables

## 1. Sales Lookup
Main transactional fact table containing sales records.

### Columns:
- SalesID (PK)
- CustomerID (FK)
- ProductID (FK)
- RegionID (FK)
- DateKey (FK)
- Quantity
- Revenue
- Discount

---

## 2. Customer Lookup
Contains customer-related information.

### Columns:
- CustomerID (PK)
- FullName
- Age
- Gender
- Segment

---

## 3. Product Lookup
Contains product details.

### Columns:
- ProductID (PK)
- ProductName
- Category
- Subcategory
- Brand

---

## 4. Region Lookup
Contains geographical information.

### Columns:
- RegionID (PK)
- Country
- State
- City

---

## 5. Date Lookup
Contains date intelligence data.

### Columns:
- DateKey (PK)
- Date
- Month
- Quarter
- Year
- Fiscal Year

---

## 6. Returns Lookup
Contains returned product records.

### Columns:
- ReturnID (PK)
- SalesID (FK)
- ReturnDateKey (FK)
- Reason

---

# 🔑 Primary Key & Foreign Key Explanation

## Primary Key (PK)
A Primary Key is a unique column used to identify each record in a table.

### Example:
- CustomerID in Customer Lookup
- ProductID in Product Lookup
- RegionID in Region Lookup

Primary Keys:
- Cannot contain duplicate values
- Cannot contain blank values
- Uniquely identify rows

---

## Foreign Key (FK)
A Foreign Key is a column used to connect one table with another table.

Foreign Keys create relationships between fact and dimension tables.

### Example:
- CustomerID in Sales Lookup connects with Customer Lookup
- ProductID in Sales Lookup connects with Product Lookup

---

# 🔗 Relationships Created

| From Table | Column | To Table | Column | Relationship Type |
|---|---|---|---|---|
| Customer Lookup | CustomerID (PK) | Sales Lookup | CustomerID (FK) | One-to-Many |
| Product Lookup | ProductID (PK) | Sales Lookup | ProductID (FK) | One-to-Many |
| Region Lookup | RegionID (PK) | Sales Lookup | RegionID (FK) | One-to-Many |
| Date Lookup | DateKey (PK) | Sales Lookup | DateKey (FK) | One-to-Many |
| Sales Lookup | SalesID (PK) | Returns Lookup | SalesID (FK) | One-to-Many |
| Date Lookup | DateKey (PK) | Returns Lookup | ReturnDateKey (FK) | One-to-Many |

---

# ⚙️ Schema Design

## Star Schema Implementation
The model was designed using a Star Schema approach where:
- Dimension tables surround the fact table
- Fact tables store transactional data
- Dimension tables store descriptive attributes

### Benefits:
- Better readability
- Faster reporting
- Easier filtering
- Improved performance

---

# 📊 Relationship Settings

## Cardinality
Used:
- One-to-Many (1:*)

### Example:
One customer can have multiple sales transactions.

---

## Cross Filter Direction
Used:
- Single Direction

Reason:
- Improves performance
- Avoids ambiguity issues

---

# 🧩 Hierarchies Created

## Date Hierarchy
Created inside Date Lookup:
- Year
- Quarter
- Month
- Date

---

## Product Hierarchy
Created inside Product Lookup:
- Category
- Subcategory
- ProductName

---

# 🎨 Data Formatting Applied

Formatting used for:
- Currency values
- Whole numbers
- Dates

---

# ✅ Validation & Testing

The model was validated using Matrix visuals and report testing.

### Testing Performed:
- Sales by Product Category
- Revenue by Customer Segment
- Returns by Fiscal Year
- Region-wise Sales Analysis

All relationships and filters worked correctly.

---

# 📈 Key Learnings

- Understanding Star Schema modeling
- Working with Power Query
- Creating relationships manually
- Handling inactive relationships
- Building hierarchies
- Optimizing Power BI data models

---
