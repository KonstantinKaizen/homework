

### Задание 1

Создайте учётную запись sys_temp.
```
CREATE USER sys_temp1@localhost IDENTIFIED BY '12345';
```
---
Выполните запрос на получение списка пользователей в базе данных.
```
SELECT user FROM mysql.user; скрин
```
---
Дайте все права для пользователя sys_temp.
```
GRANT ALL PRIVILEGES ON *.* to bill@localhost WITH GRANT OPTION;
```
---
Выполните запрос на получение списка прав для пользователя sys_temp
```
SHOW GRANTS FOR sys_temp1@localhost;
```
---
Переподключитесь к базе данных от имени sys_temp.
```
SYSTEM mysql -u sys_temp1 -p
```
---
Восстановите дамп в базу данных.
```
SOURCE C:\Users\CHYEAH\Desktop\sakila-db\sakila-data.sql
```
---
При работе в командной строке используйте команду для получения всех таблиц базы данных.
```
SHOW TABLES FROM sakila;
```
---

![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-12.02/1.png)
---
![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-12.02/2.png)
---
![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-12.02/3.png)





### Задание 2

Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц.
```
---------------------------|---------
actor                      |actor_id
actor_info                 |
address                    |address_id
category                   |category_id
city                       |city_id
country                    |country_id
customer                   |customer_id
customer_list              |ID
film                       |film_id
film_actor                 |actor_id
film_category              |category_id
film_list                  |FID
film_text                  |film_id
inventory                  |inventory_id
language                   |language_id
nicer_but_slower_film_list |FID
payment                    |payment_id
rental                     |rental_id
sales_by_film_category     |
sales_by_store             |
staff                      |staff_id
staff_list                 |ID
store                      |store_id
---------------------------|---------
```

```
SHOW COLUMNS FROM store FROM sakila
```

















