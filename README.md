# Global Sales & Returns Analysis Dashboard

This Power BI project analyzes global sales, profit, and return performance from 2014–2017 across different regions, categories, and representatives.  

**Live Dashboard:** [View on Power BI](https://app.powerbi.com/view?r=eyJrIjoiNmQ0ZGNmMjktODI1NC00Mzc2LTk0YjItMzllMTE3ZmM5NTcyIiwidCI6IjM0NTMxMzE4LTcwMTEtNGZkNC04N2YwLWE0MzgxNmM0OWJkMCJ9&pageName=d66c1e042c8cb38512cc)

---

## Objective
The goal of this project was to build an interactive Power BI dashboard to track company performance and find improvement areas.  

---

## Dataset
**Global Superstore (2014–2017)**  
Tables:
- Orders: Product, sales, profit, region, and category data  
- Returns: Returned orders and regions  
- People: Sales representatives  

---

## KPIs
- Total Sales: $13M  
- Total Profit: $1M  
- Profit Margin: 12%  
- Overall Return Rate: 8%  

---
## Challenges & How I Solved Them
| Challenge | How It Was Solved |
|------------|------------------|
| The data contained multiple related tables (Orders, Returns, People). | Built proper relationships using Order ID and Region fields in the Power BI model. |
| Needed to calculate different types of return rates. | Created two separate DAX measures — one for overall rate, one by region. |
| Wanted clean, consistent visuals for comparison. | Used filters, bar charts, and aligned visuals to compare across year and region. |
| Data had inconsistent formatting (dates, numbers). | Fixed issues in Power Query before loading into the data model. |

---
## Key Insights

### Global Overview
- Total sales reached $13M, with profits increasing each year.  
- Strongest markets are US, Europe, and Asia-Pacific.  
- Technology category achieved the highest profit margin.  
- Return rate remained low at 8%, indicating stable operations.

### Regional & Category Performance
- Asia Pacific leads in sales ($4.0M), followed by Europe ($3.3M) and USCA ($2.3M).  
- Technology products drive most sales and profit.  
- Corporate segment performs consistently across all regions.

### People & Returns
- Top sales representatives: Gilbert Wolff, Nicodemo Bautista, and Kauri Anaru.  
- Average return rate by region is around 4%, with Eastern Africa showing the highest.  
- Asia Pacific accounts for the largest share of returns (28%).

---

## Recommendations
- Focus marketing on high-profit regions such as Asia Pacific and Europe.  
- Review return processes in Asia Pacific to reduce losses. 
- Recognize top-performing sales representatives.  
- Promote Technology products more to maintain profit growth.

---

## Tools and Skills
- Power Query for data cleaning and transformations  
- DAX for calculated measures  
- Data modeling and relationship building 
- Dashboard design and visualization
- Business interpretation of analytical results

Example of a simple DAX formula used:

Return Rate % (Global) =
DIVIDE(
    COUNTROWS(Returns),
    COUNTROWS(Orders)
)

Return Rate % (By Region) =
DIVIDE(
    COUNTROWS(Returns),
    CALCULATE(
        COUNTROWS(Orders),
        ALLEXCEPT(Orders, Orders[Region])
    )
)

