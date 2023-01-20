What are your risk areas? Identify and describe them.

Risk areas are remove duplicated data, Identify Primary key for analytics table.


QA Process:


First step is to make our query readable.
Use Aliases for clear readablility.
Break queries into multiple sub queries.
Add useful comments.
Unit test
Integration Testing

-- Deleting empty rows
DELETE FROM
all_sessions WHERE totalrevenue is null ;

--Unit Test
SELECT
a.country AS Country,
a.city AS City,
s.name  AS Name,
(s.total_ordered) AS Total_ORDER 
FROM all_sessions 


--Integration

SELECT
a.country AS Country,
a.city AS City,
s.name  AS Name,
(s.total_ordered) AS Total_ORDER 
FROM all_sessions  a 
LEFT JOIN

sales_report s on a.productsku =s.productsku
GROUP BY(s.name),(s.total_ordered),a.city,a.country
HAVING (S.total_ordered) >0
ORDER BY(s.total_ordered) DESC 
,s.name,a.city DESC,a.country DESC
