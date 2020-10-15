# Query Backup History

Intersting parts are:

- Getting physical path from msdb..physical_device_name
- Converting size and compressed size to a friendly string representation

```(sql)
;with suffixes as (
	select 0 as seq,'B' as suffix
	union select 1 as seq, 'KB' as suffix
	union select 2 as seq, 'MB' as suffix
	union select 3 as seq, 'GB' as suffix
	union select 4 as seq, 'TB' as suffix
	union select 5 as seq, 'PB' as suffix
	union select 6 as seq, 'EB' as suffix
)
select 
	bs.database_name
	,bs.backup_start_date
	,bs.backup_finish_date
	,cast(SIGN(bs.backup_size) * ROUND(bs.backup_size / POWER(cast(1024 AS FLOAT), FLOOR(LOG(bs.backup_size,1024))), 1) as varchar)  + ' ' + s1.suffix as backup_size
	,cast(SIGN(bs.compressed_backup_size) * ROUND(bs.compressed_backup_size / POWER(cast(1024 AS FLOAT), FLOOR(LOG(bs.compressed_backup_size,1024))), 1) as varchar)  + ' ' + s2.suffix as compressed_size
	,ms.is_compressed
	,mf.physical_device_name
from 
	msdb.dbo.backupset bs
inner join msdb.dbo.backupmediaset ms on
	ms.media_set_id = bs.media_set_id
inner join msdb.dbo.backupmediafamily mf on
	mf.media_set_id = bs.media_set_id
inner join suffixes s1 on
	s1.seq = FLOOR(LOG(bs.backup_size,1024))
inner join suffixes s2 on
	s2.seq = FLOOR(LOG(bs.compressed_backup_size,1024))
order by
	bs.backup_start_date desc
```
