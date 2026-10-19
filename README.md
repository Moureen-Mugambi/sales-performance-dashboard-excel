# Multi-Country Sales Performance Dashboard

An interactive Excel dashboard that tracks sales across five African countries from 2023 to 2025.

![Dashboard preview](sales-dashboard-preview.png)

## Background and objective

Sales data sat in one long table. It was hard to compare countries, products and salespeople. The goal was to build one dashboard that answers these questions fast:

- How much revenue did we earn, and where?
- Which products sell best?
- How do customers pay?
- How does each salesperson perform?
- How many orders were returned?
- Do discounts and promotions change results?

## Data source and cleaning steps

- **Source:** Sample sales dataset
- **Records:** 1,500 orders
- **Period:** 1 January 2023 to 30 June 2025
- **Countries:** Democratic Republic of the Congo (DRC), Egypt, Kenya, Nigeria, South Africa
- **Fields:** date, region, product, quantity, unit price, store location, customer type, discount, salesperson, total price, payment method, promotion, returned, order ID, customer name, shipping cost, order date, week number, delivery date, region manager

**Cleaning and validation steps:**

1. Loaded the raw sales records into an Excel Table
2. Checked for blank cells. None found
3. Checked for duplicate rows and duplicate order IDs. None found
4. Checked for extra spaces and spelling differences in text columns. Category names are consistent
5. Converted dates to proper Excel dates and checked the range
6. Checked that every delivery date falls 2 to 10 days after the order date
7. Checked that quantity, unit price, discount and shipping cost sit in sensible ranges
8. Added calculated columns: `TotalPrice` (unit price x quantity x (1 minus discount)) and `WeekNum`
9. Checked that the calculated columns match on every row
10. Removed personal data. Customers appear only as anonymous codes such as "Cust 6583"

![Cleaned table](cleaned-table.png)

## Tools used

- Microsoft Excel
- PivotTables
- Slicers (discount tier, promotion, week)
- Timeline filter (years, quarters, months, days)
- Map chart
- Bar and pie charts

## How the dashboard is built

The workbook has three sheets:

| Sheet | Purpose |
|-------|---------|
| Raw Data | The cleaned order table |
| Analysis | PivotTables that feed every chart |
| Dashboard | The final interactive view |

![Pivot tables](pivot-tables.png)

The dashboard includes:

- Key performance indicator (KPI) cards for total revenue, total shipping cost and returned orders
- Top 3 products
- Regional revenue map
- Revenue by country
- Revenue by salesperson
- Payment method breakdown
- Filters for time period, discount tier, promotion and week

## Key insights

All figures cover 2023 to 2025 with no filters applied. Revenue is after discounts.

- Total revenue was **$4.38M**. Shipping cost was **$41K**, which is under 1% of revenue.
- **Egypt** led the five countries with **$968K** (22% of revenue). South Africa was lowest at $828K.
- **Tablet, Laptop and Printer** were the top three products. Each earned about **$684K**, so they are almost tied. Phone was lowest at $497K.
- **Online** ($971K) and **cash** ($950K) were the most used payment methods. Debit card was lowest at $770K.
- **Bob** was the top salesperson with **$797K**, followed by Alice at $786K. Diana was lowest at $677K.
- **FREESHIP** had the highest revenue among promotions at **$1.24M**, about 15% above orders with no promotion.
- **372 orders (24.8%) were returned.** They are worth **$1.11M**.

## Notes and limits

- Revenue includes returned orders.
- 2025 is only half a year. The data stops on 30 June 2025. A comparison of 2025 with earlier years would mislead.
- Revenue by promotion shows which promotion had the highest sales. It does not prove the promotion caused them.

## How to reproduce it

1. Download `[your-file-name].xlsx` from this repository
2. Open it in Microsoft Excel
3. Go to the **Raw Data** sheet to see the order table
4. Go to the **Analysis** sheet. Click **Data**, then **Refresh All** to update the PivotTables
5. Go to the **Dashboard** sheet
6. Click the slicers and timeline to filter the view

## Contact

- **Name:** Moureen Mugambi
- **LinkedIn:** www.linkedin.com/in/moureenmugambi
- **Email:** moureengmugambi@gmail.com
