# SQL
Learning SQL: Generate, Manipulate and Retrieve Data

## Chapter 1

### Important Concepts

| Term | Description |
|------|-------------|
| Database | Set of related information |
| Normalization | The process of refining a database design to ensure that each independent piece of information is in only one place (except FKs) is known as normalization. In other words, avoiding an over-redundancy. **(I would improve this definition)**|
| Entity | Something of interest to the database user community * **I hate this definition** * |
| Column | An individual piece of data stored in a table |
| Row | A set of columns that together describe an entity. Also called a record |
| Table | A set of rows |
| Primary Key | Information that uniquely identifies each row. One or more columns that uniquely identify each row in a table |
| Foreign Key | Information that references a row from another table. One or more columns that that uniquely identify each row in a table |


### Database Systems

They have evolved over the years.

         Hierarchical Model
                |
                v
          Network Model
                |
                v
          Relational Model

> 💡 If you leave off the WHERE clause altogether, your UPDATE statement will modify every row in the table.

### SQL Statements
- SQL Schema Statements
- SQL Data Statements
- SQL transaction Statements    

### Data Dictionary
All database elements created via SQL schema statements are stored in a special set of tables called the ***data dictionary*** - Data about the database

### Non-procedural

SQL is a **non-procedural** language in that you may control the results, however you may not control the way the process of doing so is done.

## Chapter 2: Creating and populating 

### mysql Command-Line

> To log in as a root user

```bash
mysql -u root -p 
```
> Log in using database `<database-name>`
```bash
mysql -u root -p <database-name>
```

### mysql interactive mode commands
> Show databases
```SQL
SHOW databases;
```
> Specify which database to use
```SQL
USE <database_name>;
```
> Show table design

```SQL
DESC <table_name>;
```

> Show tables in a database

```SQL
SHOW tables;
```

### Data types
> Temporal data is dates and/or time.

### Table creation

              Design
                |
                v
            Refinement
                |
                v
        SQL Schema Statements

### Common mistakes when inserting or modifying data

- Nonunique Primary Key
- Nonexistent Foreing Key
- Column Value Violations
- Invalid Date Conversions

### Query Clauses

- SELECT
- FROM
- WHERE
- GROUP BY
- HAVING
- ORDER BY

### Table Types

- Permanent tables
- Derived tables
- Temporary tables
- Virtual tables

## Chapter 3

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

## Chapter 4

> **BETWEEN** Operator may be used instead of `<= and >=`

> **IN** operator usable in rows returned by a subquery or any set. Returns True if the item is in the set, False otherwise.

### SQL built-in functions

SQL has many built-in functions.

- `LEFT()`
- `NOW()`
- `LOWER()`
- `UPPER()`

Comparisons to make when filtering data:
- Exact comparison
- Within a range
- In a set
- Partial string match - Wildcard characters or REGEX expressions.

Use the `LIKE` keyword to do a partial string match.
| Wildcard character | Matches |
|--------------------|---------|
|  _ | Exactly one character |
| %  | Any number of characters (including 0) |

> 💀 NULL - An expression can be NULL, but it can never equal NULL - Two nulls are never equal to each other.

### Exercises

#### 4.1
Which of the payment IDs would be returned by the following filter conditions?
```SQL
customer_id <> 5 AND (amount > 8 OR date(payment_date) = '2005-08-23')
```
- 101
- 107

#### 4.2
Which of the payment IDs would be returned by the following filter conditions?
```SQL
customer_id = 5 AND NOT (amount > 6 OR date(payment_date) = '2005-06-19')
```

- 108
- 110
- 111
- 112
- 113
- 115
- 116
- 117
- 118
- 119
- 120

#### 4.3
Construct a query that retrieves all rows from the payments table where the amount is either 1.98, 7.98, or 9.98.
```SQL
SELECT amount
FROM payment
WHERE  amount 
  IN (1.98, 7.98, 9.98);
```

#### 4.4
Construct a query that finds all customers whose last name contains an A in the second position and a W anywhere after the A.

```SQL
SELECT last_name
FROM customer
WHERE last_name LIKE '_A%W%';
```
