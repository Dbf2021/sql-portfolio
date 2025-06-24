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

🔹 3. Top 5 Cities by Sales
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

