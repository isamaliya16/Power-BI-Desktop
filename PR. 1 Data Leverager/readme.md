
# 📊 Data Leverager - Power Query Transformation Project

## 🔥 Objective
Simulate a real data engineering workflow using **Power BI Power Query Editor** by extracting, cleaning, reshaping, merging, and analyzing data from multiple sources.

---

## ✅ 1. Data Extraction
### **HTML Table (Web Source)**
- Load a table directly from a web page such as:
  - Country-wise GDP (Wikipedia)
  - COVID statistics
- Use **Get Data → Web → URL**  
- Select the required HTML table.

### **Excel Files (Folder Source)**
Files:
- `Sales_Jan.xlsx`
- `Sales_Feb.xlsx`
- `Sales_Mar.xlsx`

Steps:
1. Go to **Get Data → Folder**
2. Select folder containing all three files
3. Combine & Transform → Auto detect
4. Append using **Append Queries**

### **Employee Dataset**
- Load employee Excel file with fields:
  - EmployeeID  
  - Name  
  - Department  
  - Region  
  - Join Date  

---

## ✅ 2. Basic Transformations
- Remove blank rows & columns  
- Promote first row to headers  
- Rename columns  
- Apply **Data Types** correctly using **Change Type with Locale** for:
  - Currency  
  - Dates  
- Remove duplicates  
- Filter null values  

---

## ✅ 3. Text Tools
Use:
- `UPPER()`, `LOWER()`
- `TRIM()`, `CLEAN()`
- `REPLACE VALUE`
- `Split Column by Delimiter`

Used for cleaning:
- Customer Names  
- Address Fields  

---

## ✅ 4. Numeric Tools
- Round revenue columns to **2 decimals**  
- Create column:
Profit = Revenue - Cost


---

## ✅ 5. Date & Time Tools
From **Order Date**, extract:
- Day  
- Month  
- Year  
- Quarter  

Add:
- Custom **Fiscal Month**
- Age column from Birthdate

---

## ✅ 6. Conditional Columns & Indexing
### **Sales Category Logic**
- High → ≥ 10,000  
- Medium → 5,000–9,999  
- Low → < 5,000  

### **Index Columns**
- Index starting from 0  
- Index starting from 1  

---

## ✅ 7. Pivoting & Unpivoting
- Pivot monthly columns into a single column  
- Unpivot again to normalize data  

---

## ✅ 8. Merging & Appending
### **Merge Queries**
- Merge Sales Data + Employee Data  
- Use:
- Region  
- EmployeeID  

### **Append Queries**
- Append Jan–Mar Sales  

---

## ✅ 9. Grouping & Aggregation
Group by **Region** to calculate:
- Total Sales  
- Average Order Value  
- Transaction Count  

---

## ✅ 10. Data Profiling & Quality
Using:
- Column Profile  
- Column Distribution  
- Column Quality  

Helps identify:
- Missing values  
- Errors  
- Distinct / Unique values  

---

## ✅ 11. Source Settings & Parameters
- Create Parameter for dynamic folder path  
- Configure credentials via **Data Source Settings**  

---

## ✅ 12. Refresh Simulation
- Add new file: `Sales_Apr.xlsx`
- Refresh queries  
- Verify Auto-load via folder connection  

---
