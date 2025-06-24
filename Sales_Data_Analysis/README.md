 Sales Data Analysis - SQL Portfolio

This project uses SQL (SQLite) to analyze Superstore sales data (9,995 rows). The queries were run in DB Browser for SQLite.

---

  Query 1: Total Sales and Profit by Region

Purpose: Analyze which regions bring in the most revenue and profit.

```sql
SELECT 
  Region,
  ROUND(SUM(Sales), 2) AS Total_Sales,
  ROUND(SUM(Profit), 2) AS Total_Profit
FROM "Sales Data"
GROUP BY Region
ORDER BY Total_Sales DESC;

West	725457.82	108418.45
East	678781.24	91522.78
Central	501239.89	39706.36
South	391721.91	46749.43
Region	0.0    	0.0

📝 Insight: The West region leads in both revenue and profitability.
Query 2: Total Sales by Category

SELECT 
  Category,
  ROUND(SUM(Sales), 2) AS Total_Sales
FROM "Sales Data"
GROUP BY Category
ORDER BY Total_Sales DESC;

Technology	836154.03
Furniture	741999.8
Office Supplies	719047.03
🧠 Insight:
Technology generated the highest total sales, followed by Furniture and Office Supplies. This suggests that marketing and inventory efforts can be aligned more with the Technology category to maximize revenue.
Query 2: .

Query 3: Top 5 Cities by Sales
SELECT 
  City,
  ROUND(SUM(Sales), 2) AS Total_Sales
FROM "Sales Data"
GROUP BY City
ORDER BY Total_Sales DESC
LIMIT 5;

New York City	256368.16
Los Angeles	175851.34
Seattle	119540.74
San Francisco	112669.09
Philadelphia	109077.01

🧠 Insight:
New York City is the top-performing city in terms of sales. Major urban areas like LA and Seattle also contribute significantly, indicating that urban markets drive higher revenue.
Query 4: Monthly Sales and Profit
SELECT 
  SUBSTR(Order_Date, 7, 4) || '-' || SUBSTR(Order_Date, 4, 2) AS Order_Month,
  ROUND(SUM(Sales), 2) AS Monthly_Sales,
  ROUND(SUM(Profit), 2) AS Monthly_Profit
FROM "Sales Data"
GROUP BY Order_Month
ORDER BY Order_Month;
2014-01	14236.9	2450.19
2014-02	4519.89	862.31
2014-03	55691.01	498.73
2014-04	28295.35	3488.84
2014-05	23648.29	2738.71
2014-06	34595.13	4976.52
2014-07	33946.39	-841.48
2014-08	27909.47	5318.1
2014-09	81777.35	8328.1
2014-10	31453.39	3448.26
2014-11	78628.72	9292.13
2014-12	69545.62	8983.57
2015-01	18174.08	-3281.01
2015-02	11951.41	2813.85
2015-03	38726.25	9732.1
2015-04	34195.21	4187.5
2015-05	30131.69	4667.87
2015-06	24797.29	3335.56
2015-07	28765.33	3288.65
2015-08	36898.33	5355.81
2015-09	64595.92	8209.16
2015-10	31404.92	2817.37
2015-11	75972.56	12474.79
2015-12	74919.52	8016.97
2016-01	18542.49	2824.82
2016-02	22978.82	5004.58
2016-03	51715.88	3611.97
2016-04	38750.04	2977.81
2016-05	56987.73	8662.15
2016-06	40344.53	4750.38
2016-07	39261.96	4432.88
2016-08	31115.37	2062.07
2016-09	73410.02	9328.66
2016-10	59687.75	16243.14
2016-11	79411.97	4011.41
2016-12	96999.04	17885.31
2017-01	43971.37	7140.44
2017-02	20301.13	1613.87
2017-03	58872.35	14751.89
2017-04	36521.54	933.29
2017-05	44261.11	6342.58
2017-06	52981.73	8223.34
2017-07	45264.42	6952.62
2017-08	63120.89	9040.96
2017-09	87866.65	10991.56
2017-10	77776.92	9275.28
2017-11	118447.82	9690.1
2017-12	83829.32	8483.35
 Insight:
Monthly sales and profit show clear seasonality. Sales often peak in November and December, which suggests strong performance during the holiday season.
However, some months like July 2014 and January 2015 had negative or low profits, indicating possible heavy discounts or unprofitable operations during those periods.
This trend helps decision-makers plan inventory and marketing ahead of high-demand periods and investigate months with low profitability for cost optimization.
