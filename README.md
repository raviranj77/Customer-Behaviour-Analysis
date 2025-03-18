# 📊 Customer Behaviour Analysis Dashboard – Power BI

This project showcases a **Customer Behaviour Analysis Dashboard** built using Power BI to provide data-driven insights into customer trends, engagement patterns, and retention. The dashboard helps business users identify **New vs Repeat Customers**, analyze **monthly order patterns**, and make informed decisions to boost customer satisfaction and sales performance.

---

## 🧠 Project Objectives

- Analyze customer purchasing behavior using historical order data
- Identify and visualize **New vs Repeat Customers** over time
- Track key performance indicators (KPIs) to support customer retention strategies
- Provide actionable insights to sales and marketing teams

---

## 📌 Key Features

- **New vs Repeat Customers (Monthly)**:
  - Stacked column chart displaying monthly customer type split
  - DAX logic to classify new and repeat customers based on first purchase date

- **Customer Segmentation**:
  - Dynamic visuals segmenting customers by behavior and purchase frequency

- **Time Intelligence**:
  - Monthly breakdown with interactive date slicers to explore trends over time

- **KPI Cards & Visuals**:
  - Metrics such as Total Customers, Repeat Rate, New Customer Growth

---

## ⚙️ Tools & Technologies

- **Power BI**
- **DAX (Data Analysis Expressions)**
- **Power Query (M)**
- **Excel (Source Data)**

---

## 📂 Files Included

- `Customer Behaviour Dashoard2.pbix` – Power BI Dashboard file
- `DAX_Formulas.txt` – Key DAX expressions used for New/Repeat customer classification and KPIs

---

## 🔍 DAX Highlight: New vs Repeat Logic

```dax
FirstPurchaseDate = 
CALCULATE(
    MIN('Orders'[OrderDate]),
    ALLEXCEPT('Orders', 'Orders'[CustomerID])
)

CustomerType = 
IF(
    'Orders'[OrderDate] = 'Orders'[FirstPurchaseDate],
    "New",
    "Repeat"
)
