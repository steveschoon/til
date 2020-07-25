# Cursor Demo

```sql
declare @storeId int
declare curStoreId cursor for select StoreId from StoreConfig where SoftwareVersion <> 'HQ'
open curStoreId
fetch next from curStoreId into @storeId
while @@FETCH_STATUS = 0 begin
	select @storeId
	fetch next from curStoreId into @storeId
end
close curStoreId
deallocate curStoreId
```
