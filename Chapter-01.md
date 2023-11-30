## Chapter 1 - A little background

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
| Foreign Key | Information that references a row from another table. One or more columns that uniquely identify each row in a table |


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

SQL is a **non-procedural** language in that you may control the results, however, you may not control the way the process of doing so is done.
