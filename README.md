************
ÖDEV 1
1- SELECT title,description FROM film;
2- SELECT title,description FROM film WHERE length>60 AND length<75;
3- SELECT * FROM film WHERE rental_rate=0.99 AND replacement_cost=12.99 OR replacement_cost=28.99
4- SELECT last_name FROM customer WHERE first_name='Mary'
5- SELECT * FROM film WHERE NOT length>50 AND (rental_rate=2.99 OR rental_rate=4.99);
*****************************************************************************************

ÖDEV 2
1-SELECT replacement_cost FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99; 
2-SELECT first_name,last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed');
3-SELECT replacement_cost,rental_rate FROM film WHERE (replacement_cost IN (12.99,15.99,28.99) AND (rental_rate IN (0.99,2.99,4.99))); 
******************************************************************************************

ÖDEV 3
1-SELECT country FROM country WHERE country LIKE 'A%a';
2-SELECT country FROM country WHERE country LIKE '%_____n';
3-SELECT title FROM film WHERE title ILIKE '%T%T%T%T%';
4-SELECT title FROM film WHERE title LIKE 'C%' AND (length>90 AND rental_rate=2.99);
********************************************************************************************

ÖDEV 4 
1-SELECT DISTINCT replacement_cost FROM film;
2-SELECT COUNT(DISTINCT replacement_cost) FROM film;
3-SELECT COUNT(*) FROM film WHERE title LIKE 'T%' AND rating='G';
4-SELECT COUNT(*) FROM country WHERE country ILIKE '_____';
5-SELECT COUNT(*) FROM city WHERE city ILIKE '%r';
***********************************************************************************************

ÖDEV 5
1-SELECT title,length FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;
2-SELECT title,length FROM film WHERE title LIKE '%n' ORDER BY length  OFFSET 5 LIMIT 5;
3-SELECT store_id,last_name FROM customer WHERE store_id=1 ORDER BY last_name DESC LIMIT 4;
************************************************************************************************

ÖDEV 6
1-SELECT AVG(rental_rate) FROM film;
2-SELECT COUNT(*) FROM film WHERE title LIKE 'C%';
3-SELECT MAX(length) FROM film WHERE rental_rate=0.99;
4-SELECT COUNT (DISTINCT replacement_cost) FROM film WHERE length>150;
**************************************************************************************************

ÖDEV 7
1-SELECT rating,COUNT(*) FROM film GROUP BY rating;
2-SELECT replacement_cost,COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*)>50 ;
3-SELECT store_id,COUNT(*) FROM customer GROUP BY store_id;
4-SELECT country_id,COUNT(*) FROM city GROUP BY country_id ORDER BY COUNT(*) DESC LIMIT 1 ;
****************************************************************************************************

ÖDEV 8
1-CREATE TABLE employee(
	id INT, 
	name VARCHAR(50),
	birthday DATE,
	email VARCHAR(100));
2-mockaroo
3-UPDATE employee
SET name='DRSRMGL'
WHERE id=4
--SET birthday='2002-10-10'
--WHERE id=3;
--SET birthday='1995-08-15'
--WHERE id=7;

--SET birthday='1987-04-25'
--WHERE id=12;

--SET birthday='1999-12-01'
--WHERE id=9;

RETURNING *;
4-DELETE FROM employee

WHERE id=4

--WHERE id=3;
--WHERE id=7;

--WHERE id=12;

--WHERE id=9;

RETURNING *;
*********************************************************************************************
ÖDEV 9
1-SELECT city,country FROM city
INNER JOIN country ON city.country_id=country.country_id;
2-SELECT first_name,last_name,payment_id FROM payment
INNER JOIN customer ON payment.customer_id=customer.customer_id
3-SELECT first_name,last_name,rental_id FROM rental
INNER JOIN customer ON rental.customer_id=customer.customer_id
**************************************************************************************************************
ÖDEV 10
1-SELECT city,country FROM city
LEFT JOIN country ON country.country_id=city.city_id
2-SELECT payment_id,first_name,last_name FROM customer
RIGHT JOIN payment ON customer.customer_id=payment.customer_id
3-SELECT rental_id, first_name, last_name FROM customer
FULL JOIN rental ON rental.customer_id=customer.customer_id;
*****************************************************************************************************************
ÖDEV 11
1-(SELECT first_name FROM actor)
UNION
(SELECT first_name FROM customer)
2-(SELECT first_name FROM actor)
INTERSECT
(SELECT first_name FROM customer)
3-(SELECT first_name FROM actor)
EXCEPT
(SELECT first_name FROM customer)
4- ALL 
******************************************************************************************************************

