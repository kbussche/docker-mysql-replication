# Notes

## Start
docker-compose down && docker-compose -f docker-compose.yml  up -d


## Connect
```
docker-compose exec master bash
```
or
```
docker-compose exec slave bash
```

## Privs
```
GRANT REPLICATION SLAVE ON *.* TO 'repl'@'%' identified by 'fizzle';
CHANGE master to master_host='master', master_port=3306, master_user='repl', master_password='fizzle', master_log_file='master.000001', master_log_pos=0;
```

## Viewing
```
show slave status\G
show master status\G
```

## Setup
Create a database and a table

```
create database stuff
create table test (id int(11) auto_increment primary key);
```

## Misc
```
mysqlbinlog <filename>

set global sql_slave_skip_counter=1;
```
