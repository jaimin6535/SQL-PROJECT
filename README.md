# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
We have given data about Products , Sales report, Revenue , product category. We need to identify which data will be useful to get more insights about most sold products, most revenue generated cities/Countries and product Category.

## Process
### First step is to observe the data.
### Load the data
### Transform the data
### Get the result

## Results
United States has highest Total revenue for Direct Channel grouping.There are three countries which has highest average total ordered.

## Here is the SQL Query

1.

'''
SELECT
country, city,totalrevenue,channelgrouping 
FROM jaimin.all_sessions 
WHERE channelgrouping='Direct' AND totalrevenue is not null AND city is not null AND country is not null
ORDER BY totalrevenue DESC
'''

## Challenges 
  1. Identify correct Data types
  2. Identify required Data
  3. Identify relation between all files(all tables)
  

## Future Goals
Explore these data sets in more depth to gain more insights about how to increase sales, how to make future prediction of sales trend.

