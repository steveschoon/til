# MySQL Basics

### mysql.server
| Action | Command |
| ------ | ------- |
|Install with HomeBrew|`brew install mysql`|
|Start|`mysql.server start`|
|Stop|`mysql.server stop`|
|Command line client|<pre>mysql -u**user** -p**pass**</pre>|

### Queries
- List all databases  
	- `SHOW DATABASES;` or `SHOW SCHEMA;`
- Create a user with native password auth
	- `CREATE USER 'someuser'@'localhost' IDENTIFIED WITH mysql_native_password BY 'somepassword';`
- Grant all permissions to a user on a database
	- `GRANT ALL ON somedb.* TO 'someuser'@'localhost';`

