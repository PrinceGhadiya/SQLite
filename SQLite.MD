# SQLite all Querys Examples...

1. **SELECT Query Example**:
   ```sql
   SELECT column1, column2, ...
   FROM table_name
   WHERE condition;
   ```

2. **INSERT Query Example**:
   ```sql
   INSERT INTO table_name (column1, column2, column3, ...)
   VALUES (value1, value2, value3, ...);
   ```

3. **UPDATE Query Example**:
   ```sql
   UPDATE table_name
   SET column1 = value1, column2 = value2, ...
   WHERE condition;
   ```

4. **DELETE Query Example**:
   ```sql
   DELETE FROM table_name
   WHERE condition;
   ```

5. **JOIN Example**:
   ```sql
   SELECT column1, column2, ...
   FROM table1
   INNER JOIN table2 ON table1.column_name = table2.column_name;
   ```

6. **CHECK Constraint Example**:
   ```sql
   CREATE TABLE table_name (
       column1 INT CHECK (column1 > 0),
       column2 VARCHAR(50) CHECK (column2 <> '')
   );
   ```

7. **ALTER TABLE Example**:
   ```sql
   ALTER TABLE table_name
   ADD column_name datatype;
   ```

8. **GROUP BY Example**:
   ```sql
   SELECT column1, SUM(column2)
   FROM table_name
   GROUP BY column1;
   ```

9. **HAVING Example**:
   ```sql
   SELECT column1, SUM(column2)
   FROM table_name
   GROUP BY column1
   HAVING SUM(column2) > 100;
   ```

10. **UNION Example**:
    ```sql
    SELECT column1, column2
    FROM table1
    UNION
    SELECT column1, column2
    FROM table2;
    ```

<br>

## Primary Key in SQLite

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100),
    hire_date DATE
);
```
A primary key is a special relational database table column (or combination of columns) designated to uniquely identify each row in the table. It must contain unique values and cannot contain NULL values. The primary key is used to enforce entity integrity in a database, ensuring that each record in a table can be uniquely identified.

In SQL, you can define a primary key when creating a table using the following syntax:

```sql
CREATE TABLE table_name (
    column1 datatype PRIMARY KEY,
    column2 datatype,
    ...
);
```

In this example, "column1" is designated as the primary key. This means that each value in "column1" must be unique and not NULL. If you want to use a combination of columns as a primary key, you can specify multiple columns as the primary key:

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    PRIMARY KEY (column1, column2)
);
```

<br>

## Constraints in SQLite

Sure! Here are some common constraints used in SQL databases along with simple definitions and examples:

1. **Primary Key Constraint**:
   - Definition: Ensures that each row in a table is uniquely identified. It does not allow NULL values.
   - Example:
     ```sql
     CREATE TABLE employees (
         employee_id INT PRIMARY KEY,
         first_name VARCHAR(50),
         last_name VARCHAR(50)
     );
     ```

2. **Foreign Key Constraint**:
   - Definition: Enforces referential integrity by indicating that a column in a table is a foreign key that references the primary key in another table.
   - Example:
     ```sql
     CREATE TABLE orders (
         order_id INT PRIMARY KEY,
         customer_id INT,
         FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
     );
     ```

3. **Unique Constraint**:
   - Definition: Ensures that all values in a column are unique.
   - Example:
     ```sql
     CREATE TABLE users (
         user_id INT PRIMARY KEY,
         username VARCHAR(50) UNIQUE,
         email VARCHAR(100) UNIQUE
     );
     ```

4. **Check Constraint**:
   - Definition: Limits the range of values that can be placed in a column.
   - Example:
     ```sql
     CREATE TABLE employees (
         employee_id INT PRIMARY KEY,
         first_name VARCHAR(50),
         last_name VARCHAR(50),
         age INT CHECK (age >= 18)
     );
     ```

5. **Not Null Constraint**:
   - Definition: Ensures that a column cannot have NULL values.
   - Example:
     ```sql
     CREATE TABLE products (
         product_id INT PRIMARY KEY,
         product_name VARCHAR(100) NOT NULL,
         price DECIMAL(10, 2) NOT NULL
     );
     ```