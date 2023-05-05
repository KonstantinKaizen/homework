### Задание 1

Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех индексов к общему размеру всех таблиц.

```
select SUM(table_name),SUM(data_length),SUM(index_length),SUM(index_length)/SUM(data_length)*100 from INFORMATION_SCHEMA.TABLES;
```




### Задание 2


Выполните explain analyze следующего запроса:

```
select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
from payment p, rental r, customer c, inventory i, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id
```
---

```
 ![alt text](https://github.com/KonstantinKaizen/homework/blob/main/homework-12.05/1.png)
```




























