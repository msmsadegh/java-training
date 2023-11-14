# Controller Machine
- install redis 
  - secure redis
  - ![config redis](./redis.conf)

#### BackEnd
1. venv install
2. clone project (repo is [here](./index.md#components))
3. venv create
```shell
python3 -m venv venv
```
4.  venv activate
```shell
source .env/bin/activate
```

5. install package
```sh
pip3 install -r requirements.txt
```

6. initialize script
```sh
flask create-models-tables # create db 

flask db init --multidb # create migrations dir

# for every update
flask db migrate # make migration
flask db upgrade # migrate
```

7. seed data to mysql
```sh
#Dump DB:
mysqldump -u root -p db_name > file.sql

#Load DB:
msqyl -u root -p db_name < file.sql
```

8. systemd service for backend
9. run backend service
10.  service file for developer

11.   https self-signed certificate

#### OMSService
1. venv install
2. clone project (repo is [here](./index.md#components))
3. venv create
```shell
python3 -m venv venv
```
4.  venv activate
```shell
source .env/bin/activate
```

5. install package
```sh
pip3 install -r requirements.txt
```
5. One or more
    - with different config file
6. systemd service for oms
7. cron for oms:
    - start
    - stop
    - backup

8. run oms service
9. service file for developer

اگر می خواهید به چند پرتفولیو وصل شود به ازای هر پرتفولیو یک بار باید این سرویس ران شود با کانفیگ فایل های متفاوت لازم است

#### Core
1. venv install
2. clone project (repo is [here](./index.md#components))
3. venv create

```shell
python3 -m venv venv
```

4. venv activate

```shell
venv\Scripts\activate
```

5. systemd service for core
6. run core service
7. service file for developer
