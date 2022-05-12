# MySql Timezone Stuff

## @@global.timezone

Show mysql server configured timezone

`select @@global.time_zone`

SYSTEM: follow system's timezone

## Getting Current Time

```
select now(); -- 2022-05-11 13:41:53
select now(6); -- 2022-05-11 13:41:53.633788
select utc_timestamp(); -- 2022-05-11 17:41:53
select utc_timestamp(6); -- 2022-05-11 17:41:53.667698
```

## convert_tz() - convert between timezones

This converts from EST to UTC

```
update promotion_header set
	start_date = convert_tz(start_date, '-04:00', '+00:00')
	,end_date = convert_tz(end_date, '-04:00', '+00:00')
```

