# About the structure
- Comprised of databases
- Databases comprised of tables
- Tables comprised of columns (fields), and rows (entries)
- "Relational" via keys, and joining
- 

# Root functions
## Create a User
###### For SQL Server
```SQL
CREATE USER 'USERNAME_HERE' IDENTIFIED BY 'SOME_PASSWORD';
```

## Create Database / Schema
```sql
CREATE DATABASE my_database;

SHOW DATABASES; -- See all databases

USE my_database; -- Select the table for use
```

## Create Table
```sql
CREATE TABLE some_table(id INT AUTO_INCREMENT, [...field_name field_type [attributes][DEFAULT default_value]], PRIMARY KEY(id));

-- Example: 
CREATE TABLE users(id INT AUTO_INCREMENT, first_name VARCHAR(50), last_name VARCHAR(50), email VARCHAR(75), password VARCHAR(256), location VARCHAR(100), department VARCHAR(50), is_admin TINYINT(1), register_date DATETIME, PRIMARY KEY(id));
```

## Create Entry
#insert
```SQL
INSERT INTO table_name(...field_names...) values (...field_values...)

--Example:
INSERT INTO users(first_name,last_name,email,password,location,department, is_admin, register_date) values ("Jane", "Doe", "jane@gmail.com", "54321", "California", "development", 1, now());
```

## Update
[[Updating Tables and Entries]]

## Deletion 💥
#delete #drop
```SQL
DROP TABLE table_name;
DROP DATABASE db_name;
DROP TRIGGER trigger_name;

DELETE FROM table_name WHERE filter_clause
```


#attributes #constraints
# Key Attributes
PRIMARY -- Marks designated key as primary key , used to uniquely identify
FOREIGN -- Marks designated key as foreign key, used to create [[Relationships]]
UNIQUE -- cannot have repeat
NOT NULL -- Cannot be null
DEFAULT -- Allows you to set default value
AUTO_INCREMENT -- Automatically increments per new entry
ON DELETE SET NULL-- Allows you to update associated value to null when reference is deleted
```SQL
CREATE TABLE employee(
id INT AUTO_INCREMENT,
first_name VARCHAR(50),
company_car INT,
FOREIGN KEY(company_car) REFERENCES company_cars(id) ON DELETE SET NULL 
)
-- When company_cars entry with id, this foreign key gets set to null.
```
ON DELETE CASCADE -- Allows you to **delete** entire row(s) where the associated key was referenced, instead of just setting it to null. 
 