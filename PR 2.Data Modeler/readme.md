# Data Modeler - Building a Normalized Star Schema Data Model

## 📌 Project Objective
The objective of this project is to build a well-structured **relational data model** in Power BI using multiple normalized tables.  
This project demonstrates understanding of:

- Table relationships  
- Cardinality  
- Star vs. Snowflake schemas  
- Handling inactive or ambiguous relationship paths  
- Data categories & hierarchies  

All logic is implemented using **Power Query** and **Model View** only.

---

## 📂 Dataset Overview

### [1. Sales_Fact.xlsx](./Dataset/Sales_Fact.xlsx)

- SalesID (PK)  
- CustomerID (FK)  
- ProductID (FK)  
- RegionID (FK)  
- DateKey (FK)  
- Quantity  
- Revenue  
- Discount  

### [2. Customer_Dim.xlsx](./Dataset/Customer_Dim.xlsx.xlsx)
- CustomerID (PK)  
- FullName  
- Age  
- Gender  
- Segment  

### [3. Product_Dim.xlsx](./Dataset/Product_Dim.xlsx)
- ProductID (PK)  
- ProductName  
- Category  
- Subcategory  
- Brand  

### [4. Region_Dim.xlsx](./Dataset/Region_Dim.xlsx)
- RegionID (PK)  
- Country  
- State  
- City  

### [5. Date_Dim.xlsx](./Dataset/Date_Dim.xlsx)
- DateKey (PK)  
- Date  
- Month  
- Quarter  
- Year  
- Fiscal Year  

### [6. Returns_Fact.xlsx](./Dataset/Returns_Fact.xlsx)
- ReturnID (PK)  
- SalesID (FK → Sales_Fact)  
- ReturnDateKey (FK → Date_Dim)  
- Reason  

---

## 🛠️ Project Tasks

### **1. Model Construction & Relationships**
- Import all Excel sheets through **Power Query**  
- Clean data (types, blanks, formatting)  
- Load cleaned tables to the data model  
- Define all PK–FK relationships manually  

#### Relationships:
- Sales_Fact → Customer_Dim  
- Sales_Fact → Product_Dim  
- Sales_Fact → Region_Dim  
- Sales_Fact → Date_Dim  
- Returns_Fact → Sales_Fact  
- Returns_Fact → Date_Dim (*inactive relationship for ReturnDateKey*)  

![Sales & Returns Matrix](image/model%20view.png) 
---

### **2. Schema Design**
- Design a **Star Schema** with **Sales_Fact** as the central fact table  
- Model Returns_Fact as:
  - A separate fact table **or**
  - Part of a Snowflake schema  

### Demonstrate understanding of:
## ⭐ 1:Many (One-to-Many)
Definition:
One record in Table A is linked to many records in Table B.
- Example (in your schema):
- Product_Dim (1) → Sales_Fact (Many)
- One product can appear in many sales transactions.
- Customer_Dim (1) → Returns_Fact (Many)
- One customer can return many items.

## ⭐ Many:1 (Many-to-One)

This is the reverse of 1:Many (in Power BI, direction is usually Many → 1).
- Example:
- Sales_Fact (Many) → Date_Dim (1)
- Many sales happen on one date.
- Returns_Fact (Many) → Product_Dim (1)
- Many returns can happen for the same product.

## ⭐ 1:1 (One-to-One)
- Definition:
One record in Table A corresponds to exactly one record in Table B.
- Example scenarios:
- Sales_Fact and Invoice_Fact when each sale has exactly one invoice.
- Customer_Dim and Customer_Details_Dim if you split a large dimension table.
-Power BI Note:
1:1 relationships are rare and used only when logically correct.---

### **3. Advanced Model Settings**
- Set correct cardinalities  
- Use **single-direction cross-filtering** (preferred)  
- Enable bi-directional filtering only when necessary  
- Handle inactive relationships using **USERELATIONSHIP()**  
- Resolve ambiguous filtering paths  

---

### **4. Data Model Enhancements**

#### ✔ Apply Proper Data Formats
- Currency → Revenue, Discount  
- Whole Number → Quantity  
- Date → Date fields  

#### ✔ Data Categories
- City  
- Country  
- Product Name  

#### ✔ Build Hierarchies
- **Date_Dim:** Year → Quarter → Month → Date  
- **Region_Dim:** Country → State → City  
- **Product_Dim:** Category → Subcategory → ProductName  

---

## 📊 Verification Step (Matrix Table Only)

Create a Matrix visual to verify:

- Sales by **Product Category** & **Region**  
- Return reasons by **Fiscal Year**  
- Revenue by **Customer Segment**  

---
![Sales & Returns Matrix](image/Report%20View.png)
---

## 🎯 Deliverables

A single **Power BI (.pbix)** file containing:
- All Power Query transformations  
- Complete Star/Snowflake model  
- Validated relationships  
- Defined hierarchies and clean fields  
- Matrix visuals for verification  

---