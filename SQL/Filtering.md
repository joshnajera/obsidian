#filter

[[Logical Operators]] can be used in combination

# Where Clause
#where
```SQL
SELECT some_selection FROM some_table WHERE conditional_clause;

-- Example:
SELECT * FROM users WHERE is_admin >0;
SELECT * FROM users WHERE location ='California';
```


Multiple WHERE  clauses

```SQL
SELECT some_selection FROM some_table WHERE conditional_clause AND|OR conditional_clause;

--Example: 
SELECT * FROM users WHERE is_admin >0 AND location='California';
```


# Existence
#in
If field is in a collection of values
```SQL
SELECT fields FROM some_table WHERE some_field IN (some_CSV_values)

--Example:
SELECT * FROM users WHERE first_name IN ('John', 'Jacob', 'Jingle-heimer')
SELECT * FROM users WHERE first_name NOT IN ('Ken', 'Kenny', 'Griffith')
```

# Range / Between
#between
```SQL
SELECT fields FROM some_table WHERE some_field BETWEEN val1 AND val2;

--Example:
SELECT * FROM users WHERE age BETWEEN 20 AND 25;
```


# Like 
#fuzzy-finding #fuzzy #search #like #wild-card #wildcard
```SQL
SELECT fields FROM some_table WHERE some_field LIKE '%...|...%|...%...';
SELECT fields FROM some_table WHERE some_field LIKE '_...|..._|..._...';
-- the string argument contains a percentage sign % to denote a series of wildcard characters
-- the string argument can contain an understcore sign _ to denote a single wildcard characters

--Example
SELECT * FROM users WHERE name LIKE 'Dav%'; -- Would search for anything starting with 'Dav'
```