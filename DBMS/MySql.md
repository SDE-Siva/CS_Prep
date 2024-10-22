### MySQL Notes for Basic Queries

#### 1. **USE `database_name`;**

- This command selects a database for subsequent operations.
- Example:
  ```sql
  USE my_database;
  ```

#### 2. **SELECT**

- Used to retrieve data from a table.
- Example:
  ```sql
  SELECT * FROM table_name;
  ```
- You can also select specific columns:
  ```sql
  SELECT column1, column2 FROM table_name;
  ```

#### 3. **ORDER BY**

- Sorts the result set based on one or more columns.
- By default, it sorts in ascending order, but you can specify `ASC` (ascending) or `DESC` (descending).
- Example:
  ```sql
  SELECT * FROM employees
  ORDER BY first_name ASC, last_name DESC;
  ```

#### 4. **DISTINCT**

- Used to remove duplicate rows from the result set.
- Example:
  ```sql
  SELECT DISTINCT department FROM employees;
  ```

#### 5. **Aliases (`AS`)**

- Assigns a temporary name to a column or table.
- Example (renaming a column in the result):
  ```sql
  SELECT name, unit_price, unit_price * 1.1 AS "New price"
  FROM products;
  ```
- This gives a new name "New price" to the calculated result of `unit_price * 1.1`.

#### 6. **WHERE**

- Filters records that match a specified condition, similar to conditional statements.
- Example:
  ```sql
  SELECT * FROM products
  WHERE price > 100;
  ```
- You can also use logical operators (`AND`, `OR`, `NOT`) for more complex conditions:
  ```sql
  SELECT * FROM products
  WHERE price > 100 AND stock > 50;
  ```

### Additional Useful Queries:

#### 7. **LIMIT**

- Restricts the number of rows returned by the query.
- Example:
  ```sql
  SELECT * FROM customers
  LIMIT 5;
  ```

#### 8. **IN**

- Checks if a value matches any value in a list of values.
- Example:
  ```sql
  SELECT * FROM orders
  WHERE status IN ('shipped', 'processing');
  ```

#### 9. **BETWEEN**

- Selects values within a given range (inclusive).
- Example:
  ```sql
  SELECT * FROM employees
  WHERE salary BETWEEN 30000 AND 50000;
  ```

#### 10. **LIKE**

- Searches for a specified pattern in a column.
- Example:
  ```sql
  SELECT * FROM employees
  WHERE first_name LIKE 'S%';  -- Names starting with 'S'
  ```

#### 11. **GROUP BY**

- Groups rows that have the same values in specified columns and often used with aggregate functions (`COUNT`, `MAX`, `MIN`, `SUM`, `AVG`).
- Example:
  ```sql
  SELECT department, COUNT(*)
  FROM employees
  GROUP BY department;
  ```

#### 12. **HAVING**

- Used to filter results after the `GROUP BY` clause.
- Example:
  ```sql
  SELECT department, COUNT(*)
  FROM employees
  GROUP BY department
  HAVING COUNT(*) > 10;
  ```

These notes will serve as a solid foundation for preparing MySQL queries. Would you like more notes on advanced topics or specific operations in MySQL?
