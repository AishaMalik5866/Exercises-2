# Exercises-2

*these are intermediate query exercies I did from made-up databases from a made-up company*

*the database names for the made-up company are sql_invoicing, sql_store, sql_inventory, sql_hr*

-------------------------------------------------------------------------------------------

USE sql_store;

*doing exercises from the 'store' database*

----------

SELECT customer_id, first_name, points, 'Bronze' AS type

FROM customers

WHERE points < 2000

UNION

SELECT customer_id, first_name, points, 'Silver' AS type

FROM customers

WHERE points >= 2000 AND points <= 3000

UNION

SELECT customer_id, first_name, points, 'Gold' AS type

FROM customers

WHERE points > 3000

ORDER BY first_name

---------------






