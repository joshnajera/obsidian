Adding indexes allow you to get faster searches on specific fields

```SQL
CREATE INDEX index_name on table_name(field_name);

--Example:
CREATE INDEX LIndex on users(location);
```

```SQL
DROP INDEX index_name on table_name;

--Example:
DROP INDEX Lindex on users
```