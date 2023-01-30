# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
We have given data about Products , Sales report, Revenue , product category. We need to identify which data will be useful to get more insights about most sold products, most revenue generated cities/Countries and product Category.

## Process
  1. First step is to observe the data
  2. Load the data
  3. Make the relation between tables
  4. Transform the data
  5. Get the result

## Results
United States has highest Total revenue for Direct Channel grouping.There are three countries which has highest average total ordered.

"Ballpoint LED Light Pen" is higest sold in the United States and " Women's Convertible Vest-Jacket Black" is sold 1 in the states.

## Challenges 
  1. Identify correct Data types
  2. Identify required Data
  3. Identify relation between all files(all tables)
  

## Future Goals
Explore these data sets in more depth to gain more insights about how to increase sales, how to make future prediction of sales trend.

## Here is the SQL Query

1.

```
SELECT
country, city,totalrevenue,channelgrouping 
FROM all_sessions 
WHERE channelgrouping='Direct' AND totalrevenue is not null AND city is not null AND country is not null
ORDER BY totalrevenue DESC ;
```

2.
``` 
SELECT
a.country,a.city,s.name,(s.total_ordered) from jaimin.all_sessions  a 
LEFT JOIN sales_report s on a.productsku =s.productsku
GROUP BY(s.name),(s.total_ordered),a.city,a.country
HAVING (S.total_ordered) >0
ORDER BY(s.total_ordered) DESC ,s.name,a.city DESC,a.country DESC ;
```


