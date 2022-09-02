#aggregate #count
# Count
```SQL
SELECT COUNT(id) FROM some_table;
```

#minimum #min #maximum #max
# Max & Min
```SQL
SELECT MIN(age) FROM users;
SELECT MIN(age) FROM users;
```

#sum #add
# Sum
```SQL
SELECT SUM(cost) FROM invoices;
```

#upper #upper-case #lower #lower-case
# Upper & Lower
```SQL
SELECT UCASE(first_name), LCASE(last_name) FROM users;
```

# Group By
Allows you to chunk entries together 
#grouping #group-by
```SQL
SELECT location, COUNT(location) FROM users GROUP BY location;
```

