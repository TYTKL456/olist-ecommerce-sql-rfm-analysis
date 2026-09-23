# 🛒 Brazilian E-Commerce Analytics Pipeline & Customer Segmentation (Olist Dataset)

An end-to-end data analytics and relational database project analyzing ~100k e-commerce orders from Olist (Brazil). This project demonstrates relational database design, advanced SQL (`JOIN`s, CTEs), statistical feature engineering (RFM), and data visualization using Python (SQLite, Pandas, Seaborn).

---

## 📊 Project Overview
E-commerce marketplaces require deep visibility into customer behavior, regional demand, and seasonal transaction spikes. This project ingests raw relational CSVs into a local **SQLite** database, joins multiple operational entities, and extracts key business intelligence metrics.

### Key Highlights:
* **Relational Database Engineering:** Stitched together 9 normalized tables (Customers, Orders, Order Items, Products, Sellers, Payments, Reviews, and Translations).
* **Descriptive & Volume Analysis:** Evaluated transaction volume versus price magnitude, identifying top-selling categories like *bed_bath_table*.
* **Behavioral Segmentation (RFM Model):** Engineered **Recency, Frequency, and Monetary** metrics using SQL Common Table Expressions (CTEs) and date arithmetic (`JULIANDAY`).
* **Time-Series & Geographic Analysis:** Built faceted visualizations to isolate major seasonal retail shocks (such as Black Friday spikes in November 2017) and mapped payment preferences across regions.

---

## 🗂️ Database Relational Schema Map
The data flows across primary and foreign keys linking customers to orders, order items down to products and third-party sellers, and attaching financial transactions and feedback scores:
* `customers.customer_id` $\rightarrow$ `orders.customer_id`
* `orders.order_id` $\rightarrow$ `order_items.order_id`
* `order_items.product_id` $\rightarrow$ `products.product_id` $\rightarrow$ `product_category_name_translation`
* `orders.order_id` $\rightarrow$ `order_payments.order_id`

---

## 📈 Key Insights & Visualizations
1. **Volume vs. Value:** Mass-market categories (*bed_bath_table*, *health_beauty*) drive high transaction frequency, whereas high-ticket items (computers, appliances) drive higher monetary value per order.
2. **Customer Lifetime Value (RFM):** Successfully isolated high-value repeat buyers from one-time luxury purchasers using custom SQL windowing and aggregations.
3. **Seasonality:** Faceted trend lines highlighted exponential growth across 2017–2018, culminating in massive holiday and Black Friday transaction surges.

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python
* **Database:** SQLite
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
