# 📊 AdventureWorks Sales Analysis - Power BI

This project presents a **comprehensive sales analysis** using the AdventureWorks dataset (2015–2017).  
The aim is to deliver actionable insights through an interactive **Power BI Dashboard**, focusing on revenue, returns, customer behavior, and product performance.

---

## 🔎 Project Objectives
- Consolidate multi-year sales data into a unified data model.
- Build relationships across **Sales, Products, Customers, Territories, Returns**.
- Develop **DAX measures** for sales, returns, and net performance.
- Provide drill-down analytics by **Region, Category, Subcategory, Product, and Customer**.
- Design dashboards inspired by **Financial Statement layouts** for clarity and decision-making.

---

## 🗂 Data Sources
- **AdventureWorks_Sales_2015–2017**
- **AdventureWorks_Products (Category & Subcategory)**
- **AdventureWorks_Customers**
- **AdventureWorks_Returns**
- **AdventureWorks_Territories**

---

## 🛠 Data Modeling
- Star schema model with **Sales** as the fact table.
- Dimension tables: **Products, Categories, Subcategories, Customers, Territories, Date**.
- Relationships built via keys:
  - `Sales[ProductKey] → Products[ProductKey]`
  - `Products[ProductSubcategoryKey] → Subcategory[ProductSubcategoryKey]`
  - `Subcategory[ProductCategoryKey] → Category[ProductCategoryKey]`
  - `Sales[CustomerKey] → Customers[CustomerKey]`
  - `Sales[TerritoryKey] → Territories[SalesTerritoryKey]`
  - `Sales[OrderDate] → Date[Date]`
  - `Returns[ProductKey] → Products[ProductKey]`

---

## 📐 Key DAX Measures
DAX
Total Sales = CALCULATE(SUM(Sales[OrderQuantity]), NOT(ISBLANK(Sales[OrderQuantity])))

Total Returns = CALCULATE(SUM(Returns[ReturnQuantity]), NOT(ISBLANK(Returns[ReturnQuantity])))

Net Sales = [Total Sales] - [Total Returns]

Returns Negative = -1 * [Total Returns]

Net Sales = [To]()

📸 Dashboard Previews

1. Executive Overview
![Overview](images/Overview.png)
2. Customer Analysis
![Customers](images/customersAnalysis.png)



