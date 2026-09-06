# Power BI Capstone — Retail Business Performance Analytics

## Overview
This Power BI project (`powerbi_capstone.pbix`) is a multi-page dashboard analyzing an e-commerce business across revenue, orders, customers, and products. It uses a star-schema-style data model (Orders, Products, Users, Reviews) with DAX measures for KPIs, filterable by city, brand, category, order status, rating, and date.

## Data Model
Tables and key fields referenced across the report:

| Table | Sample Fields | Purpose |
|---|---|---|
| **orders** | `order_date`, `order_status`, `Monthly Revenue` | Order-level transactions and dates |
| **products** | `product_name`, `brand`, `category`, `Average Product Price`, `Total Products`, `Total Units Sold`, `Avg Product Rating` | Product catalog and pricing |
| **users** | `name`, `city`, `Total Customers` | Customer master data |
| **reviews** | `rating`, `Average Review Rating`, `Review Count 1` | Product review data |

**Key DAX measures:**
- `Total Revenue`
- `Total Orders`
- `Average Order Value`
- `Average Orders per Customer`

*(Note: the compiled data model inside the .pbix is stored in a compressed VertiPaq format, so full DAX formula text isn't extractable outside Power BI Desktop — open the file there to view/edit measures in the Data pane.)*

## Report Pages

### 1. Overall Dashboard
High-level KPI summary and trends.
- **Cards:** Total Revenue, Total Users, Total Orders, Average Order Value, Total Products, Average Review Rating
- **Monthly Revenue Trend** (line chart)
- **Top 10 Products by Revenue** (funnel)
- **Order Status Distribution** (donut)
- **Top 10 Cities Revenue** (area chart)
- **Top 10 Brands by Revenue** (clustered column)
- **Filters:** City, Brand, Category, Order Date

### 2. Customer & Product Analysis
Deep dive into customer geography and product performance.
- **Cards:** Total Users, Total Products, Average Product Price, Total Units Sold
- **Customer Distribution by City** (map)
- **Average Rating by Category** (bar chart)
- **Top 10 Products by Rating** (treemap)
- **Top 10 Brands by Average Price** (clustered column)
- **Filters:** City, Category, Brand, Rating

### 3. Customer & Order Analysis
Order behavior and fulfillment patterns.
- **Cards:** Total Users, Total Orders, Average Order Value, Average Orders per Customer
- **Orders by Month** (line chart)
- **Order Status by Category** (bar chart)
- **Top 7 Orders by City** (waterfall)
- **Average Order Value by Category** (column chart)
- **Order Status vs Category over time** (stacked area chart)
- **Filters:** Order Date, City, Order Status, Category

### 4. ToolTip Page
A hidden support page providing a custom hover tooltip (column chart) used by other visuals.

## How to Use
1. Open `powerbi_capstone.pbix` in **Power BI Desktop** (free download from Microsoft).
2. Use the slicers on each page (City, Brand, Category, Order Date, Order Status, Rating) to filter the dashboard.
3. Navigate between pages using the on-canvas page navigator or the page tabs at the bottom.
4. To refresh underlying data, use **Home → Refresh** (requires access to the original data source).
5. To inspect or edit measures, open the **Data** or **Model** view in Power BI Desktop.

## Requirements
- Power BI Desktop (latest version recommended)
- Access to the original data source if refreshing data (not required to just view/interact with the existing snapshot)

## Suggested Next Steps
- Document the exact DAX formulas for each measure (open in Power BI Desktop → Measure tools → open formula bar).
- Add row-level security (RLS) if this will be shared across regions/teams.
- Consider adding a Returns/Refunds analysis page if that data is available.
