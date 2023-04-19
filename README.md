# Exercises-2

*these are more advanced query exercies I did from made-up databases from a made-up company*

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

INSERT INTO products (name, quantity_in_stock, unit_price)

VALUES ('chocolate cupcake', 35, 3.20), ('vanilla cupcake', 40, 3.20), ('red velvet cupcake', 20, 3.50);

*inserting multiple rows into the 'products' table at the same time*

-------------

UPDATE orders

SET comments = 'Gold Customer'

WHERE customer_id IN (SELECT customer_id FROM customers WHERE points > 3000)

*updating comments on orders to say 'Gold Customer' if the customer has greater than 3000 points. uses a subquery to first find the customers who have more than 3000 points*

---------------

USE sql_invoicing;

*doing exercises from the 'invoicing' database*

----------

CREATE TABLE invoices_archived AS

SELECT i.invoice_id, i.number, c.name, i.invoice_total, i.payment_total, i.invoice_date, i.due_date, i.payment_date

FROM invoices i

JOIN clients c

	ON i.client_id=c.client_id
  
WHERE i.payment_date IS NOT NULL

*creating a new table called 'invoices_archived', which would contain old invoices, using a sub-query where a join was made of the 'invoices' and 'clients' tables in order to contain information from multiple tables for the new table 'invoices_archived*

---------------





