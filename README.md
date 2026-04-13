# 🍕 Pizza Sales SQL Project
A complete SQL data analysis project on a pizza restaurant's sales database — covering everything from basic aggregations to advanced window functions.

---

## 👨‍💻 Author
**Nitin Tiwari**

---

## 📁 Project Structure
pizza-sales-sql-project/
│
├── Pizza_sales_project.sql     # All 13 SQL queries
├── pizzas.csv                  # Pizza details (id, type, size, price)
├── pizza_types.csv             # Pizza categories and ingredients
├── orders.csv                  # Order records (date, time)
├── order_details.csv           # Order line items (quantity, pizza)
└── README.md

---

## 🗄️ Database

- **Database Name:** `pizzamania`
- **Tool Used:** MySQL Workbench
- **Tables:** `orders`, `order_details`, `pizzas`, `pizza_types`

### Schema Overview

| Table | Key Columns |
|-------|-------------|
| `orders` | order_id (PK), date, time |
| `order_details` | order_details_id (PK), order_id (FK), pizza_id (FK), quantity |
| `pizzas` | pizza_id (PK), pizza_type_id (FK), size, price |
| `pizza_types` | pizza_type_id (PK), name, category, ingredients |

---

## 📊 Key Results at a Glance

| Metric | Value |
|--------|-------|
| 📦 Total Orders | 21,350 |
| 💰 Total Revenue | $817,860.05 |
| 🍕 Most Popular Size | Large (L) — 18,526 orders |
| 🏆 Top Pizza (Quantity) | The Classic Deluxe Pizza (2,453) |
| 💵 Highest-Priced Pizza | The Greek Pizza ($35.95) |
| 📅 Avg. Pizzas Per Day | ~138 |
| 📈 Top Revenue Category | Classic (26.9%) |

---

## 🔍 Queries Solved

### 🟢 Basic

| # | Question | Key Function |
|---|----------|-------------|
| Q1 | Retrieve the total number of orders placed | `COUNT()` |
| Q2 | Calculate the total revenue generated from pizza sales | `SUM()`, `ROUND()` |
| Q3 | Identify the highest-priced pizza | `ORDER BY price DESC LIMIT 1` |
| Q4 | Identify the most common pizza size ordered | `GROUP BY`, `COUNT()` |
| Q5 | List the top 5 most ordered pizza types with quantities | `JOIN`, `SUM()`, `LIMIT 5` |

### 🟡 Intermediate

| # | Question | Key Function |
|---|----------|-------------|
| Q6 | Total quantity of each pizza category ordered | `JOIN`, `GROUP BY category` |
| Q7 | Distribution of orders by hour of the day | `HOUR()`, `GROUP BY` |
| Q8 | Category-wise distribution of pizzas | `COUNT(name)`, `GROUP BY` |
| Q9 | Average number of pizzas ordered per day | `AVG()` on subquery |

### 🔴 Advanced

| # | Question | Key Function |
|---|----------|-------------|
| Q10 | Top 3 most ordered pizza types based on revenue | Multi-table `JOIN`, `SUM()` |
| Q11 | Percentage contribution of each pizza type to total revenue | Correlated subquery, `%` calculation |
| Q12 | Cumulative revenue generated over time | `SUM() OVER(ORDER BY date)` — Window Function |
| Q13 | Top 3 pizza types by revenue for each category | `RANK() OVER(PARTITION BY category)` — Window Function |

---

## 🛠️ SQL Techniques Used

- `SELECT`, `COUNT()`, `SUM()`, `ROUND()`, `AVG()`
- `GROUP BY`, `ORDER BY`, `LIMIT`
- `INNER JOIN` across multiple tables
- Subqueries (nested & correlated)
- `HOUR()` for time-based analysis
- **Window Functions:** `SUM() OVER()`, `RANK() OVER()`, `PARTITION BY`

---

## ▶️ How to Run

1. Import the CSV files into MySQL as tables under a database named `pizzamania`
2. Open `Pizza_sales_project.sql` in MySQL Workbench
3. Run queries individually or all at once

```sql
-- Example: Create and use the database
CREATE DATABASE pizzamania;
USE pizzamania;

-- Then import the CSV files as tables and run the queries
```

---

## 📌 Insights

- **Large pizzas** dominate orders — customers prefer bigger portions
- **Lunch hour (12 PM)** is the peak ordering time, with a secondary spike around 5–6 PM
- **Chicken-based pizzas** generate the highest revenue despite not being the most ordered by quantity
- Revenue is **evenly distributed** across all 4 categories (Classic, Supreme, Chicken, Veggie), each contributing ~24–27%
- The business shows **consistent, steady growth** with no major seasonal dips

---

## 🙏 Acknowledgement

This project was built with guidance from the **WsCube Tech** YouTube channel.

> Special thanks to WsCube Tech for the structured and beginner-friendly SQL tutorials that made this project possible.

---

## 📜 License

This project is for educational purposes. Feel free to use or modify it for learning SQL.

