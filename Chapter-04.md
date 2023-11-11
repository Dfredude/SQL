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