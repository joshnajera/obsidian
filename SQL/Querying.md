
# Query
```SQL
SELECT fields FROM table_name [OPTIONAL]

```
## Nested query
```SQL
SELECT fields FROM table_name WHERE table_name.id IN (
	SELECT id FROM table_name_2 WHERE where_clause
)
-- Example:     Select employee names who made total sales more than $30,000
SELECT employee.first_name FROM employee WHERE employee.id IN (
	SELECT sales.employee_id FROM sales WHERE sales.total_sales > 30000
);
```


More specific results can be acheived with [[Filtering]]
[[Logical Operators]] can be to combine & get more specific.
Search results can be optimized with [[Indexes]]
Tables can be [[Joining|joined]] together for more complex queries.
[[Aggregate|Aggregate functions]] can be applies to combine/modify results

# Ordering
#ordering #ascending #descending
```SQL
SELECT fields FROM table_name ORDER BY field ASC;
SELECT fields FROM table_name ORDER BY field DESC;
```


# Modifying results
#concatenation #concat
```SQL
-- Concatenation of a field, with an alias
SELECT CONCAT(first_name, ' ', last_name) AS 'name', department FROM users;
```
#unique #distinct
```SQL
-- Distinct& Unique
SELECT DISTINCT field FROM some_table;
```