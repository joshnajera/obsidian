Setup
#relationships #foreign_key
```SQL
CREATE TABLE posts(
	id INT auto_increment,
	user_id INT,
	title VARCHAR(100),
	body text,
	publish_date DATETIME DEFAULT CURRENT_TIMESTAMP,
	PRIMARY KEY(id),
	FOREIGN KEY(user_id) REFERENCES users(id)
)
```

Define foreign key of posts to be user_id,
this points to the id field of an entry from the users table.

Foreign key -> Reference (unique?) field
