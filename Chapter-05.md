## Chapter 5

### Exercises

#### 5.1

Fill in the blanks (denoted by <#>) for the following query to obtain the results that follow:
```SQL
SELECT c.first_name, c.last_name, a.address, ct.city
FROM customer c
  INNER JOIN address <1>
  ON c.address_id = a.address_id
  INNER JOIN city ct
  ON a.city_id = <2>
WHERE a.district = 'California'; 
```

```
<1> a
<2> ct.city_id
```

#### 5.2 

Write a query that returns the title of every film in which an actor with the first name JOHN apeared.

```SQL
SELECT f.title
FROM film f
  INNER JOIN film_actor fa
  ON f.film_id = fa.film_id
  INNER JOIN actor a
  ON fa.actor_id = a.actor_id
WHERE a.first_name = "JOHN";
```

#### 5.3

Construct a query that returns all addresses that are in the same city. You will need to join the address table to itself, and each row should include two different addresses.

```SQL
SELECT a1.address addres_1, a2.address address_2, a1.city_id city
FROM address a1
  INNER JOIN address a2
  ON a1.city_id = a2.city_id AND a1.address_id < a2.address_id;
```