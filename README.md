<div align="center">

# 📊 Retail Sales Interactive Dashboard

**An interactive Excel dashboard built on 1,000 retail transactions**

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

**Author:** [Your Name] &nbsp;|&nbsp; **File:** `YourName_ExcelDashboard.xlsx`

</div>

---

## video
[![Play Video](https://img.shields.io/badge/▶%20Play-Video-success?style=for-the-badge)](https://drive.google.com/file/d/1DLl20xGPpQ72SVOb-ehCRyiAsJEVnF0y/view?usp=sharing)


## 🎯 Overview

This project turns raw retail transaction data into a dashboard that lets anyone explore sales by **product category**, **gender**, **age group** and **time period**, using slicers and a timeline, with no formulas needed.

---

## 🗂️ Dataset

**Source:** Retail Sales Dataset (Kaggle) &nbsp;•&nbsp; **Rows:** about 1,000

| Column | Description |
|---|---|
| `Transaction ID` | Unique ID of each sale |
| `Date` | Date of the transaction |
| `Customer ID` | Unique customer identifier |
| `Gender` | Customer gender |
| `Age` | Customer age |
| `Product Category` | Category of the product |
| `Quantity` | Units purchased |
| `Price per Unit` | Price of one unit |
| `Total Amount` | Quantity × Price per Unit |

**Columns added by me:** `Age Group`, `Order Size`, `Month`, `Year`

---

## 📁 Workbook Structure

| Sheet | Contents |
|---|---|
| 📘 `README` | Purpose, sheet guide and usage instructions |
| 🗃️ `Data` | Cleaned data stored as the Table `SalesData` |
| 🧮 `Pivots` | PivotTables that feed the charts and KPIs |
| 🔍 `Lookup` | VLOOKUP, INDEX-MATCH and nested formula demo |
| 📈 `Dashboard` | Final interactive view |

---

## ✨ Dashboard Features

| Feature | Details |
|---|---|
| **KPI Cards** | Total Sales, Total Transactions, Total Quantity |
| **Charts** | Column (category), Line (monthly trend), Donut (gender), Bar (age group) |
| **Slicers** | Product Category, Gender, Year |
| **Timeline** | Filter by date range |
| **Conditional Formatting** | Data Bars, Color Scales, Top 10 and text rules |
| **Dynamic Range** | `DynAmount` grows automatically with the data |

---

## 🧹 Data Preparation

- ✅ Removed duplicates using `Transaction ID`
- ✅ Checked and handled missing values
- ✅ Fixed data types (dates, whole numbers, currency)
- ✅ Converted the data into the Table `SalesData`

---

## 🧮 Key Formulas

```excel
Age Group    =IF([@Age]<25,"18-24",IF([@Age]<35,"25-34",IF([@Age]<50,"35-49","50+")))
Order Size   =IF([@[Total Amount]]>=1000,"High",IF([@[Total Amount]]>=300,"Medium","Low"))

VLOOKUP      =VLOOKUP(B3,SalesData[[Transaction ID]:[Total Amount]],9,FALSE)
INDEX-MATCH  =INDEX(SalesData[Customer ID],MATCH(B3,SalesData[Transaction ID],0))

Nested       =IFERROR(INDEX(SalesData[Total Amount],MATCH(B3,SalesData[Transaction ID],0)),"Not Found")
SUMIFS       =SUMIFS(SalesData[Total Amount],SalesData[Product Category],"Clothing",SalesData[Gender],"Female")
Dynamic      =OFFSET(SalesData[[#Headers],[Total Amount]],1,0,COUNTA(SalesData[Total Amount]),1)
```

---

## 🖱️ How to Use

1. Open the **Dashboard** sheet.
2. Click a **slicer** button to filter every chart and KPI. Hold `Ctrl` to select several values.
3. Drag the **Timeline** handles to focus on a period.
4. Click the **clear filter** icon on a slicer to reset it.
5. Press `Alt + F5` to refresh after changing the data.
6. To test the formulas, enter a Transaction ID in cell `B3` of the **Lookup** sheet.

---

## 💡 Key Insights

- Top category: **[category]** with **[amount]** in sales
- Best month: **[month]**
- Largest customer group: **[age group]**

---

## ✅ Task Coverage

| # | Task | Weight | Location |
|:-:|---|:-:|---|
| 1 | Dataset Selection and Import | 5% | `Data` |
| 2 | Data Cleaning and Preparation | 10% | `Data` |
| 3 | Create Pivot Tables | 15% | `Pivots` |
| 4 | Advanced Formulas | 15% | `Data`, `Lookup` |
| 5 | Data Visualization | 20% | `Dashboard` |
| 6 | Interactive Dashboard | 25% | `Dashboard` |
| 7 | Documentation | 10% | `README` |
