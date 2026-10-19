<div align="center">

# 🐼 Panda Market — Retail Analytics & Business Intelligence Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-0078D4?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Data Modeling](https://img.shields.io/badge/Schema-Star%20Schema-2EA44F?style=for-the-badge)](#-data-model--architecture)

<p align="center">
  <b>A comprehensive, interactive Power BI report transforming multi-regional retail sales data into actionable strategic insights.</b>
  <br />
  <i>Track, Manage, Grow — Your Panda World in One Screen.</i>
</p>

<!-- Live Animated Walkthrough -->
<img src="demo.gif" alt="Panda Dashboard Walkthrough" width="100%" />

</div>

---

## 📌 Project Overview
The **Panda Market Analytics Dashboard** provides management with a 360-degree view of retail performance:
- **Financial Health:** Revenue, product cost structures, and operating profit margins.
- **Product Velocity:** Fast-moving items vs. high-margin categories.
- **Customer Segmentation:** Purchasing behavior across demographics, gender split, and quarterly trends.
- **Geographic Penetration:** Performance across 4 countries, multiple states, and top cities.

---

## 📑 Report Structure & Modules

| # | Page | Core Focus | Key Visualizations |
|---|------|------------|---------------------|
| 1 | **Home Page** | Brand landing & routing | Seamless navigation portal to all analytical modules |
| 2 | **Sales Overview** | High-level sales performance | KPI cards, category column chart, top products, sales gauge |
| 3 | **Products** | Margins & product-level trends | Product profit margin ranking, subcategory revenue, Top 5 products |
| 4 | **Customers** | Demographic & time-based analysis | Sales by Location ID, quarterly trend line, gender split, revenue by region |
| 5 | **Location Overview** | Macro-to-micro geographic breakdown | Country distribution, continental revenue share (Donut), top states, city sales |

---

## 🗄️ Data Model (Star Schema)

Built using a star schema architecture with 1 Fact table and 7 Dimension tables:
- **Fact Table:** `Fact_Sales`
- **Dimension Tables:** `Dim_Product`, `Dim_Category`, `Dim_SubCategory`, `Dim_Customer`, `Dim_Country`, `Dim_Location`, `Dim_Date`

---

## 📐 Key DAX Measures

```dax
-- Total Revenue
Total Sales = SUM(Fact_Sales[TotalAmount])

-- Total Volume Sold
Total Quantity = SUM(Fact_Sales[Quantity])

-- Distinct Invoices Count
Total Orders = DISTINCTCOUNT(Fact_Sales[InvoiceNo])

-- Average Order Value (AOV)
AOV = DIVIDE([Total Sales], [Total Orders], 0)

-- Cost of Goods Sold (COGS)
Total Cost = 
SUMX(
    Fact_Sales, 
    Fact_Sales[Quantity] * RELATED(Dim_Product[Cost])
)

-- Net Operating Profit
Total Profit = [Total Sales] - [Total Cost]

-- Profit Margin Ratio
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
