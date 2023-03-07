# Проект: SQL
## ER-диаграмма ([PDF-версия](/6.SQL/er.pdf)):
![ER-диаграмма](/6.SQL/er_image.PNG)
## Задачи:
| Номер задачи | Описание задачи | Функция                                                     |
|---------------|-------------------|------------------------------------------------------------------|
|1              |Посчитайте, сколько компаний закрылось.|SELECT COUNT(status)<br/>FROM company<br/>WHERE status = 'closed'|
|2              |Отобразите количество привлечённых средств для новостных компаний США. Используйте данные из таблицы company. Отсортируйте таблицу по убыванию значений в поле funding_total.|SELECT SUM(funding_total) AS ft<br/>FROM company<br/>WHERE country_code = 'USA' AND category_code = 'news'<br/>GROUP BY name<br/>ORDER BY ft DESC|
|3              |Найдите общую сумму сделок по покупке одних компаний другими в долларах. Отберите сделки, которые осуществлялись только за наличные с 2011 по 2013 год включительно.|SELECT SUM(price_amount)<br/>FROM acquisition<br/>WHERE term_code = 'cash' AND CAST(acquired_at AS date)<br/>BETWEEN '2011-01-01' AND '2013-12-31'|
|4              |Отобразите имя, фамилию и названия аккаунтов людей в твиттере, у которых названия аккаунтов начинаются на 'Silver'.|SELECT first_name, last_name, twitter_username<br/>FROM people<br/>WHERE twitter_username LIKE 'Silver%'|
|5              |||
|6              |||
|7              |||
|8              |||
|9              |||
|10             |||
|11             |||
|12             |||
|13             |||
|14             |||
|15             |||
|16             |||
|17             |||
|18             |||
|19             |||
|20             |||
|21             |||
|22             |||
|23             |||
|24             |||
