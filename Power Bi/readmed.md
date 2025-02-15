
# Real Estate Sales Performance Dashboard

## Project Overview
This Power BI dashboard analyzes real estate sales performance, helping stakeholders track sales trends, agent contributions, and revenue distribution across projects. It provides interactive insights into property sales, agent performance, and revenue trends.

## Data Sources
- **Source:** Online datasets (e.g., Kaggle, public real estate data)
- **Dataset Includes:** Property details, sales transactions, agent performance, and time-based sales records.

## Features
- **Dim_Date Table:** Created for proper date-based analysis.
- **DAX Measures for Key Insights:** Custom calculations for total sales, agent contributions, and performance comparisons.

## Measures Used
1. **Total Sales Calculation:** Sums up all sales values.
   ```DAX
   Total Sales = SUM('Real Estate Data'[Sales])
   ```

2. **ALL Sales:** Calculates total sales across all records.
   ```DAX
   ALL = CALCULATE(SUM('Real Estate Data'[Sales]), ALL('Real Estate Data'))
   ```
3. **New Properties Count:** Counts properties categorized as "New Property."
   ```DAX
   New Properties = CALCULATE(COUNT('Real Estate Data'[Properties]), 'Real Estate Data'[Properties] = "New property")
   ```
4. **Previous Year Sales:** Compares current sales with the previous year's performance.
   ```DAX
   Previous Year Sales = CALCULATE('Real Estate Data'[Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]))
   ```
5. **Sold Properties Count:** Counts properties that have been sold.
   ```DAX
   Sold Properties = CALCULATE(COUNT('Real Estate Data'[Properties]), 'Real Estate Data'[Properties] = "Sales")
   ```
6. **Agent Contribution:** Determines each agent's percentage contribution to total sales.
   ```DAX
   Agent Contribution = DIVIDE(SUM('Real Estate Data'[Sales]), 'Real Estate Data'[ALL])
   ```
7. **Sales Performance Indicator (Icon):** Displays an upward or downward arrow based on performance.
   ```DAX
   VAR PositiveIcon = UNICHAR(9650)
   VAR NegativeIcon = UNICHAR(9660)
   VAR Result = IF('Real Estate Data'[Total Sales] > [Previous Year Sales], PositiveIcon, NegativeIcon)
   RETURN Result
   ```
8. **Profit Indicator Color:** Highlights sales performance in green (growth) or red (decline).
   ```DAX
   Icon Profit Color = IF('Real Estate Data'[Total Sales] > [Previous Year Sales], "Green", "Red")
   ```

## Key Visuals
1. **KPI Cards:** Display key metrics such as total sales, previous year sales, and agent performance.
2. **Bar Chart:** Sales by age group.
3. **Line Chart:** Comparison of sold properties vs. new properties.
4. **Aster Plot:** Shows average revenue by project.
5. **Line & Stacked Column Chart:** Displays actual vs. target performance.
6. **Donut Chart:** Stage-wise property count and collection bucket analysis.
7. **Map Visualization:** State-wise sales distribution.
8. **Decomposition Tree:** Revenue breakdown by project category.

##  The Dashboard uses
- **Interactive Filters:** Apply filters to analyze sales by region, property type, and agent.
- **Drill-Down Analysis:** Click on visuals to explore sales performance by different categories.
- **Compare Metrics:** Use KPIs to track growth and profitability over time.


 **Overview Screen**
![image alt](https://github.com/Shohanur97/Portfolio/blob/main/Power%20Bi/Assets/Real%20Estate%20Sales%20Performance%20Dashboard%2001.png)


![image alt](https://github.com/Shohanur97/Portfolio/blob/main/Power%20Bi/Assets/Real%20Estate%20Sales%20Performance%20Dashboard%2002.png)
