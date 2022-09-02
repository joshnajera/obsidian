# Union
Combines results from different select statements into a single place.
Unlike joining, it does not use a common field to match up anything.
The number of fields being selected from each table has to be equal.
They both have to have a similar datatype as well.
```SQL
SELECT fields FROM table_name UNION SELECT fields_2 FROM table_name_2;
SELECT fields AS new_field_name FROM table_name UNION SELECT fields_2 FROM table_name_2;

-- Example:
SELECT first_name FROM users UNION SELECT 
```