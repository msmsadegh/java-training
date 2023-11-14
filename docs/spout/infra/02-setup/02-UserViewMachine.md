
# User View Machine
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
#### user view
- clone user_view
- user owner `./storage` is runner
- install php

```sh
cd ./[project root]

php composer install
```

- db migration

```sh
php artisan migrate
```

- create db from .env

#### build front
- clone user-frontend
- install node
- `cd ./[project root]`
- npm install

```sh
# install dependencies
$ npm install
```

- npm run generate
```sh
# install dependencies
$ npm run generate
```
- copy `./dist` to the `./user-view/public`

