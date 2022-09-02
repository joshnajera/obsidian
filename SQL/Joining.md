#join #inner-join
# Inner Join
Joins tables getting matching rows only. 
This means it will drop all entries where there is no foreign key matching on one table matching to the id of another table.
Multiple inner joins can be used in conjunction
![[Pasted image 20220902075839.png]]

```SQL
SELECT field FROM some_table INNER JOIN other_table ON foreign_key = id_key

--Example:
SELECT * FROM posts INNER JOIN users ON users.id = posts.user_id
```


#left-join #right-join 
# Left Join & Right Join
Each of these keeps non-matching rows from the respective sides they represent. This is to say, left join keeps all rows from the left table even if they are missing a partner entry in the right table. Vis-versa applies for right join.
![[Pasted image 20220902081105.png]]
```SQL
SELECT field FROM left_table LEFT|RIGHT JOIN right_table ON foreign_key = id_key
```




# Cross Join

# ___ Join
