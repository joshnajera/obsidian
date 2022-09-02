# Triggers
Allows you to do some sort of processing when something happens.

```SQL
DELIMITER $$ -- Change delimiter
CREATE
	TRIGGER trigger_name BEFORE|AFTER INSERT|DELETE|UPDATE
	ON table_name
	FOR EACH ROW BEGIN
		--ACTION
	END $$
DELIMITER ; -- Reset delimiter


DROP TRIGGER trigger_name;


-- Example:
DELIMITER $$ -- Change delimiter
CREATE
	TRIGGER my_trigger BEFORE INSERT
	ON employee
	FOR EACH ROW BEGIN
		INSERT INTO company_log VALUES('Added a new employee');
	END $$
DELIMITER ; -- Reset delimiter
```


Normally, sql delimiter is the semicolon ;  however, since this is being used inside the CREATE TRIGGER function, which needs a delimiter, we must create an outer delimiter to differentiate between the two properly.




#new #old
# New & Old keywords
## NEW
Allows you to get NEW data values when in a trigger.
Blank if using BEFORE INSERT?

## OLD
Allows you to get the OLD data values when in a trigger.
Blank if using AFTER INSERT?