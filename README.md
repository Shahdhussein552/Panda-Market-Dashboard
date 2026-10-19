<div align="center">

# 🐼 Panda Market — Retail Analytics & Business Intelligence Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-0078D4?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Data Modeling](https://img.shields.io/badge/Schema-Star%20Schema-2EA44F?style=for-the-badge)](#-data-model--architecture)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)

<p align="center">
  <b>A comprehensive, interactive Power BI report transforming multi-regional retail sales data into actionable strategic insights.</b>
  <br />
  <i>Track, Manage, Grow — Your Panda World in One Screen.</i>
</p>

</div>

---

## 📌 Project Overview

The **Panda Market Analytics Dashboard** provides management with a 360-degree view of retail performance. Built with custom navigation, dynamic bookmark-driven filter drawers, and robust DAX calculations, it enables stakeholders to evaluate:

- **Financial Health:** Revenue, product cost structures, and operating profit margins.
- **Product Velocity:** Fast-moving items vs. high-margin categories.
- **Customer Segmentation:** Purchasing behavior across demographics, genders, and quarterly cycles.
- **Geographic Penetration:** Performance across 4 countries, multiple states/governorates, and top cities.

---

## 📑 Report Structure & Modules

| # | Page | Core Focus | Key Visualizations |
|---|------|------------|---------------------|
| 1 | **Home Page** | Brand landing & routing | Navigation portal to all analytical modules |
| 2 | **Sales Overview** | High-level sales performance | KPI cards, category column chart, top products, sales gauge |
| 3 | **Products** | Margins & product-level trends | Product profit margin ranking, subcategory revenue, Top 5 products |
| 4 | **Customers** | Demographic & time-based analysis | Sales by Location ID, quarterly trend line, gender split, revenue by region |
| 5 | **Location Overview** | Macro-to-micro geographic breakdown | Country distribution, continental revenue share (Donut), top states, city sales |

---

## 🔍 Detailed Page Breakdown

### 1. 🏠 Home Page
- Centralized portal welcoming stakeholders to the dashboard.
- Seamless one-click page navigation buttons directly linked to each department's view.

### 2. 📈 Sales Overview
- **Key Metrics:** `Total Sales`, `Total Cost`, `Total Profit`.
- **Category Sales:** Revenue breakdown across `Electronics`, `Clothing`, `Books`, and `Home Appliances`.
- **Top Product Performance:** Horizontal bar chart identifying highest revenue-generating stock-keeping units (SKUs).
- **Target Tracking:** Gauge chart measuring sales pace against business milestones.
- **Slide-Out Slicer Panel:** Collapsible drawer filtering by Month, Product, SubCategory, and Quantity.

### 3. 📦 Products Insights
- **Key Metrics:** `Profit Margin %`, `Total Orders`, `Sum of Quantity`.
- **Margin Analysis:** Detailed bar chart contrasting high-margin vs. high-volume products.
- **Category Contribution:** Operating profit contribution by product vertical.
- **SubCategory Breakdown:** Granular revenue tracking for product lines.
- **Fast-Moving Goods:** Top 5 products ranked by quantity sold.

### 4. 👥 Customers Insights
- **Key Metrics:** `Total Revenue`, `Sum of Quantity`, `Average Order Value (AOV)`.
- **Quarterly Seasonality:** Line chart highlighting revenue trajectory across Q1 to Q4.
- **Gender Dynamics:** Donut visual analyzing purchasing power between male and female customer bases.
- **Regional Footprint:** Customer revenue split across MENA, North America, and Europe.

### 5. 🌍 Location Overview (Geographical Performance)
- **Key Metrics:** `Total Revenue`, `Sum of Quantity`, `Average Order Value (AOV)`.
- **Country Benchmarks:** Comparative revenue across Egypt, Saudi Arabia, USA, and Germany.
- **Continental Share:** Visual representation of MENA vs. Western market penetration.
- **State & City Analysis:**
  - *Top 5 Profits by State:* Identification of the most profitable administrative territories.
  - *Total Sales by City:* Granular performance tracking (Cairo, Riyadh, Alexandria, Giza, etc.).
- **Interactive Cascading Filters:** Slice by Region, Country, State, City, and Month.

---

## 🗄️ Data Model & Architecture

The report is built on a **Star Schema** to ensure optimal performance, scalability, and clean relationship paths:
