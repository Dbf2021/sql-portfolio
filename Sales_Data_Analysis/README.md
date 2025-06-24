 Sales Data Analysis - SQL Portfolio

This project uses SQL (SQLite) to analyze Superstore sales data (9,995 rows). The queries were run in DB Browser for SQLite.

---

  Query 1: Total Sales and Profit by Region

**Purpose:** Analyze which regions bring in the most revenue and profit.

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
Region	0.0	0.0
