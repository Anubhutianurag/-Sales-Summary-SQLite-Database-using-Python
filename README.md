# Task 7 - Basic Sales Summary using SQLite and Python

This project is part of the **Data Analyst Internship (Task 7)**, where we perform a basic sales summary analysis using a tiny SQLite database within Python and visualize the results using a bar chart.

---

##  Objective

- Use **SQL inside Python** to retrieve basic sales info like:
  - Total quantity sold
  - Total revenue per product
- Visualize revenue data using a **matplotlib bar chart**

---

##  Tools Used

- **Python**
- **SQLite** (via `sqlite3`)
- **pandas**
- **matplotlib**
- **Jupyter Notebook**

---

##  Files Included

| Filename | Description |
|----------|-------------|
| `sales_data.db` | SQLite database with a single `sales` table |
| `sales_analysis.ipynb` | Jupyter notebook performing SQL queries and plotting(created using matplotlib)  |
| `sales_chart.png` | Bar chart visualizing revenue by product |
| `README.md` | Project documentation |

---

## Dataset Description

A simple `sales` table was created with the following fields:
- `id`: Primary key
- `product`: Name of the product
- `quantity`: Number of items sold
- `price`: Price per item

Sample products include: Shirts, Jeans, Shoes, Jackets, Hats, T-Shirts, Socks.

---

##  Analysis Performed

- Connected to SQLite database using `sqlite3`
- Ran SQL query to group data by product:
  ```sql
  SELECT product, 
         SUM(quantity) AS total_qty, 
         SUM(quantity * price) AS revenue 
  FROM sales 
  GROUP BY product
