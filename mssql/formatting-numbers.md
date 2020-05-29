# Formatting Numbers

Today I was running a query that was deleting millions of records in batches of 1,000,000.  I wanted to log row counts before/during/after the query, with numbers formatted with commas.  Discovered today that this is possible:

```sql
declare @x int = 1234567
declare @s varchar(50)
set @s =  format(@x, 'N0')
print @s	-- 1,234,567
```

