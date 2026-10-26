# Global Superstore – Executive Sales & Profitability Dashboard

An interactive **Microsoft Power BI** dashboard that helps senior management monitor sales, profitability, customer behaviour and regional performance for a global retailer.

> Prepared by: **Enoch Tawiah Acquaye** · Junior Business Intelligence Analyst · October 2026

## Business problem

A national retail company needs an executive dashboard that turns raw sales data into decisions. The dashboard answers seven questions:

1. What is the overall sales performance?
2. Which regions generate the highest sales and profit?
3. Which customer segments contribute the most revenue?
4. Which product categories perform best?
5. Which products are the most profitable?
6. What trends appear over time?
7. What should management do to improve performance?

## Dataset

| Item | Detail |
| --- | --- |
| File | `data/Global_Superstore.csv` |
| Size | 51,290 order lines × 24 columns |
| Period | 1 Jan 2011 – 31 Dec 2014 |
| Scale | 25,035 orders · 147 countries · 7 markets · 13 regions |
| Currency | Not labelled; assumed USD |

## Tools

Microsoft Power BI Desktop (Power Query, DAX)

## Data preparation (Power Query)

- Checked structure and missing values (only Postal Code is blank, for non-US rows; replaced with `N/A`)
- Removed duplicates on Row ID (0 found)
- Converted dd-MM-yyyy text dates to Date using the UK locale; IDs and Postal Code to Text
- Added `Ship Days` and `Discount Band` columns

## Key measures

Key DAX measures:
Total Sales   = SUM(Orders[Sales])
Total Profit  = SUM(Orders[Profit])
Total Orders  = DISTINCTCOUNT(Orders[Order ID])
Avg Sales     = AVERAGE(Orders[sales])
Profit Margin = DIVIDE([Total Profit], [Total Sales])

## Dashboard

**Page 1 – Executive Overview:** 5 KPI cards, profit by region (bar), sales by segment (donut), profit by country (map), monthly trend (line), sales by category (column).
**Page 2 – Product & Profit Detail:** profit by sub-category (column), top 5 products by profit (bar), product details table.
Slicers: Year, Market, Segment, Category (synced across pages).

## Headline results

| KPI | Value |
| --- | --- |
| Total Sales | $12.64M |
| Total Profit | $1.47M |
| Total Orders | 25,035 |
| Average Sales | $246.49 |
| Profit Margin | 11.6% |

## Key insights

- Sales grew from $2.26M (2011) to $4.30M (2014) but margin stayed at about 11–12%.
- Technology leads (14.0% margin); Furniture lags (6.9%).
- Tables is the only loss-making sub-category (−$64K), with a 29.1% average discount.
- Margins range from 19.5% (North Asia) to 2.0% (Southeast Asia).
- Orders discounted above 20% make up 15.3% of sales but lose about $815K.

## Recommendations (summary)

1. Cap discounts at 20% and require approval above it
2. Reprice or restructure Tables
3. Review loss-making countries (29 of 147)
4. Recover margin in Southeast Asia and EMEA
5. Rationalise loss-making products
6. Invest in Technology and Copiers
7. Replicate high-margin markets; develop Canada
8. Make profit margin a core management KPI

## Limitations

Findings describe 2011–2014. Discount and loss move together, but other costs (e.g. shipping) may contribute. Targets are proposals for management to confirm.

## Author

**Enoch Tawiah Acauaye**.
