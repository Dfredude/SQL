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

### mysql interactive mdoe commands
> Show databases
```bash
show databases;
```
> Specify which database to use
```bash
use <database-name>;
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