# Query For Maintenance Plan Logs

Easy way find and error that happened during maintenance plan execution: 

```
select top 100 
	* 
from 
	msdb..sysmaintplan_logdetail 
where 
	error_number is not null 
order by 
	start_time desc
```
