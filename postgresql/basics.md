# Postgresql Basics

## Install/Config

### MacOS

- brew install postgresql
- Auto Start: `brew services start postgresql`
- Start Foreground: `pg_ctl -D /usr/local/var/postgres start`
- Default database cluster created in `/usr/local/var/postgres`
	- This is like a MS-SQL instance: a collection of databases
- Security
	- There is no default user
- psql command line
	'-l': List Databases
	'-d <dbname>': specify database if not specified default dbname is username
- config file location: `/var/lib/psql/13/data`


### Grouping

- Group by with count:  `select whse_nmbr, to_char(count(*), '9,999,999,999') as cust_count from customer group by rollup (whse_nmbr) order by cust_count`

### String Formatting
- Format number: `select to_char(12345.67, '99,999.99'); --> 12,345.67
- Concat: `select '[' || 'foo' || ']';` --> [foo]

### System Info
- Show config file locations: `show config_file`

