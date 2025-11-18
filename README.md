# Zepto Ecommerce SQL Analysis
📌 Project Overview
This project simulates how real-world data analysts work with operational datasets using SQL. The main objective is to understand how analysts use SQL to:

✅ Build and organize a messy, real-world dataset into a structured SQL database
✅ Perform Exploratory Data Analysis (EDA) to uncover trends, patterns, and inconsistencies
✅ Clean and prepare the data by handling nulls, incorrect values, and formatting issues
✅ Write business-focused SQL queries to generate insights around inventory, pricing, performance, and product behavior

📁 Dataset Overview

The dataset used in this project comes from Kaggle and represents scraped product listings from an online grocery delivery platform. It closely resembles real-world e-commerce catalog data.

Each row represents a unique SKU (Stock Keeping Unit) for a product. Duplicate product names exist because the same product may appear multiple times in different package sizes, weights, discounts, or categories to improve visibility – exactly how real catalog data looks.

🧾 Columns

sku_id – Synthetic primary key for each record
name – Product name as displayed in the app
category – Food & grocery category the product belongs to
mrp – Maximum Retail Price (originally in paise, later converted to ₹)
discountPercent – Discount offered on the MRP
discountedSellingPrice – Final selling price after discount (in ₹)
availableQuantity – Units available in stock
weightInGms – Weight of product in grams
outOfStock – Boolean flag showing stock availability
quantity – Units per package (mixed with grams for loose items)

🔧 Project Workflow
1. Database & Table Creation

Created the SQL table using appropriate datatypes for consistent storage:

<img width="600" height="645" alt="Image" src="https://github.com/user-attachments/assets/391fa699-d4db-4380-bf0a-4606709589eb" />


2. Data Import

The CSV was loaded using pgAdmin’s Import tool.

3. 🔍 Data Exploration

Performed basic EDA to understand dataset shape, structure, and behavior:

Counted total number of records

Viewed sample data using LIMIT

Checked for null values

Retrieved distinct product categories

Compared in-stock vs out-of-stock items

Identified product duplicates representing multiple SKUs

4. 🧹 Data Cleaning

Removed rows where MRP or discountedSellingPrice was zero

Converted mrp and discountedSellingPrice from paise → rupees

Ensured pricing consistency across duplicated SKUs

Standardized weight formats for accurate comparisons

5. 📊 Business Insights

Extracted meaningful insights using SQL, such as:

Top 10 most discounted products

High-MRP products currently out of stock

Estimated revenue potential by category

Expensive products (MRP > ₹500) with low discounts

Top 5 categories offering highest average discounts

Value-for-money products based on price per gram

Categorized items as Low, Medium, or Bulk weight

Measured total inventory weight for each product category
