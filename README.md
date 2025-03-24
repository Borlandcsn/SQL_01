-- 1) Вывести все имена из таблицы customers
SELECT DISTINCT first_name FROM EDU.customers;

-- 3) Вывести все записи, где регион = 'South'
SELECT * FROM EDU.customers WHERE district = 'South';

-- 5) Вывести количество клиентов из западного региона
SELECT COUNT(*) AS client_west FROM EDU.customers WHERE district = 'West';

-- 7) Вывести макс., среднее и мин. значение заказов за год
SELECT 
    MAX(amount_of_orders) AS max_orders, 
    AVG(amount_of_orders) AS avg_orders, 
    MIN(amount_of_orders) AS min_orders
FROM EDU.year_statistics;

-- 9) Вывести один самый старый заказ
SELECT * FROM EDU.delivery_list ORDER BY date_arrived ASC LIMIT 1;

-- 10) Вывести все записи, где курьеры Kate и Bob
SELECT * FROM EDU.courier_info WHERE first_name IN ('Kate', 'Bob');

-- 12) Статистика по месяцам, где заказов > 351
SELECT month_name, amount_of_orders FROM EDU.year_statistics WHERE amount_of_orders > 351;

-- 14) Статистика по месяцам, где заказов ≤ 350
SELECT month_name, amount_of_orders FROM EDU.year_statistics WHERE amount_of_orders <= 350;

-- 16) Вывести все записи за зиму и весну
SELECT * FROM EDU.year_statistics WHERE id_month >= 12 OR id_month <= 5;

-- 18) Вывести 5 свежих заказов, оплаченных картой
SELECT * FROM EDU.delivery_list WHERE payment_method = 'Card' ORDER BY date_arrived DESC LIMIT 5;

-- 11) Подсчитать количество строк в таблице customers
SELECT COUNT(*) AS total_customers FROM EDU.customers;

-- 13) Вывести все имена, содержащие букву 'A' (учитывая регистр)
SELECT first_name FROM EDU.customers WHERE first_name ILIKE '%a%';

-- 15) Перевести first_name в верхний регистр и назвать 'name'
SELECT UPPER(first_name) AS name FROM EDU.customers;

-- 17) Округлить цену до 1 знака после запятой и вывести с названием
SELECT menu_name, ROUND(price, 1) AS rounded_price FROM EDU.products;
