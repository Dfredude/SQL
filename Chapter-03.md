## Chapter 3 - Query Primer

### Exercises

#### 3.1

Retrieve the actor ID, first name, and last name for all actors. Sort by last name and then by first name.

```SQL
SELECT actor_id, first_name, last_name 
  FROM actor 
  ORDER BY 3, 2;
```

#### 3.2 

Retrieve the actor ID, first_name, and last name for all actors whose last name equals 'WILLIAMS' or 'DAVIS'

```SQL
SELECT actor_id, first_name, last_name, last_update 
  FROM actor 
  WHERE last_name = 'WILLIAMS' OR last_name = 'DAVIS';
```

#### 3.3

Write a query against the rental table that returns the IDs of the customers who rented a film on july 5, 2005 (use the rental.rental_date column, and you can use the date() function to ignore the time component). Include a single row for each distinct customer ID.

```SQL
SELECT DISTINCT customer_id 
  FROM rental 
  WHERE date(rental_date) = '2005-07-05';
```

#### 3.4

Fill in the blanks (denoted by <#>) for this multitable query to achieve the following results:

```SQL
SELECT c.email, r.return_Date
FROM customer c
  INNER JOIN rental <1>
  ON c.customer_id = <2>
WHERE date(r.rental_date) = '2005-06-14'
ORDER BY <3> <4>;
```

| Values |
|--------|
<1> = r
<2> = r.customer_id
<3> = r.return_date OR 2
<4> = DESC

```SQL
SELECT c.email, r.return_date
FROM customer c
  INNER JOIN rental r
  ON c.customer_id = r.customer_id
WHERE date(r.rental_date) = '2005-06-14'
ORDER BY r.return_date DESC;
```