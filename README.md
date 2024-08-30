# Finance & Supply Chain Analyses - AtliQ Hardwares

## Overview
AtliQ Hardware is a leading global manufacturing company specializing in electronic peripherals such as mouse, keyboards, and other devices. The company operates through three primary distribution channels: retail partnerships, direct channels (AtliQ Exclusive stores and e-stores), and distributors in regulated regions like China and South Korea. This strategy allows AtliQ to maintain a robust global presence across both traditional and digital platforms.

## **Table of Contents** 
- [Problem Statement](#problem-statement)
- [Project Overview](#project-overview)
- [Key Areas of Focus](#key-areas-of-focus)
- [Data Sources](#data-sources)
- [Techniques Used](#techniques-used)
- [Challenges and Solutions](#challenges-and-solutions)
- [Reports](#reports)
- [Contact](#contact)
  
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

## **Reports**

This project generated 10 key reports, each addressing specific business questions related to the supply chain and finance functions. The reports are generated using SQL scripts, and the resulting CSV files are provided:

## Reports

## Reports

### 1. Croma India Product-Wise Sales Report for Fiscal Year 2021
**Report Description:** This report provides an aggregated view of individual product sales on a monthly basis for Croma India customers for the fiscal year 2021. The objective is to track sales performance at the product level, enabling further analysis and insights into product sales trends and profitability.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/1%20.%20Croma%20India%20Product-wise%20monthly%20sales%20report%20for%20FIscal%20Year%20-%202021.csv) <!-- Replace '#' with the actual link to the report file -->

### 2. Gross Monthly Total Sales Report for Croma
**Report Description:** This report provides an aggregate view of the total gross sales generated by Croma India customers on a monthly basis. It is designed to help product owners track the sales performance of this specific customer and manage relationships with AtliQ based on the generated revenue.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/2%20.%20Total%20Gross%20sales%20Monthly%20report%20for%20Croma%20India.csv) <!-- Replace '#' with the actual link to the report file -->

### 3. Gross Yearly Total Sales Report for Croma
**Report Description:** This report provides an aggregated view of the total gross sales amount for Croma India customers on a yearly basis. It is intended to offer insights into the overall annual sales performance, facilitating better strategic decisions and relationship management with AtliQ.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/3.%20Yearly%20Total%20Gross%20Sales%20report%20for%20Croma%20India..csv) <!-- Replace '#' with the actual link to the report file -->

### 4. Top Markets, Products, and Customers for a Given Financial Year
**Report Description:** This set of reports is designed to provide a comprehensive view of the top-performing markets, products, and customers based on net sales for a given financial year. These insights are crucial for assessing financial performance, identifying key areas for growth, and addressing potential issues.

- **Report for Top Markets:**
  - **Description:** Identifies the top 5 markets based on net sales for the specified financial year. This report helps in understanding which markets are driving the most revenue.
  [View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/4%20.%201%20.%20Top%205%20market%20by%20Net%20Sales.csv) <!-- Replace '#' with the actual link to the report file -->

- **Report for Top Products:**
  - **Description:** Lists the top 5 products based on net sales for the given financial year. This report helps in identifying the most successful products and understanding their contribution to overall revenue.
  [View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/4.%202%20.%20Top%205%20product%20by%20Net%20Sales.csv) <!-- Replace '#' with the actual link to the report file -->

- **Report for Top Customers:**
  - **Description:** Provides insights into the top 5 customers based on net sales for the specified financial year. This report is useful for managing key customer relationships and understanding customer contribution to revenue.
  [View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/4.%203%20.%20Top%205%20customers%20by%20Net%20Sales.csv) <!-- Replace '#' with the actual link to the report file -->

### 5. Net Sales Percentage Share by Region - APAC & EU
**Report Description:** This report provides a breakdown of net sales by region and customer, presenting the percentage share of net sales within each region. The goal is to perform a regional analysis of financial performance and understand the contribution of different customers to the net sales in each region. This analysis will be visualized using bar charts for the financial year 2021 and will be designed as a reusable asset for any financial year.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/5%20.%20APAC%20%26%20EU%20Market%20%25%20by%20Net%20Sales.pdf) <!-- Replace '#' with the actual link to the report file -->

### 6. Net Sales Percentage Share Global
**Report Description:** This report presents the percentage share of net sales for the top 10 markets globally for the financial year 2021. It provides a clear view of how different markets contribute to the overall net sales, allowing for strategic decision-making and performance analysis. The results will be visualized using a bar chart to highlight the top markets based on their percentage share of global net sales.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/6.%20Net%20Sales%20Percentage%20Share%20Global%20for%20FY%202021.pdf) <!-- Replace '#' with the actual link to the report file -->

### 7. Top N Products in Each Division by Sold Quantity for FY 2021
**Report Description:** This report identifies the top N products within each division based on their sold quantity for the fiscal year 2021. The goal is to analyze and rank products within each division according to their sales performance. This information helps in understanding the top-performing products and aids in inventory management and strategic planning.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/7.%20Top%203%20Products%20in%20each%20division..csv) <!-- Replace '#' with the actual link to the report file -->

### 8. Top N Markets by Region by Gross Sales for FY 2021
**Report Description:** This report identifies the top N markets within each region based on their gross sales for the fiscal year 2021. The aim is to highlight the leading markets in terms of gross sales within each region, providing insights into regional sales performance and market contributions.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/8.%20Top%202%20market%20in%20each%20region.csv) <!-- Replace '#' with the actual link to the report file -->

### 9. Forecast Accuracy for All Customers for FY 2021
**Report Description:** This report assesses the accuracy of forecasts made for all customers for the fiscal year 2021. It provides insights into how closely the actual sales quantities align with the forecasted quantities, helping in evaluating forecast performance and accuracy.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/9.%20Forecast%20Accuracy%202021.csv) <!-- Replace '#' with the actual link to the report file -->

### 10. Forecast Accuracy for All Customers: FY 2020 vs. FY 2021 
**Report Description:** This report compares the forecast accuracy for all customers between fiscal years 2020 and 2021. It identifies customers whose forecast accuracy has dropped from 2020 to 2021, providing insights into changes in forecast performance.
[View Report](https://github.com/NK-TheAnalyst/SQL-Project---Finance-Supply-Chain-Analyses/blob/main/10.%202021%20vs%202020%20forecast%20accuracy.csv) <!-- Replace '#' with the actual link to the report file -->



Each report's SQL script and corresponding CSV file are included in the repository.


## **Contact**

For any inquiries or collaboration opportunities, feel free to connect with me:

- **LinkedIn:** [Profile](https://www.linkedin.com/in/naveen-kumar-n-095051195/)

