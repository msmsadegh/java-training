# Model Machine
- create db: 2 db
  
```sql
CREATE DATABASE oms;
CREATE DATABASE Users;
```
- create db user: oms db and backend db user set sql user host:data_lke-user_admin-backup_user
  
```sql
CREATE USER data_lke@[user_host] IDENTIFIED BY [user_password];
CREATE USER user_admin@[user_host] IDENTIFIED BY [user_password];
CREATE USER backup_user@[user_host] IDENTIFIED BY [user_password];
```
- grant user
  
```sql
GRANT ALL PRIVILEGES ON oms.* TO data_lke@[user_host];
GRANT ALL PRIVILEGES ON Users.* TO user_admin@[user_host];
GRANT ALL PRIVILEGES ON *.* TO backup_user@[user_host];

FLUSH PRIVILEGES;
```

- os and mysql hardening
    - file: cis_oracle_mysql_edition_80.0.pdf (ubuntu-debian)

- dump db from old db
- load data to new db