# Convert UTC to Local Timstamp

```
declare @utcNow datetime2 = SYSUTCDATETIME()

select 
	@utcNow as UtcNow
	,CONVERT(datetime, SWITCHOFFSET(CONVERT(datetimeoffset, @utcNow), DATENAME(TzOffset, SYSDATETIMEOFFSET()))) as LocalNow
```

Output

```
UtcNow                      LocalNow                    LocalNowString
--------------------------- --------------------------- -----------------------------
2020-09-28 19:36:37.0081538 2020-09-28 15:36:37.0081538 2020-09-28 03:36:37 PM

(1 row(s) affected)
```

Notes:
- Local timezone value is returned in military time
