Replaces the value with { $operator : valueToCompare [, $operator: valueToCompare2]}
Operators in MongoDB have a $ prefix

1. **Equality Operators:**
    - `$eq`: Matches values that are equal to a specified value.
    - `$ne`: Matches all values that are not equal to a specified value.
	
2. **Comparison Operators:**
    - `$gt`: Matches values that are greater than a specified value.
    - `$gte`: Matches values that are greater than or equal to a specified value.
    - `$lt`: Matches values that are less than a specified value.
    - `$lte`: Matches values that are less than or equal to a specified value.
	
3. **Array Operators:**
    - `$in`: Matches any of the values specified in an array.
    - `$nin`: Matches none of the values specified in an array.
    - `$all`: Matches arrays that contain all elements specified in an array.
	
4. **Logical Operators:**
    - `$and`: Joins query clauses with a logical AND and returns documents that match all the conditions.
    - `$or`: Joins query clauses with a logical OR and returns documents that match at least one of the conditions.
    - `$not`: Inverts the effect of a query expression and returns documents that do not match the query expression.
    - `$nor`: Joins query clauses with a logical NOR and returns documents that fail to match all the conditions.
	
5. **Element Operators:**
    - `$exists`: Matches documents that have the specified field.
    - `$type`: Matches documents where the value of a field is of the specified type.
	
6. **Evaluation Operators:**
    - `$expr`: Allows the use of aggregation expressions within the query language.
    - `$jsonSchema`: Validates documents against the given JSON schema.