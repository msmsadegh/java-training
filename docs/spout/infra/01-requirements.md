# Requirement

| **Requirement**   | **version** |**Machine**|
|-------------------|-------------|-----------|
| **python**        | 3\.8        |Controller |
| **venv?**         |||
| **mariadb**       | 10\.3\.25   |Model      |
| **redis**         | 5\.0\.7     |Controller |
| **php**           | 7\.3        |View User  |
| **php**           | 8\.*        |View Admin |
| **mysql admin**   | 8\.0\.31    |View Admin |
| **maria db user** | 10\.3\.25   |View User  |
| **laravel admin** | 8\.77\.1    |View Admin |
| **laravel user**  | 7\.30\.4    |View User  |
| **php composer**  | 2           |View User  |
| **php composer**  | 2           |View Admin |
| **apache**        |||

composer.json --> php composer
docker compose ?

## Monitoring:

- os level:
    - hard
    - ram
    - cpu
- health check
    - 200 ok
    - json with usefully data
        - pyzabix
        - send metrics
        - check SNMP
- component connection
    - ws
- log
    - ELK

## Requirement:

- اضافه شدن سیستم تیکتینگ
- پشتیبانی باید شماره عوض شود - شماره پشتیبان باشد
- قابلیت ری استارت کردن کور اسپات
- چک کردن اعمال کران اتفاق می افتد یا نه؟
- اسکریپت:
    - مایگریشن ها
    - پر کردن ردیس
    - بررسی صحت عملکرد پنل ادمین
    - گزارش های ماهانه


- ارتباط بین ماشینی در داخل رمز شده نیست
- تدوین فرآیند تغییر کلید