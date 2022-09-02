
# Updating  An Entry
```SQL
UPDATE some_table SET field_name = 'some_value' WHERE some_filter
```


# Updating a Table
## Add field
```SQL
ALTER TABLE table_name ADD field_name field_type

--Example
ALTER TABLE users ADD age VARCHAR(3) 
```
## Modify field
```SQL
ALTER TABLE table_name MODIFY COLUMN field_name field_type


--Example:
ALTER TABLE users MODIFY COLUMN age INT(3);
```