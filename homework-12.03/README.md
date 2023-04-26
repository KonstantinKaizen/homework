

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.


```
SELECT DISTINCT district FROM address WHERE district LIKE 'K%a' AND district NOT LIKE '% %';
```


### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.


```
SELECT * FROM payment WHERE payment_date BETWEEN '2005-06-15 00:00:00' AND '2005-06-18 23:59:59' AND amount>10;
```





### Задание 3

Получите последние пять аренд фильмов.

```
SELECT * FROM payment ORDER BY payment_date DESC LIMIT 5;
```




### Задание 4


Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
замените буквы 'll' в именах на 'pp'.


```
SELECT last_name , LOWER(REPLACE(first_name, 'LL', 'PP')) FROM customer WHERE first_name LIKE 'Kelly' OR first_name LIKE 'Willie';
```















