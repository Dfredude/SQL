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