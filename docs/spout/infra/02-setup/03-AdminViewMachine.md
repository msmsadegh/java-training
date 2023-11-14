
# Admin View Machine
#### DB create
- laravel read db data from .env file
```sql
CREATE DATABASE db_name;
```
- create user from .env
```sql
CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
```
- add privilage db from .env
```sql
GRANT ALL PRIVILEGE ON [database].* TO 'username'@'host';
```
#### admin view
- clone admin_view
- user owner `./storage` is runner
- install php

```sh
cd ./[project root]

php composer install
```

- db migration

```sh
php artisan migrate
php artisan optimize
```

- create db from .env
