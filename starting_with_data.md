Question 1: find all duplicate records

SQL Queries: 
```
SELECT 
COUNT(DISTINCT visitid) AS TOTA_COUNT
FROM all_sessions;

SELECT 
COUNT(visitid) AS TOTAL_VISITOR
FROM all_sessions;
```
Answer: There is about 600 duplicated values.



Question 2: find the total number of unique visitors (`fullVisitorID`)
```
SQL Queries: 
--counting total number
SELECT COUNT(fullvisitorid)
FROM all_sessions
```
Answer: 14223


Question 3: find the total number of unique visitors by referring sites

SQL Queries: 
```
SELECT
COUNT(Distinct visitid)  --Counting Unique value
FROM analytics
WHERE
channelgrouping ='Organic Search'
```
Answer:17283



Question 4: find each unique product viewed by each visitor

SQL Queries: 
```
SELECT 
DISTINCT v2productname AS PRODUCT_NAME,
fullvisitorid AS VISIOR_ID,
date
FROM all_sessions 
ORDER BY v2productname DESC ,fullvisitorid
```



