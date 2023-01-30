What issues will you address by cleaning the data?

Make sure Primary key doesn't have duplicated Data.
Remove the columns from all tables which doesn't have any data

Queries:
1. Deleting any column
```
ALTER TABLE anlaytics
DROP COLUMN itemQuantity ;
```

2. Deleting empty rows
```
DELETE FROM
all_sessions WHERE totalrevenue is null ;
```
3. unit price /100000
```
SELECT *, unit_price/(100000) as Unit_price ;
```
4. Deleting total order=0
```
DELETE FROM
sales_by_sku 
WHERE total_ordered =0;
```