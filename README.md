# Blinkit-powerbi-dashbord
# 📦 Blinkit Sales Dashboard | Power BI

This is a fully interactive Power BI dashboard built to analyze the sales performance and customer behavior of Blinkit (formerly Grofers). It demonstrates data analysis, DAX calculation, and business intelligence storytelling skills.

---

## 📌 Project Objective

The main goal of this dashboard is to transform raw sales data into meaningful insights through visually engaging and interactive reports. It helps answer business questions such as:

- What are the top-selling products?
- Which categories are performing best?
- How do sales vary over time?
- What is the average order value?
- How can we segment high vs low value orders?


## 📊 Dashboard Features

- **Sales Summary** – View total revenue, quantity sold, and number of transactions  
- **Top Products & Categories** – Rank-wise performance visualization  
- **Monthly & Daily Trends** – Understand how sales vary over time  
- **Customer Insights** – Analyze customer purchase behavior  
- **Dynamic Filters** – Filter by date, category, product, and location (if applicable)  
- **Sales Performance Labels** – DAX logic to label orders as 'High' or 'Low' based on thresholds



## 🧠 Key DAX Measures Used

Some of the important DAX calculations used in the dashboard:

```dax
Total Sales = SUM(Sheet1[TotalSales])

Total Quantity = SUM(Sheet1[Quantity])

Average Sales = AVERAGE(Sheet1[TotalSales])

Sales Status = IF(Sheet1[TotalSales] >= 1000, "High", "Low")

Top Category = 
CALCULATE(
    MAX(Sheet1[Category]),
    FILTER(Sheet1, Sheet1[TotalSales] = MAX(Sheet1[TotalSales]))
)

Monthly Sales = 
CALCULATE(
    SUM(Sheet1[TotalSales]),
    ALLEXCEPT(Sheet1, Sheet1[Month])
)
