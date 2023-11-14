# Queue Predict
## Overview
## Versions
- [Version 1](v1.md) (stopped)
- [Version 2](v2.md)
- [Version 3](v3.md)

## Working Flow
![My alt text](../../statics/diagram/queue-pred-v.0.01.drawio)
## Data Gathering

- لیست سهم های مورد بررسی
  
{{ read_csv('./services/queue-prediction/id.csv') }}

## Data Preprocessing
## Points:
- داده های تابلو و ... هر روز جمع آوری می شود
  

- این عملیات برروی سهم هایی که در یک فایل گرآوری شده اند ب انجام میشود )(به خاطر کیفیت رفتار آن سهم ها)


- Confueion Matrix calculated

- به علت کمبود داده و نامتوازن بودن آن ها امکان استفاده از شبکه های عصبی وجود ندارد برای همین مدل های درخت تصمیم استفاده شده است.

## New idea
- Get balanced data