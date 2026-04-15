# 📊 Historical Enrollment Dashboard (Philippines)

---

## 📌 Project Overview
This project presents an **interactive Power BI dashboard** analyzing historical enrollment trends in the Philippine education system from **SY 2010–2011 to SY 2020–2021**.

The dashboard provides insights into:
- Enrollment trends over time  
- Distribution across education levels  
- Regional concentration of students  
- Sector contribution (Public, Private, SUCs/LUCs)  
- Senior High School strand dynamics  

---

## 🎯 Objectives
- Analyze long-term enrollment trends across education levels  
- Identify high-concentration regions  
- Evaluate sector dominance in education delivery  
- Examine grade-level and strand-level patterns  
- Provide insights into growth, decline, and structural changes  

---

## 🧰 Tools & Technologies
- **Power BI** – Dashboard design & visualization  
- **Power Query** – Data transformation  
- **DAX** – KPI calculations and time intelligence  
- **Excel / CSV** – Source data  

---

## 🗂️ Dataset
The dataset includes:
- Enrollment by Region, Grade Level, Education Level, and Sector  
- Senior High School strand-level data  
- Academic years from **2010–2021**

---

## 🔄 Data Transformation (Power Query)

**Key steps performed:**
- Standardized column names and data types  
- Unpivoted wide-format datasets into long format  
- Appended datasets across:
  - Elementary  
  - Junior High  
  - Senior High  
- Added a **Sector column** for unified filtering  
- Converted `AY_Start` into **Date format (`AY_Start_Date`)**  
- Cleaned categorical fields (Region, Grade, Strand)  

---

## 🧱 Data Modeling

The dashboard follows a **star schema design**:

### Fact Tables
- `f_Enrollment_By_Level`
- `f_SHS_Strand`

### Dimension Tables
- `Dim_Calendar`
- `Dim_Region`
- `Dim_Sector`
- `Dim_Education_Level`
- `Dim_Strand`

### Key Design Decisions
- Used `AY_Start_Date` for time intelligence  
- Structured relationships as **one-to-many (dimension → fact)**  
- Avoided redundant date tables for consistency  

---

## 📈 Key DAX Measures

### Total Enrollment
```DAX
Total Enrollment - All =
SUM(f_Enrollment_By_Level[Enrollment])
