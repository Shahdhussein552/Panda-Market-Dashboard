# 🐼 Panda Market Sales Analytics Dashboard (Power BI)

An end-to-end, interactive **Power BI** business intelligence dashboard designed for **Panda Market** to monitor sales performance, optimize profitability, analyze product distribution, understand customer demographics, and track regional market penetration.

---

## 📌 Executive Summary
The goal of this project is to transform raw retail sales data into actionable business insights. The report provides a seamless multi-page reporting experience with dynamic page navigation and collapsible filter panels (powered by Bookmarks & Selection panes).

---

## 📊 Dashboard Pages & Insights

### 1. 🏠 Home Page
* Welcome interface featuring brand identity and direct navigation buttons to all report modules:
  * **Sales Overview**
  * **Products**
  * **Customers**
  * **Location Overview**

---

### 2. 📈 Sales Overview
* **Key KPIs:**
  * **Total Sales**
  * **Total Cost**
  * **Total Profit**
* **Visuals & Charts:**
  * **Category Breakdown:** Total Sales across categories (`Electronics`, `Clothing`, `Books`, etc.).
  * **Product Contribution:** Top-performing products by sales revenue.
  * **Category Revenue Share:** Donut chart showcasing revenue distribution across categories.
  * **Gauge Visual:** Sales performance indicator against business targets.
  * **Interactive Filter Panel:** Collapsible drawer filtering by Month, Category, SubCategory, Product, Quantity, and Amount.

---

### 3. 📦 Products Insights
* **Key KPIs:**
  * **Profit Margin %**
  * **Total Orders**
  * **Quantity Sold**
* **Visuals & Charts:**
  * **Profit Margin by Product:** Top profitable products vs. high-volume low-margin items.
  * **Total Profit by Category:** Category contribution to operating profit.
  * **Revenue by SubCategory:** Granular sales performance across subcategories.
  * **Top 5 Products by Quantity:** Fast-moving consumer goods (FMCG) ranking.

---

### 4. 👥 Customers Insights
* **Key KPIs:**
  * **Total Revenue**
  * **Sum of Quantity**
  * **Average Order Value (AOV)**
* **Visuals & Charts:**
  * **Sales by Location ID:** Customer purchase volume by geographical identifiers.
  * **Sales by Quarter:** Quarterly purchasing trends and seasonality analysis.
  * **Gender Distribution:** Revenue split between male and female customer segments.
  * **Revenue by Region:** Macro-level performance across MENA, North America, and Europe.

---

### 5. 🌍 Location Overview (Geographical Analysis)
* **Key KPIs:**
  * **Total Revenue**
  * **Sum of Quantity**
  * **Average Order Value (AOV)**
* **Visuals & Charts:**
  * **Total Sales by Country:** Market share across operating countries (Egypt, Saudi Arabia, USA, Germany).
  * **Sales Share by Region:** Donut chart detailing continental market distribution.
  * **Top 5 Profits by State:** States/Governorates generating the highest operating profit.
  * **Total Sales by City:** City-level revenue ranking (Cairo, Riyadh, Alexandria, Giza, etc.).
  * **Location Filter Panel:** Multi-level cascading slicers for Country, Region, State, City, and Month.

---

## 🛠️ Data Model & DAX Measures

### Star Schema Architecture:
* **Fact Table:** `Fact_Sales`
* **Dimension Tables:** 
  * `Dim_Product`
  * `Dim_Category`
  * `Dim_SubCategory`
  * `Dim_Customer`
  * `Dim_Country`
  * `Dim_Location`
  * `Dim_Date`

### Key DAX Measures:
```dax
-- Total Sales Revenue
Total Sales = SUM(Fact_Sales[TotalAmount])

-- Total Quantity Sold
Total Quantity = SUM(Fact_Sales[Quantity])

-- Total Order Count
Total Orders = DISTINCTCOUNT(Fact_Sales[InvoiceNo])

-- Average Order Value (AOV)
AOV = DIVIDE([Total Sales], [Total Orders], 0)

-- Total Product Cost
Total Cost = 
SUMX(
    Fact_Sales, 
    Fact_Sales[Quantity] * RELATED(Dim_Product[Cost])
)

-- Operating Profit
Total Profit = [Total Sales] - [Total Cost]

-- Profit Margin Percentage
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
