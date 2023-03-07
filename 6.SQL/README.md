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
|5              |Выведите на экран всю информацию о людях, у которых названия аккаунтов в твиттере содержат подстроку 'money, а фамилия начинается на 'K.|SELECT *<br/>FROM people<br/>WHERE twitter_username LIKE '%money%' AND last_name<br/>LIKE 'K%'|
|6              |
Для каждой страны отобразите общую сумму привлечённых инвестиций, которые получили компании, зарегистрированные в этой стране. Страну, в которой зарегистрирована компания, можно определить по коду страны. Отсортируйте данные по убыванию суммы.|SELECT country_code, SUM(funding_total)<br/>FROM company<br/>GROUP BY country_code<br/>ORDER BY SUM(funding_total) DESC|
|7              |Составьте таблицу, в которую войдёт дата проведения раунда, а также минимальное и максимальное значения суммы инвестиций, привлечённых в эту дату.|SELECT funded_at, MIN(raised_amount), MAX(raised_amount)<br/>FROM funding_round<br/>GROUP BY funded_at<br/>HAVING MIN(raised_amount) != 0 AND MIN(raised_amount) != MAX(raised_amount)|
|8              |Создайте поле с категориями:
Для фондов, которые инвестируют в 100 и более компаний, назначьте категорию high_activity.
Для фондов, которые инвестируют в 20 и более компаний до 100, назначьте категорию middle_activity.
Если количество инвестируемых компаний фонда не достигает 20, назначьте категорию low_activity.
Отобразите все поля таблицы fund и новое поле с категориями.|SELECT *, CASE WHEN invested_companies >= 100 THEN 'high_activity' WHEN invested_companies >= 20 AND invested_companies < 100 THEN 'middle_activity' ELSE 'low_activity' END<br/>FROM fund|
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
