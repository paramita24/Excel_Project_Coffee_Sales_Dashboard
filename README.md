# ☕ Coffee Sales Data Analysis

A end-to-end Excel data project analysing coffee sales across three countries from 2019 to 2022. The workbook covers raw data ingestion, customer and product lookup, aggregation, and an interactive sales dashboard.

---

## 📊 Project Overview

| Detail | Value |
|---|---|
| **Period** | Jan 2019 – Aug 2022 |
| **Total Orders** | 1,000 |
| **Unique Customers** | 913 |
| **Total Sales** | $45,134.26 |
| **Markets** | United States, Ireland, United Kingdom |

---

## 📁 File Structure

```
coffeeOrdersDataFinal.xlsx
├── orders           # Raw transaction data (1,000 rows)
├── customers        # Customer master (ID, contact, address, loyalty card)
├── products         # Product catalogue (48 SKUs, pricing, profit margin)
├── TotalSales       # Pivot — monthly sales by coffee type (2019–2022)
├── SalesByCountry   # Pivot — total sales per country
├── TopFiveCustomers # Pivot — top 5 customers by spend
└── Dashboard        # Interactive visual dashboard with slicers
```

---

## 🗂️ Sheet Details

### `orders`
The main fact table. Each row is a line item on an order.

| Column | Description |
|---|---|
| Order ID | Unique order identifier |
| Order Date | Date of purchase |
| Customer ID | FK → customers sheet |
| Product ID | FK → products sheet |
| Quantity | Units purchased |
| Customer Name | Looked up from customers |
| Email | Looked up from customers |
| Country | Looked up from customers |
| Coffee Type | Short code (Ara, Rob, Exc, Lib) |
| Roast Type | Short code (L, M, D) |
| Size | Package size in kg |
| Unit Price | Price per unit |
| Sales | Quantity × Unit Price |
| Coffee Type Name | Full name (Arabica, Robeca, etc.) |
| Roast Type Name | Full name (Light, Medium, Dark) |

### `customers`
1,000 customer records including name, email, phone, address, and loyalty card status.

### `products`
48 SKUs across 4 coffee types × 3 roast levels × 4 sizes (0.2 kg, 0.5 kg, 1.0 kg, 2.5 kg), with unit price, price per 100g, and profit margin.

---

## ☕ Product Catalogue

| Coffee Type | Roast Types | Sizes (kg) |
|---|---|---|
| Arabica | Light, Medium, Dark | 0.2, 0.5, 1.0, 2.5 |
| Excerica | Light, Medium, Dark | 0.2, 0.5, 1.0, 2.5 |
| Liberica | Light, Medium, Dark | 0.2, 0.5, 1.0, 2.5 |
| Robeca | Light, Medium, Dark | 0.2, 0.5, 1.0, 2.5 |

---

## 🌍 Sales by Country

| Country | Total Sales |
|---|---|
| United States | $35,638.89 |
| Ireland | $6,696.87 |
| United Kingdom | $2,798.51 |

---

## 🛠️ Techniques Used

- **INDEX-MATCH** — populate customer and product details into the orders sheet from lookup tables
- **Pivot Tables** — TotalSales, SalesByCountry, and TopFiveCustomers summaries
- **Slicers & Timelines** — interactive filters on the Dashboard for roast types
- **Data Formatting** — custom number formats, date handling, and conditional formatting

---

## 🚀 Getting Started

1. Open `coffeeOrdersDataFinal.xlsx` in **Microsoft Excel 2016+** or **Excel 365** (recommended — slicers and timeline require Excel; some features may not render in LibreOffice/Google Sheets)
3. Navigate to the **Dashboard** sheet for the interactive overview
4. Use the timeline to filter sales data
5. Use the slicers to filter by roast type

---

## Screenshot of Dashboard

![image_alt](https://github.com/paramita24/Excel_Project_Coffee_Sales_Dashboard/blob/main/images/CoffeeSalesDashboard.PNG)
---

## 📌 Notes

- The `orders` sheet is the single source of truth; all pivot sheets derive from it
- Some customer email and phone fields contain nulls — these rows are retained in all analyses
- Sales figures are in **USD**
- Instead of **INDEX-MATCH** we can use **XLOOKUP** with the newer version of excel.
