### Задание 1

Одним запросом получите информацию о магазине, в котором обслуживается более 300 покупателей, и выведите в результат следующую информацию:

фамилия и имя сотрудника из этого магазина;
город нахождения магазина;
количество пользователей, закреплённых в этом магазине.



```
select count(c.customer_id),s.first_name,s.last_name,c2.city from customer c 
	inner join staff s on  c.store_id = s.store_id 
	inner join address a on a.address_id = s.address_id
	inner join city c2 on c2.city_id = a.city_id 
	group by s.staff_id,s.first_name,c2.city HAVING count(c.customer_id) > 300;
```





### Задание 2

Получите количество фильмов, продолжительность которых больше средней продолжительности всех фильмов.


```
SELECT COUNT(length) FROM film WHERE length > (SELECT AVG(length) FROM film);
```




### Задание 3


Получите информацию, за какой месяц была получена наибольшая сумма платежей, и добавьте информацию по количеству аренд за этот месяц.


```
select COUNT(payment_date),date_format(payment_date , '%b %Y') from payment group by date_format(payment_date , '%b %Y') ORDER by COUNT(payment_date) DESC LIMIT 1;
```

























