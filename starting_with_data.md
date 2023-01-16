Question 1: find all duplicate records

SQL Queries: 
SELECT 
COUNT(DISTINCT visitid) FROM all_sessions;
SELECT 
COUNT(visitid) FROM all_sessions;

Answer: There is about 600 duplicated values.



Question 2: find the total number of unique visitors (`fullVisitorID`)

SQL Queries: SELECT COUNT(fullvisitorid)  FROM all_sessions

Answer: 14223



Question 3: find the total number of unique visitors by referring sites

SQL Queries: SELECT COUNT(Distinct visitid) FROM analytics where channelgrouping ='Organic Search'

Answer:17283



Question 4: find each unique product viewed by each visitor

SQL Queries: 

SELECT 
DISTINCT v2productname, fullvisitorid, date FROM all_sessions 
ORDER BY v2productname DESC ,fullvisitorid




Question 5:  compute the percentage of visitors to the site that actually makes a purchase

SQL Queries:

Answer:
