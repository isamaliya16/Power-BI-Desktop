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

### **1. Sales_Fact.xlsx**
- SalesID (PK)  
- CustomerID (FK)  
- ProductID (FK)  
- RegionID (FK)  
- DateKey (FK)  
- Quantity  
- Revenue  
- Discount  

### **2. Customer_Dim.xlsx**
- CustomerID (PK)  
- FullName  
- Age  
- Gender  
- Segment  

### **3. Product_Dim.xlsx**
- ProductID (PK)  
- ProductName  
- Category  
- Subcategory  
- Brand  

### **4. Region_Dim.xlsx**
- RegionID (PK)  
- Country  
- State  
- City  

### **5. Date_Dim.xlsx**
- DateKey (PK)  
- Date  
- Month  
- Quarter  
- Year  
- Fiscal Year  

### **6. Returns_Fact.xlsx**
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

---

### **2. Schema Design**
- Design a **Star Schema** with **Sales_Fact** as the central fact table  
- Model Returns_Fact as:
  - A separate fact table **or**
  - Part of a Snowflake schema  

Demonstrate understanding of:
- 1:Many  
- Many:1  
- 1:1  

---

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

## 🎯 Deliverables

A single **Power BI (.pbix)** file containing:
- All Power Query transformations  
- Complete Star/Snowflake model  
- Validated relationships  
- Defined hierarchies and clean fields  
- Matrix visuals for verification  

---