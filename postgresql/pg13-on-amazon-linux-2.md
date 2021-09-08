# Postgres on Amazon Linux 2

- Start an instance
	- i3.8xlarge 
		- 32 vcpu
		- 244gb ram
		- 4x1900gb nvme 
	
	- R5B

- Update installed packages

`sudo yum -y update`

- Enable  EPEL repository

`sudo amazon-linux-extras install epel`

- Add PGDG repository  to Yum 

Create `/etc/yum.repos.d/pgdg.repo` with following content

```
[pgdg13]
name=PostgreSQL 13 for RHEL/CentOS 7 - x86_64
baseurl=https://download.postgresql.org/pub/repos/yum/13/redhat/rhel-7-x86_64
enabled=1
gpgcheck=0
```

- Install Postgresql 13

`sudo yum install postgresql13 postgresql13-server`

- Install postgresql13-contrib for stuff like pgbench

`sudo yum install postgresql13-contrib`

- Allow Remote connections
- Initialize database

`sudo /usr/pgsql-13/bin/postgresql-13-setup initdb`

- Set databse to start on boot

`sudo systemctl enable --now postgresql-13`

- Check status of PostgreSQL 13

`systemctl status postgresql-13` 

- Stop

`sudo systemctl stop postgresql-13`

- List avail disks

`sudo lsblk`

- Format NVMe disk as EXT4

`mkfs.ext4 -E nodiscard /dev/nvme0n1`
`mkfs.ext4 -E nodiscard /dev/nvme1n1`
`mkfs.ext4 -E nodiscard /dev/nvme2n1`
`mkfs.ext4 -E nodiscard /dev/nvme3n1`

Default is 4096 block size

- Create directory for database

`mkdir /data`
`mkdir /data/incoming`

- Mount the NVMe disk 

`sudo mount /dev/nvme0n1 /data/incoming`

- Set permissions

`sudo chown postgres:postgres /pgdata`

- Create tablespace

`create tablespace pgdata location '/pgdata';`

- Create database on that tablespace

`create database dbname with tablespace=pgdata;`

- Add a user

`create user foo with password 'bar';`

- Give user all permissions in database just created

`grant all privileges on database dbname to foo;`

- Configure Postgres to allow incoming TCP connections
	- edit postgresql.conf and add following line at end
	- set `listen_addresses = '*'`

- Relax permissions for remote connections
	- edit pg_hba.conf
		- add `host all all 0.0.0.0/0 md5`
	- edit pg_ident.conf
		- add 'hoss ec2-user hoss' at bottom

- Stop Postgres

`sudo systemctl stop postgresql`




