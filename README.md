1) Вывести все имена из таблицы customers;

   SELECT first_name
   FROM EDU.customers;

3) Вывести все записи, где регион = юг из таблицы customers;

   SELECT district
   FROM EDU.customers
   WHERE district = 'South';

   SELECT district
   FROM EDU.customers
   WHERE district IN ('South');

   SELECT district
   FROM EDU.customers
   WHERE district LIKE '%South%';

5) Вывести количество клиентов из западного региона из таблицы customers;

   SELECT COUNT(district) AS client_west
   FROM EDU.customers
   WHERE district = 'West';

7) Вывести максимальное, среднее и минимальное значение заказов за год из таблицы year_statistics;

  SELECT MAX(amount_of_orders) AS MAX,
	  AVG(amount_of_orders) AS AVG,
	  MIN(amount_of_orders) AS MIN
  FROM EDU.year_statistics;

9) Вывести один самый старый заказ из таблицы delivery_list;

   SELECT MIN(date_arrived) AS Min_Date
   FROM EDU.delivery_list;

10) Вывести все записи, где есть курьеры kate и bob из таблицы courier_info;

    SELECT *
    FROM EDU.courier_info
    WHERE first_name IN ('Kate', 'Bob');

12) Вывести статистику по месяцам, где общее количество заказов превысило 351 в месяц из таблицы year_statistics;

   SELECT month_name, amount_of_orders
   FROM EDU.year_statistics
   WHERE amount_of_orders > 351;

14) Вывести статистику по месяцам, где общее количество заказов равняется и меньше 350 в месяц из таблицы year_statistics;

   SELECT month_name, amount_of_orders
   FROM EDU.year_statistics
   WHERE amount_of_orders <= 350;

16) Вывести все записи из таблицы за зиму и весну из таблицы из таблицы year_statistics;

   SELECT *
   FROM EDU.year_statistics
   WHERE id_month IN (12, 1, 2, 3, 4, 5);

18) Вывести 5 свежих заказов, которые оплатили картой из таблицы delivery_list.

   SELECT TOP 5 *
   FROM EDU.delivery_list
   WHERE payment_method IN ('Card');

Задание cо звёздочкой*


11) Необходимо запросом подсчитать количество строк в таблице customers;

   SELECT COUNT(*) AS Sum_Records
   FROM EDU.customers;

13) Вывести все имена, где есть буква A, из таблицы customers;

   SELECT first_name
   FROM EDU.customers
   WHERE first_name LIKE '%A%';

15) Запросом перевести строку в верхний регистр, а так же обозвать колонку 'name'. Данные взять из таблицы customers, колонка first_name;

   SELECT UPPER(first_name) AS name
   FROM EDU.customers;

17) С помощью функции вывести цену с округлением до десятичного числа. Использовать табличку products, вывести столбцы: цена, название.

   SELECT menu_name, ROUND(price, 1)
   FROM EDU.products;



