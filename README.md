# Global Electronics Retail Analysis & Executive Dashboard
[Dashboard_Link](https://public.tableau.com/app/profile/dhanesh.gauri/viz/globalelectronicmap/Dashboard2)

## 📌 Project Overview
This project transforms raw transactional data from a global electronics retailer into an interactive executive dashboard. The objective was to analyze over $55M in revenue to uncover business-critical insights regarding customer retention, demographic purchasing power, and brand performance. 

By engineering the data pipeline in SQL and visualizing the metrics in Tableau, this project provides a comprehensive look at global sales health and actionable recommendations for market expansion and marketing spend.

## 🛠️ Tech Stack
* **Database Management:** MySQL (Data modeling, schema design, bulk data importing)
* **Data Manipulation & Analysis:** Advanced SQL (CTEs, Window Functions, Complex Joins, Case Statements, Aggregations)
* **Data Visualization:** Tableau (Executive KPI design, Geographic mapping, Lollipop charts, Time-series analysis)

## 🗄️ Database Architecture
The backend is built on a relational database utilizing a Star Schema design for optimal query performance and BI tool integration:
* **Fact Table:** `sales` (Transaction-level data including order dates, delivery, and quantities)
* **Dimension Tables:** * `products` (Categories, Brands, Unit Costs, Prices)
  * `customers` (Geographic data, Birthdays for demographic grouping)
  * `stores` (Physical vs. Online classifications, Square meters)

## 🚀 Key Business Insights (Dashboard Highlights)
Based on the visualized Tableau dashboard, several key narratives emerged from the data:

1. **Customer Retention is Driving the Business:** * **Insight:** While "One-Hit-Wonders" make up a portion of the customer base, **Loyalists (3+ purchases)** generate the absolute majority of the revenue (56.17%).
   * **Recommendation:** Shift marketing budget from top-of-funnel acquisition to VIP loyalty programs, as retaining existing customers is highly lucrative.
2. **Brick-and-Mortar vs. E-Commerce:** * **Insight:** Physical stores currently dominate the revenue stream (79.55%), compared to the online store (20.45%). 
   * **Recommendation:** Investigate the online user experience to capture more digital market share, while continuing to optimize high-performing physical retail locations.
3. **Demographic Revenue Concentration:** * **Insight:** The "Senior" and "Middle Age" demographics are the highest revenue-generating cohorts, significantly outpacing Teens and Young Adults.
   * **Recommendation:** Tailor premium electronic product advertising toward older demographics who possess higher disposable income.
4. **Brand Performance:** * **Insight:** *Adventure Works* and *Contoso* are the leading brands by total revenue, dwarfing bottom-tier brands like *Tailspin Toys*.

## 💻 SQL Implementation Details
The accompanying `Global_Electronic_SQL.sql` script handles the heavy lifting of data transformation before it reaches the BI layer. Key technical highlights include:

* **Customer Segmentation:** Utilized Common Table Expressions (CTEs) and `COUNT(DISTINCT)` to categorize customers into 'Loyalist', 'Potential Loyalist', and 'One-Hit Wonder' status without causing many-to-many fan-out errors.
* **Dynamic Demographic Engineering:** Employed nested `CASE` statements and date math (`MAX(YEAR)` - `YEAR(Birthday)`) to dynamically group customers into specific age brackets (Teen to Senior) based on their most recent purchase date.
* **Profitability & Channel Analysis:** Built robust aggregation queries to calculate true profit margins (`Unit_Price_USD` - `Unit_Cost_USD` * `Quantity`) and split revenue streams between physical and digital channels.
