[README.md](https://github.com/user-attachments/files/24079818/README.md)# 🏢 Inventory & Sales Management System

A simple database system to manage suppliers, products, customers, and sales with automatic tracking.

---

## 📁 Files I Created

```
01-database-creation.sql              ← Creates the database
02-table-definitions.sql              ← Creates 6 tables
03-indexes.sql                        ← Speed up queries (8 indexes)
04-views.sql                          ← 5 ready-made reports
05-triggers.sql                       ← 5 automatic actions
06-stored-procedures.sql              ← 6 functions for operations
07-sample-data-suppliers-products.sql ← 5 suppliers + 10 products
08-sample-data-customers-sales.sql    ← 8 customers + 8 sales
09-verification-queries.sql           ← Test everything works
README-PROJECT.md                     ← Documentation
```

Execute them in order 01 → 09 in MySQL Workbench or phpMyAdmin.

---

## 📊 What I Built

**6 Tables:**
- **suppliers** - Company info (5 sample: TechSupply Inc, Global Traders, etc)
- **products** - Product catalog (10 sample: Laptop, Mouse, Cable, etc with prices)
- **customers** - Customer data (8 sample: John Doe, Jane Smith, etc)
- **sales** - Sale transactions (8 sample sales)
- **sales_items** - Items in each sale (14 line items)
- **inventory_logs** - Track stock changes (auto-logged)

**5 Views:**
- Product inventory status
- Sales summary
- Top selling products
- Customer purchase history
- Monthly revenue report

**6 Procedures:**
- Make sale
- Add item to sale
- Monthly revenue report
- Restock product
- Get top products
- Cancel sale

**5 Triggers:**
- Log stock changes automatically
- Prevent product deletion if sold
- Update sale total when item added
- Update sale total when item changed
- Update sale total when item removed

**8 Indexes:**
- Speed up product searches by supplier, name, category
- Speed up sales queries by date and customer
- Speed up item lookups

---

## 🖼️ My ERD Design

All 6 tables connected with relationships:

```
[Uploadin<img width="1152" height="671" alt="Untitled Diagram drawio (1)" src="https://github.com/user-attachments/assets/fc430ee1-f7f9-4a64-9116-46d2ebda9f40" />

```

**Relationships:**
- 1 Supplier has Many Products
- 1 Customer has Many Sales
- 1 Sale has Many Items
- 1 Product has Many Sales
- 1 Product has Many Log Entries

---

## 📸 Screenshots of Work

### 1. MySQL Workbench - All Files Executed
✅ Database created
✅ All tables loaded
✅ Verification complete

### 2. phpMyAdmin - Sales Items Table
Shows table structure with columns, data types, and indexes

### 3. phpMyAdmin - Products Data
All 10 products displayed:
- Laptop Pro 15 ($1299.99)
- Wireless Mouse ($29.99)
- USB-C Cable ($12.99)
- Mechanical Keyboard ($89.99)
- Monitor Stand ($49.99)
- Phone Case ($19.99)
- Screen Protector ($9.99)
- Webcam HD ($59.99)
- Headphones ($79.99)
- Desk Lamp ($39.99)

### 4. MySQL Workbench - Suppliers Data
All 5 suppliers displayed with phone, email, city

### 5. ERD Diagram
Complete visual showing all tables and relationships

---

## 🔧 How to Use

**Run files in order:**
```bash
mysql -u root -p < 01-database-creation.sql
mysql -u root -p inventory_sales_system < 02-table-definitions.sql
mysql -u root -p inventory_sales_system < 03-indexes.sql
mysql -u root -p inventory_sales_system < 04-views.sql
mysql -u root -p inventory_sales_system < 05-triggers.sql
mysql -u root -p inventory_sales_system < 06-stored-procedures.sql
mysql -u root -p inventory_sales_system < 07-sample-data-suppliers-products.sql
mysql -u root -p inventory_sales_system < 08-sample-data-customers-sales.sql
mysql -u root -p inventory_sales_system < 09-verification-queries.sql
```

Or open files one by one in MySQL Workbench and execute.

---

## 💡 What It Does

**Create a sale:**
```sql
CALL sp_make_sale(1, '2025-12-10', @id, @status);
```

**Add items to sale:**
```sql
CALL sp_add_sale_item(@id, 1, 2, @status);
```

**Check inventory status:**
```sql
SELECT * FROM v_product_inventory_status;
```

**Top selling products:**
```sql
CALL sp_get_top_selling_products(5);
```

**Customer spending:**
```sql
SELECT * FROM v_customer_purchase_history;
```

**Cancel a sale:**
```sql
CALL sp_cancel_sale(1, @status);
```

---

## ✅ What I Did

✓ Designed database structure (6 interconnected tables)
✓ Created ERD showing all relationships
✓ Built tables with validation rules
✓ Added 5 views for reporting
✓ Wrote 6 procedures for operations
✓ Set up 5 triggers for automation
✓ Added 8 indexes for speed
✓ Loaded 37+ sample records
✓ Tested in MySQL Workbench
✓ Verified in phpMyAdmin

---

## 🎯 Key Features

- **Prevents bad data**: Validates prices, stock, emails
- **Prevents deletion**: Can't delete products with sales
- **Auto-calculates**: Sale totals calculate automatically
- **Auto-logs changes**: Every stock change recorded
- **Handles errors**: Rollback if something fails
- **Fast queries**: Indexes speed up lookups
- **Easy operations**: Use procedures instead of writing SQL

---

## 📋 Sample Data Included

| What | Count |
|------|-------|
| Suppliers | 5 |
| Products | 10 |
| Customers | 8 |
| Sales | 8 |
| Sale Items | 14 |

---

## 🚀 Ready to Use

All files are ready. Just execute 01-09 in order and you're done. Database works in:
- MySQL Workbench
- phpMyAdmin
- Any application connected to MySQL

---

**Status**: ✅ Complete and Tested
