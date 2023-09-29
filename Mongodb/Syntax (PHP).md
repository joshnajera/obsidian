# Connect
Unsecured Login?
```php
<?php
try {
	$manager = new MongoDB\Driver\Manager("mongodb://localhost:27017");
} catch (MongoDB\Driver\Exception\ConnectionTimeoutException $e) {
    echo "Connection timed out: " . $e->getMessage();
} catch (MongoDB\Driver\Exception\ConnectionException $e) {
    echo "Connection failed: " . $e->getMessage();
} catch (Exception $e) {
    echo "An error occurred: " . $e->getMessage();
}

echo "Connected successfully to MongoDB";
// Close the MongoDB connection
unset($manager);
?>
```
Secured Login?
```php
<?php
$username = 'your_username';
$password = 'your_password';
$database = 'admin'; // Authentication database
$host = 'localhost';
$port = 27017;

$uri = "mongodb://$username:$password@$host:$port/$database";
$manager = new MongoDB\Driver\Manager($uri);

echo "Connected successfully to MongoDB";
?>

```


#  Create
```php
<?php
$bulk = new MongoDB\Driver\BulkWrite;

$document = ['name' => 'John Doe', 'age' => 30, 'email' => 'john@example.com'];
$bulk->insert($document);

$manager->executeBulkWrite('your_db.your_collection', $bulk);
?>
```

# Read

```php
<?php
// Query filter
$filter = ['name' => 'John Doe'];
// Regex for partial match, or regex
$pattern = 'John';  // Partial match pattern
$filter = ['name' => ['$regex' => $pattern]];
// Logical operators in query filter
// Supports: $or, $and, $not, $nor
$filter = [
    '$or' => [
        ['age' => ['$gte' => 30]], // Note the comparison operator
        ['name' => 'John Doe']
    ]
];
// Filter with 'in' a set
$filter = ['status' => ['$in' => ['active', 'pending']]];


// Compile the query, note options come later
$query = new MongoDB\Driver\Query($filter);

// RESULT Options
$options = ['limit' => 10];  // Limit to 10 results
$options = ['skip' => $skip, 'limit' => $perPage]; // Limit and offset by amount
// Retreive specific fields
$options = ['projection' => ['name' => 1, 'age' => 1]];  // Include only 'name' and 'age' fields
// Sorting
$sort = ['age' => 1]; // Sort age ascending (1 for ascending, -1 for descending)
$options = [
    'sort' => $sort
];

$cursor = $manager->executeQuery('your_db.your_collection', $query);
$cursor = $manager->executeQuery('your_db.your_collection', $query, $options);

foreach ($cursor as $document) {
    var_dump($document);
}
?>

```

# Update

```php
<?php
$bulk = new MongoDB\Driver\BulkWrite;

$filter = ['name' => 'John Doe'];
$update = ['$set' => ['age' => 31]];
$bulk->update($filter, $update);

$manager->executeBulkWrite('your_db.your_collection', $bulk);
?>
```
# Delete
```php
<?php
$bulk = new MongoDB\Driver\BulkWrite;

$filter = ['name' => 'John Doe'];
$bulk->delete($filter);

$manager->executeBulkWrite('your_db.your_collection', $bulk);
?>
```