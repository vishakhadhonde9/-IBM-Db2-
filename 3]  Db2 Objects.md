#  Db2 Objects -
- Db2 objects are the structural elements used to organize, store, and manage data within an IBM Db2 relational database system. 
- These components range from physical data storage structures (like databases, table spaces, and tables) to logical objects (like views, indexes, and triggers).

# 1. Database -
- Database is a logical grouping of related data and database objects.
- It provides an organizational structure for storing and managing tablespaces, tables, indexes, and other objects.

    CREATE DATABASE db_name;

# 2. Schema
Schema is a logical collection of database objects.

## why we use schema -
- **Organize Database Objects:** Groups related objects together for easier management.
- **Avoid Naming Conflicts:** Different users can create objects with the same name in different schemas.
- **Improve Security:** Permissions can be granted at the schema level instead of individual objects.
- **Simplify Administration:** Makes database maintenance and object management easier.
- **Support Multiple Applications:** Different applications can have their own schemas within the same database.
- **Provide Logical Separation:** Separates objects based on departments, projects, or users.

# Create Schema:

        CREATE SCHEMA schema_name;

## Schema Naming Conventions
- 1. Use Meaningful Names: Choose names that reflect the department, application, or purpose.
- 2. Use Uppercase for Consistency: Db2 stores unquoted identifiers in uppercase by default.
- 3. Avoid Special Characters: Use letters, numbers, and underscores.
- 4. Must Start with a Letter
- 5. Length Limit: In Db2, a schema name can be up to 128 characters long.
- 6. Allowed Characters: A–Z, 0–9 and Underscore (_)
- 7. Do not use SQL keywords as schema names.
- 8. Schema Names Must Be Unique within a database.





# 3. Table Space
- Tablespace is a storage structure that holds table data.

    CREATE TABLESPACE tablespace_name
    IN db_name;

4. Table
- Table stores data in rows and columns.
        
        CREATE TABLE table_name
        (
            column1 datatype,
            column2 datatype,
            column3 datatype
        );

- Example:

          CREATE TABLE table_name
          (
              id INTEGER,
              name VARCHAR(50),
              salary DECIMAL(10,2)
          );

# 5. Constraint
- Constraints enforce data integrity rules.
- Primary Key

        CREATE TABLE table_name
        (
            id INTEGER PRIMARY KEY,
            name VARCHAR(50)
        );

- Foreign Key

        CREATE TABLE child_table
        (
            id INTEGER,
            parent_id INTEGER,
            FOREIGN KEY(parent_id)
            REFERENCES parent_table(id)
        );
Unique
CREATE TABLE table_name
(
    email VARCHAR(100) UNIQUE
);
Check
CREATE TABLE table_name
(
    age INTEGER CHECK (age >= 18)
);
Not Null
CREATE TABLE table_name
(
    name VARCHAR(50) NOT NULL
);
6. Index

An index improves query performance.

CREATE INDEX index_name
ON table_name(column_name);
7. View

A view is a virtual table based on a query.

CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name;
8. Alias

An alias provides an alternate name for a table or view.

CREATE ALIAS alias_name
FOR table_name;
9. Synonym

A synonym is another name for a table or view.

CREATE SYNONYM synonym_name
FOR table_name;
10. Trigger

A trigger executes automatically when data changes.

CREATE TRIGGER trigger_name
AFTER INSERT
ON table_name
FOR EACH ROW
BEGIN ATOMIC
   -- SQL Statements
END;
11. Sequence

A sequence generates unique numeric values.

CREATE SEQUENCE sequence_name
START WITH 1
INCREMENT BY 1;

Using a sequence:

NEXT VALUE FOR sequence_name;
12. Cursor

A cursor processes query results one row at a time.

DECLARE cursor_name CURSOR FOR
SELECT column_name
FROM table_name;

OPEN cursor_name;

FETCH cursor_name
INTO variable_name;

CLOSE cursor_name;
13. Stored Procedure

A stored procedure is a collection of SQL statements stored in the database.

CREATE PROCEDURE procedure_name()
LANGUAGE SQL
BEGIN
   SELECT * FROM table_name;
END;
14. User Defined Function (UDF)

A UDF is a user-created function.

CREATE FUNCTION function_name
(
    input_parameter INTEGER
)
RETURNS INTEGER
RETURN input_parameter * 10;
15. User Defined Type (UDT)

A UDT is a custom data type derived from an existing type.

CREATE TYPE type_name
AS VARCHAR(20)
FINAL;
16. Usage List

A usage list records DML activity on tables and indexes.

CREATE USAGELIST usage_list_name;









