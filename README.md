# Power BI — Global Sales & Returns Analysis Dashboard

This Power BI project analyzes global sales, profit, and return performance from 2014–2017 across different regions, categories, and representatives.  

**Live Dashboard:** [View on Power BI](https://bit.ly/powerbi_project_sales_analysis)

---

## Objective
Build an interactive Power BI dashboard to visualize key performance indicators and discover insights from the Global Superstore dataset.

---

## Dataset
**Global Superstore (2014–2017)**  
Includes three related tables:
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

## Key Insights

### Global Overview
- Total sales reached $13M, with profits increasing each year.  
- Strongest markets: US, Europe, and Asia-Pacific.  
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
- Expand Technology category promotions to sustain profit growth.

---

## Tools and Skills
- Power Query for data cleaning and transformations  
- DAX for calculated measures  
- Data modeling and relationship building  
- Dashboard design and visualization

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

