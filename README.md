# 📊 Sales Performance Dashboard — Power BI + MySQL

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
(<img width="1833" height="1062" alt="image" src="https://github.com/user-attachments/assets/6f890063-87ca-449f-a99c-13a536fee4b3" />)

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)


A fully interactive **Sales Performance Dashboard** built with **Power BI**, powered by data extracted and transformed using **MySQL queries**. This project provides end-to-end business intelligence — from raw relational data in a SQL database all the way to compelling visual insights for decision-makers.

---

## 🚀 Project Overview

Sales teams and business stakeholders need fast, reliable visibility into revenue trends, product performance, regional breakdowns, and rep-level metrics. This project bridges the gap between a structured MySQL database and a polished Power BI dashboard — making raw transactional data instantly actionable.

**Key capabilities:**
- Extract and shape sales data with optimized SQL queries
- Load transformed datasets into Power BI via MySQL connector
- Visualize KPIs, trends, and comparisons through an interactive multi-page report

---

## 🗂️ Repository Structure

```
├── mysql extracted dataset (Queries used) power bi file (compressed zip file).zip
│   ├── Sales_Dashboard.pbix          # Power BI report file
│   └── extracted_dataset.csv / xlsx  # Dataset exported from MySQL
│
├── sales data using sql queries.sql compressed zip file.zip
│   └── sales_queries.sql             # All SQL queries used for data extraction
│
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **MySQL** | Database storage & query-based data extraction |
| **SQL** | Data filtering, aggregation, joins, and transformation |
| **Power BI Desktop** | Dashboard design, DAX measures, and data modelling |
| **Power Query (M)** | Data cleaning and shaping inside Power BI |

---

## 📐 Data Pipeline

```
MySQL Database
      │
      ▼
SQL Queries (JOINs, GROUP BY, filters)
      │
      ▼
Extracted Dataset (CSV / direct connection)
      │
      ▼
Power BI — Power Query (cleaning & transformation)
      │
      ▼
Data Model (relationships + DAX measures)
      │
      ▼
Interactive Dashboard
```

---

## 📊 Dashboard Highlights

The Power BI report covers the following analytical views:

- **Sales Overview** — Total revenue, units sold, and profit margin at a glance
- **Monthly / Quarterly Trends** — Time-series line charts to track growth over time
- **Product Performance** — Best and worst performing products by revenue and volume
- **Regional Analysis** — Geographic breakdown of sales using maps and bar charts
- **Sales Rep Leaderboard** — Individual performance ranking with target vs. actual comparisons
- **Customer Segment Analysis** — Revenue distribution across customer categories
- **Dynamic Filters** — Slicers for date range, region, product category, and sales rep

---

## 🧮 Sample SQL Queries Used

```sql
-- Total sales by product category
SELECT 
    p.category,
    SUM(o.quantity * o.unit_price) AS total_revenue,
    COUNT(o.order_id) AS total_orders
FROM orders o
JOIN products p ON o.product_id = p.product_id
GROUP BY p.category
ORDER BY total_revenue DESC;

-- Monthly sales trend
SELECT 
    DATE_FORMAT(order_date, '%Y-%m') AS month,
    SUM(quantity * unit_price) AS monthly_revenue
FROM orders
GROUP BY month
ORDER BY month;

-- Top 10 sales representatives by revenue
SELECT 
    e.employee_name,
    SUM(o.quantity * o.unit_price) AS revenue_generated
FROM orders o
JOIN employees e ON o.employee_id = e.employee_id
GROUP BY e.employee_name
ORDER BY revenue_generated DESC
LIMIT 10;
```

---

## ⚙️ How to Set Up & Run

### Prerequisites
- [MySQL](https://www.mysql.com/downloads/) (v8.0 or above)
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/nitishkanna2003/sales-performance-dashboard-PowerBi-using-SQl.git
   cd sales-performance-dashboard-PowerBi-using-SQl
   ```

2. **Set up the MySQL database**
   - Unzip `sales data using sql queries.sql compressed zip file.zip`
   - Open MySQL Workbench (or any MySQL client)
   - Run `sales_queries.sql` to create tables and load the dataset

3. **Open the Power BI report**
   - Unzip `mysql extracted dataset (Queries used) power bi file (compressed zip file).zip`
   - Open `Sales_Dashboard.pbix` in Power BI Desktop

4. **Update the data source connection**
   - Go to **Home → Transform Data → Data Source Settings**
   - Update the MySQL server name, port, and credentials to match your local setup
   - Click **Refresh** to load live data

5. **Explore the dashboard**
   - Use slicers and filters to drill into specific regions, time periods, or product categories

---

## 📸 Dashboard Preview

> _Screenshots can be added here. To add: export visuals from Power BI via File → Export → Export to PDF or take screenshots of each report page._

| Page | Description |
|---|---|
| Overview | High-level KPIs and summary cards |
| Trends | Month-over-month and year-over-year comparisons |
| Products | Category and SKU-level performance |
| Regions | Geographic heatmap and territory breakdown |
| Reps | Individual sales performance vs. targets |

---

## 💡 Key Insights This Dashboard Can Answer

- Which product categories drive the most revenue?
- How does sales performance vary across regions?
- Who are the top-performing and underperforming sales reps?
- What months show seasonal peaks or dips?
- How is actual sales performance tracking against targets?

---

## 🙌 Author

**Nitish Kanna**
- GitHub: [@nitishkanna2003](https://github.com/nitishkanna2003)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

> ⭐ If you found this project useful, please consider giving it a star — it helps others discover it!
