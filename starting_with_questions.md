Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
```
SELECT
country, city,totalrevenue,channelgrouping 
FROM all_sessions 
WHERE channelgrouping='Direct' AND totalrevenue is not null AND city is not null AND country is not null
ORDER BY totalrevenue DESC
```
Answer: United states with (no city), United states with Palo Alto and Canada with San Jose

**Question 2: What is the average number of products ordered from visitors in each city and country?**

SQL Queries:
```
SELECT
a.country,a.city, AVG(s.total_ordered) 
FROM all_sessions  a 
LEFT JOIN sales_report s on a.productsku =s.productsku
LEFT JOIN analytics b on a.visitid=b.visitid
GROUP BY (s.total_ordered),a.city,a.country
HAVING AVG(S.total_ordered) >0
ORDER BY s.total_ordered DESC,a.city desc,a.country desc
```
Answer:
| First Header  | Second Header | Third Header|
|---------------|---------------|-------------|
|  country      |     City      |       average|
|"India"	    |  "Sunnyvale"	|456.0000000000000000 |
|"United States" | 	"Seoul"	    |456.0000000000000000  |
|"United States" |  "Seattle"	|456.0000000000000000  |
|"United States" |	"Santa Clara"|456.0000000000000000  |
|"United States" |	"San Jose"	 |456.0000000000000000  |   
|"United States" |	"San Jose"	 |456.0000000000000000   |   
|"United States" |	"San Jose"	 |456.0000000000000000   |   
|"United States" |	"San Jose"	 |456.0000000000000000    |  
|"United Kingdom"|	"San Francisco"  |456.0000000000000000  |
|"United States" |    "Pune"	    | 456.0000000000000000  |
 

**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**

SQL Queries:

```
SELECT 
a.country,a.city,a.v2productcategory,AVG(s.total_ordered
FROM all_sessions  a 
LEFT JOIN sales_report s on a.productsku =s.productsku
LEFT JOIN analytics b on a.visitid=b.visitid
GROUP BY (a.v2productcategory),(s.total_ordered),a.city,a.country
HAVING AVG(S.total_ordered) >0
ORDER BY (a.v2productcategory),(s.total_ordered),a.city DESC
```

Answer:  USA is highest with NEST-USA and Seond product is "Home/Shop by Brand/YouTube/" in many countries.


**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:

```
SELECT
a.country,a.city,s.name,(s.total_ordered)
FROM all_sessions  a 
LEFT JOIN sales_report s on a.productsku =s.productsku
GROUP BY(s.name),(s.total_ordered),a.city,a.country
HAVING (S.total_ordered) >0
ORDER BY(s.total_ordered) DESC ,s.name,a.city DESC,a.country DESC
```
Answer: "Ballpoint LED Light Pen" is higest sold in the United States and " Women's Convertible Vest-Jacket Black" is sold 1 in the states.

**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:

```
SELECT
country, city,SUM(totalrevenue)
FROM all_sessions 
Group by city,country,totalrevenue
Having totalrevenue >0 
ORDER BY totalrevenue DESC
```
Answer: Yes but We need correct data for Cities.









