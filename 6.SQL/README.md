# Проект: SQL
## ER-диаграмма ([PDF-версия](/6.SQL/er.pdf)):
![ER-диаграмма](/6.SQL/er_image.PNG)
## Задача 1
Посчитайте, сколько компаний закрылось.

SELECT COUNT(status)
FROM company
WHERE status = 'closed'

## Задача 2
