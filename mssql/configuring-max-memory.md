# Configuring Max Memory

Working on a customers server today, had 8GB installed, and 7GB was used.  MS-SQL was taking over 6GB.  Best practice seems to be limiting MS-SQL to 50% of what's installed in server.  Used this sql:

```sql
sp_configure 'show advanced options', 1;
GO
RECONFIGURE;
GO
sp_configure 'max server memory', 4096;
GO
RECONFIGURE;
GO
```
