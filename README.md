<div align="center">

# 🐼 Panda Market Sales Dashboard | Power BI
### Turning Retail Sales Data into Business Insights

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-0078D4?style=for-the-badge)](https://learn.microsoft.com/en-us/dax/)
[![Data Modeling](https://img.shields.io/badge/Schema-Star%20Schema-2EA44F?style=for-the-badge)](#-data-preparation--modeling)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)

<p align="center">
  <b>An interactive Business Intelligence project analyzing retail transactions, product performance, regional market penetration, customer demographics, and profitability margins across global markets.</b>
  <br />
  <i>Track. Manage. Grow. — Your Panda World in One Screen.</i>
</p>

<!-- Live Animated Walkthrough / Preview -->
<img src="demo.gif" alt="Panda Dashboard Walkthrough" width="100%" />

</div>

---

## 📌 Project Overview

The **Panda Market Sales Dashboard** is an end-to-end business intelligence solution built using **Microsoft Power BI**. The dashboard transforms over **50,000 retail sales transactions** into meaningful visual stories and decision-making metrics. 

It provides executives and operations teams with full visibility into high-level sales trends, product vertical margins, customer behavior patterns, and geographical distributions across continents, nations, and metropolitan cities.

### 📋 Project at a Glance

| Project Detail | Description |
| :--- | :--- |
| **Project Name** | Panda Market Sales & Retail Analytics Dashboard |
| **Domain** | Retail & E-Commerce Business Intelligence |
| **Reporting Period** | 2023 – 2025 |
| **Total Transactions** | 50,005 Sales Records |
| **Total Products** | 80 Active SKUs across 4 Categories & 8 SubCategories |
| **Customer Base** | 2,000 Registered Customers |
| **Main Tool** | Microsoft Power BI Desktop & Power BI Service |
| **Data Preparation** | Power Query (ETL, Type Casting, Cleaning) |
| **Analytical Calculations** | DAX (Explicit Measures, Time Intelligence, Profitability) |
| **Data Model** | Relational Star Schema (1 Fact, 7 Dimensions) |

---

## 📸 Dashboard Preview

### 1. Cover / Home Page
<p align="center">
  <img src="Screenshots/1_Home_Page.png" alt="Home Page" width="85%" />
</p>

### 2. Sales Overview Dashboard
<p align="center">
  <img src="Screenshots/2_Sales_Overview.png" alt="Sales Overview" width="85%" />
</p>

> *The Sales Overview page summarizes high-level performance metrics, tracking top revenue-generating categories, products, and overall financial pace.*

---

## 📑 Table of Contents
- [Project Overview](#-project-overview)
- [Dashboard Preview](#-dashboard-preview)
- [Business Objectives](#-business-objectives)
- [Dataset Architecture](#-dataset-architecture)
- [Data Preparation & Modeling](#-data-preparation--modeling)
- [Dashboard Pages](#-dashboard-pages)
- [Key Features](#-key-features)
- [Key Performance Indicators (KPIs)](#-key-performance-indicators-kpis)
- [Key Business Insights](#-key-business-insights)
- [DAX Measures](#-dax-measures)
- [Tools and Technologies](#-tools-and-technologies)
- [Repository Structure](#-repository-structure)
- [How to Use & Run](#-how-to-use--run)
- [Project Demonstration](#-project-demonstration)
- [Limitations & Considerations](#-limitations--considerations)
- [About the Author](#-about-the-author)

---

## 🎯 Business Objectives

This project aims to answer critical commercial and operational questions:

1. **Revenue & Margins:** What is the overall gross revenue, cost of goods sold (COGS), and net operating profit margin?
2. **Category Contribution:** Which product categories (Electronics, Home Appliances, Clothing, Books) drive the volume vs. profitability?
3. **SKU Velocity:** Which specific products represent the top revenue generators, and which products lead in unit volume?
4. **Geographic Distribution:** How are sales distributed across continental regions (MENA, North America, Europe) and key countries (Egypt, Saudi Arabia, USA, Germany)?
5. **Customer Profiling:** What is the average order value (AOV), and how does purchasing volume vary between male and female customer segments?
6. **Time Dynamics:** How does purchasing momentum fluctuate across quarters and calendar months?

---

## 📂 Dataset Architecture

The project dataset represents a complete retail sales environment organized into a normalized relational model.

### Dataset Tables & Description

| Table | Type | Records | Key Columns & Description |
| :--- | :--- | :--- | :--- |
| **`Fact_Sales`** | Fact | 50,005 | `InvoiceNo`, `InvoiceDate`, `CustomerID`, `ProductID`, `Quantity`, `UnitPrice`, `TotalAmount` |
| **`Dim_Product`** | Dimension | 80 | `ProductID`, `ProductName`, `SubCategoryID`, `Price`, `Cost` |
| **`Dim_Category`** | Dimension | 4 | `CategoryID`, `CategoryName` (Electronics, Home Appliances, Clothing, Books) |
| **`Dim_SubCategory`**| Dimension | 8 | `SubCategoryID`, `SubCategoryName`, `CategoryID` |
| **`Dim_Customer`** | Dimension | 2,000 | `CustomerID`, `Name`, `Gender`, `Age`, `LocationID`, `RegistrationDate` |
| **`Dim_Location`** | Dimension | 12 | `LocationID`, `City`, `State`, `CountryID` |
| **`Dim_Country`** | Dimension | 4 | `CountryID`, `Country`, `Region` |
| **`Dim_Date`** | Dimension | Auto | `DateID`, `Date`, `Day`, `Month`, `Month Name`, `Quarter`, `Year` |

---

## 🧹 Data Preparation & Modeling

### 1. ETL with Power Query:
* Imported the raw CSV files and validated column headers.
* Verified appropriate data types (Currency for financial figures, Whole Numbers for quantities, and Date formats for transactional timestamps).
* Cleaned categorical values and ensured relational integrity across primary and foreign keys.

### 2. Star Schema Data Model:
Relationships are designed with **1-to-Many ($1:*$)** cardinalities and single-direction filter propagation:
