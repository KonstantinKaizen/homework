### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию:

фамилия и имя сотрудника из этого магазина;
город нахождения магазина;
количество пользователей, закреплённых в этом магазине.


```
select c.store_id,count(c.customer_id) from customer c  join staff s on  c.store_id = s.store_id  group by c.store_id HAVING count(c.customer_id) > 300;
```


```
ОШИБКА

select c.store_id,count(c.customer_id),s.first_name  from customer c  join staff s on  c.store_id = s.store_id  group by c.store_id HAVING count(c.customer_id) > 300;
```





### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.


```
SELECT COUNT(length) FROM film WHERE length > (SELECT AVG(length) FROM film);
```




### Задание 3


Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.


```
select COUNT(payment_date),month(payment_date) from payment group by month(payment_date) ORDER by COUNT(payment_date) DESC LIMIT 1;
```

























