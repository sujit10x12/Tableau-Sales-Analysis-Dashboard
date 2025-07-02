![Sales Dashboard](https://github.com/user-attachments/assets/1acd366d-f132-4821-ac6f-b41e98211f8b)
![Performance by Location](https://github.com/user-attachments/assets/e837d5ab-c9ff-46da-8453-d2fa4f409154)



## ❓ Key Business Questions & KPIs

This dashboard answers the following key performance questions:

- 🧮 **What are our topline metrics** such as total Sales, Orders, and Profit?
- 📦 **Which product categories and sub-categories** drive the most sales and profit?
- ⏳ **How has performance trended over time** across categories?
- 👥 **Who are our most and least profitable customers?**
- 🚚 **What are the most preferred shipping methods** by sub-category?
- 🌍 **Which regions and states** generate the highest sales and profit?
- 🏆 **What are our top-selling products?**
- 📍 **How does performance vary by state** in a detailed tabular format?
---

## 🛠 Tools & Technologies

- **Tableau Desktop** (Data visualization)
- **Excel / CSV** (Source data)

---

## 🌐 Live Dashboard

  👉 [Sales Dashboard](https://public.tableau.com/app/profile/sujit.singh5086/viz/shared/QBRCQYZDZ)  
  👉 [Performance by Location Dashboard](https://public.tableau.com/app/profile/sujit.singh5086/viz/TableauFundamentals_17483200559180/PerformancebyLocation)

---

## 🔍 Dashboard Features

### 📌 Topline Summary
- Displays high-level KPIs including:
  - **Total Sales**
  - **Orders**
  - **Profit**
  - **Profit Ratio**

### 📦 Sales Analysis
- **Sales by Product Category and Sub-Category**
- **Top Selling Products** based on total revenue

### ⏱ Performance Over Time
- Time series trends:
  - Sales and profit **over time by Category**

### 👥 Customer Insights
- Identifies:
  - **Most Profitable Customers**
  - **Least Profitable Customers**

### 🚚 Shipping Preferences
- Breakdown of shipping methods by **Product Sub-Category**

### 🌍 Geographic Performance
- **Performance by Region** (Sales, Profit)
- **Top States by Sales**
- **Tabular view** showing performance **by State** (Sales, Profit, Quantity)

---

## ⚙️ Data Preparation Steps (in Tableau)

### 1. Import and Clean Fact Table
```
→ Imported 'FactOrders' into Tableau
→ Used Tableau's built-in Data Interpreter to:
   - Remove nulls
   - Fix headers
```

### 2. Extract Country from `OrderId`
Used Tableau's `SPLIT()` function to extract the country code from `OrderId`.

```tableau
SPLIT([OrderId], "-", 1)
```
### 3. Apply Aliases
Renamed country codes for clarity.

```text
CA → Canada  
US → United States
```

### 4. Import and Join Fact and Dimension Tables
Performed **Inner Joins** on ID fields:

```text
FactOrders.CustomerID     = Customers.CustomerID  
FactOrders.ProductID      = Products.ProductID  
FactOrders.PostalCodeID   = PostalCodes.PostalCodeID  
FactOrders.ShipModeID     = ShipModes.ShipModeID  
```
Renamed the resulting combined table to **SalesData**

### 5. Hide Unnecessary Columns from **Dimension Tables**
```text
→ Hidden columns:
   - CustomerID
   - ProductID
   - PostalCodeID
   - ShipModeID
```

### 6. Union Additional Records
Unioned the cleaned `SalesData` table with `FactOrders18-19`.

---

## 🔍 Key Insights

👥 Customer Insights:
  - **Leading Account:** Tamara Chand, with highest total sales and profit.
  - **Hunter Lopez**, **Raymond Buch**, and **Tom Ashbrook** — all delivering strong, profitable transactions.

🏆 Top-Selling Products Summary:
  - Phones lead in sales, driving the Technology category.
  - Chairs are top in Furniture, boosted by home office demand.
  - Binders show strong, steady sales in Office Supplies.
  - Storage products perform well across home and office needs.

💼 Popular Category:
  - **Technology and Office Supplies** are nearly equal in profit, with **Technology slightly ahead** overall.
  - By **end of 2019**, **Office Supplies overtook Technology** in profit — indicating a shift in demand and category strength.

🌍 Geographic Performance:
  - South region leads sales, followed closely by Northeast.
  - California leads with ~$590K in sales — dominant market with strong urban demand.
  - New York follows at ~$346K — strong metro-driven performance.
  - Texas, Washington & Pennsylvania show similar mid-tier sales.

🚚 Shipping Preferences:
  - **Standard Class** is the most preferred option, indicating customers prioritize cost-effective delivery over speed.
  - **Second Class** is also popular, offering a balance between faster shipping and moderate pricing.
  - **First Class** and **Same Day** are used less frequently, likely due to higher associated costs.
  - Overall, customers tend to prioritize affordability over speed, especially for non-urgent purchases.
---
