# Finance & Supply Chain Analyses - AtliQ Hardwares

## Overview
AtliQ Hardware is a leading global manufacturing company specializing in electronic peripherals such as mouse, keyboards, and other devices. The company operates through three primary distribution channels: retail partnerships, direct channels (AtliQ Exclusive stores and e-stores), and distributors in regulated regions like China and South Korea. This strategy allows AtliQ to maintain a robust global presence across both traditional and digital platforms.

## **Table of Contents** 
- [Problem Statement](#problem-statement)
- [Project Overview](#project-overview)
- [Key Areas of Focus](#key-areas-of-focus)
- [Data Sources](#data-sources)
- [Techniques Used](#techniques-used)
## **Problem Statement**
As AtliQ Hardware expanded globally, the company faced significant data management challenges. Initially relying on Excel, the company struggled with large datasets, leading to frequent crashes and operational disruptions. A transition to MySQL was implemented to manage the growing data effectively and support the company's expansion.

## **Project Overview**
This project focuses on analyzing AtliQ Hardware's performance in two critical areas: Finance and Supply Chain. The objective is to generate insightful reports that assist stakeholders in making informed decisions related to profitability, product sales, and operational efficiency.

## **Key Areas of Focus**

### Finance Domain:
- **Profit and Loss Statements:** Assess overall financial health.
- **Product-Level Analysis:** Track sales performance and profitability of individual products.
- **Country-Level Analysis:** Analyze sales performance across different countries.
- **Yearly Financial Analysis:** Compare year-over-year growth and financial trends.

### Supply Chain Domain:
- **Inventory Management:** Monitor stock levels and optimize inventory.
- **Supply Chain Efficiency:** Identify bottlenecks and streamline processes.
- **Customer Analysis:** Understand customer behavior and preferences.

## Expected Outcomes
- **Actionable Insights:** Provide strategic guidance for product launches, market expansions, and operational improvements.
- **Enhanced Decision-Making:** Support data-driven decisions through detailed financial and supply chain analysis.

## Project Methodology
The project was managed using the Kanban Agile methodology, implemented through JIRA Software. This approach facilitated continuous delivery, flexibility, and efficient task management.

## **Data Sources**
While the actual datasets are not included due to privacy restrictions, the data used in this project includes customer, product, sales, and financial data imported from CSV files into a MySQL database.

### Primary Tables:
- **DimCustomer:** Customer information.
- **DimDate:** Date details.
- **DimProduct:** Product information.
- **FactActuals:** Actual sales data.
- **FactSalesMonthly:** Monthly sales data.
- **Estimate:** Table created for forecast accuracy calculation.
- **FactGrossPrice, FactManufacturingCost, FactPreInvoiceDeduction, FactPostInvoiceDeduction:** Tables for detailed financial data.

## **Techniques Used**
To efficiently manage and analyze the data, the following SQL techniques were utilized:

### User-Defined Functions:
- **GetFiscalYear():** Custom function to derive the fiscal year based on the calendar date.

### Common Table Expressions (CTEs):
- Used to simplify complex queries by breaking them into manageable parts.

### Data Views (Virtual Tables):
- Employed to create virtual tables for intermediate calculations, reducing the need for physical table storage.

### Temporary Tables:
- Utilized for holding intermediate results during complex operations.

### Window Functions:
- Applied for operations like ranking and aggregations over partitions of data (`OVER` clause).

### Stored Procedures:
- **Top-N Reports:** Created stored procedures for generating reports related to top customers, markets, products, etc. These procedures streamline the process for generating these insights.

## **Challenges and Solutions**

### **1. Performance Optimization for Top Market Product Customers**
- **Challenge:** Initial queries for top market product customers by fiscal year were slow due to the repetitive use of the fiscal year function.
- **Solution:** The issue was resolved by creating a calculated fiscal year column in the `FactSalesMonthly` table, reducing query time from 8 seconds to 2 seconds.

### **2. Forecast Accuracy Calculation**
- **Challenge:** Complex calculations involving multiple financial deductions and sales data were challenging to manage without impacting performance.
- **Solution:** Utilized temporary tables and data views to streamline calculations, followed by stored procedures to generate forecast accuracy reports efficiently.

