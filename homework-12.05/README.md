### Задание 1

Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех индексов к общему размеру всех таблиц.

```
select SUM(table_name),SUM(data_length),SUM(index_length),SUM(index_length)/SUM(data_length)*100 from INFORMATION_SCHEMA.TABLES;
```




### Задание 2


Выполните explain analyze следующего запроса:


перечислите узкие места;

-таблица film присоединена некорректно, "многое ко многим"

оптимизируйте запрос: внесите корректировки по использованию операторов, при необходимости добавьте индексы.

```
create index best_index on payment(payment_date);

explain analyze select concat(c.last_name, ' ', c.first_name), sum(p.amount) from payment p
	inner join rental r on p.payment_date = r.rental_date
	inner join customer c on r.customer_id = c.customer_id
	inner join inventory i on i.inventory_id = r.inventory_id
where p.payment_date >= '2005-07-30' and p.payment_date < DATE_ADD('2005-07-30', INTERVAL 1 DAY)
group by concat(c.last_name, ' ', c.first_name); 

```






























