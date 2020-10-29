# Query Trigger Enabled or Disabled

Basic way:

```sql
SELECT 
	name, 
	is_disabled 
FROM 
	sys.triggers
```

Little bit nicer to get the table names too, and list disabled triggers first

```sql
SELECT 
	OBJECT_NAME(parent_id) as [table_name],
	[name] as [trigger_name],
	is_disabled
FROM 
	sys.triggers 
ORDER BY 
	is_disabled desc,
	table_name,
	trigger_name
```

