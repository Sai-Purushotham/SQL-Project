# 🛒 Smart Inventory & Sales Management System

A comprehensive, production-ready SQL database for retail inventory and sales management. Includes normalized schema (BCNF), triggers, views, stored procedures, indexing, audit logging, and sample data. Perfect for portfolios, learning, demo, or production.

---

## 📚 Table of Contents
- [Features](#features)
- [Schema Overview](#schema-overview)
- [Getting Started](#getting-started)
- [Usage Examples](#usage-examples)
- [Reporting & Analytics](#reporting--analytics)
- [Testing](#testing)
- [Troubleshooting](#troubleshooting)
- [Tech Stack](#tech-stack)
- [License](#license)
- [Author](#author)

---

## 🚀 Features

- **BCNF-Normalized Tables**: suppliers, products, customers, sales, sales_items, inventory_logs
- **Triggers & Audit Logs**: Stock changes and transactional automation
- **Views**: Prebuilt for inventory, sales summary, top products, customer stats, monthly analytics
- **Stored Procedures**: Automated sales, restocks, analytics, cancellations
- **50+ Sample Data Rows**: Ready for demo and testing
- **Full Integrity & Performance**: Indexed, validated, optimized

---

## 🏗️ Schema Overview

erDiagram
SUPPLIERS ||--o{ PRODUCTS : supplies
PRODUCTS ||--o{ SALES_ITEMS : sold
CUSTOMERS ||--o{ SALES : makes
SALES_ITEMS ||--|{ SALES : part_of
PRODUCTS ||--o{ INVENTORY_LOGS : tracked

---

## ⚡ Getting Started

### Prerequisites
- MySQL 5.7+/MariaDB 10+
- SQL Workbench/phpMyAdmin/CLI

### Installation

1. Create a new DB (or delete old):  
   `DROP DATABASE IF EXISTS inventory_sales_system;`
2. **Copy-paste the entire SQL** from this repo (`inventory_project.sql`) into your SQL editor (Workbench, phpMyAdmin, or CLI).
3. Run all at once (tables, views, triggers, procedures, sample data = ready instantly).

---

## 💡 Usage Examples

SELECT * FROM v_product_inventory_status; -- Inventory view
CALL sp_make_sale(1, '2025-11-25', @sid, @stat); -- Create sale
CALL sp_add_sale_item(@sid, 2, 5, @stat); -- Add items to sale
CALL sp_get_monthly_revenue_report(2025); -- Monthly analytics
CALL sp_restock_product(3, 20, @stat); -- Restock product
SELECT * FROM inventory_logs WHERE product_id = 3; -- Audit logs

---

## 📊 Reporting & Analytics

| View/Proc                     | Description                         |
|-------------------------------|-------------------------------------|
| v_product_inventory_status    | Inventory, supplier, stock snapshot |
| v_sales_summary               | All sales, customer details         |
| v_top_selling_products        | Ranked product analytics            |
| v_customer_purchase_history   | Buyer analytics                     |
| v_monthly_revenue_report      | Monthwise revenue & stats           |
| sp_get_top_selling_products() | Top-N product leaderboard           |

---

## 🧪 Testing

Try these after install:

SHOW TABLES;
SELECT * FROM v_sales_summary LIMIT 2;
SELECT * FROM inventory_logs ORDER BY change_date DESC LIMIT 5;

---

## 🛠 Troubleshooting

- **"Table doesn't exist"**: Run the full SQL script; ensure correct DB.
- **Trigger not working**: Confirm MySQL version (5.7+/MariaDB 10+).
- **Foreign key errors**: Insert parent before child (suppliers → products, etc.).

---

## ⚙️ Tech Stack

- **Database**: MySQL/MariaDB
- **Features**: Triggers, Views, Procedures, Indexes, BCNF schema

---

## 🏷️ License

MIT — use, learn, extend freely

---

## 👤 Author

Created by [purushotham], November 2025  
Add questions/issues through GitHub!

---

*Ready to use, learn, or extend 🚀*
