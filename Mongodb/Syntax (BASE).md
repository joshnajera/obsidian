Listing database
`show dbs`

Switching databases:
`use someDatabaseName`



# Collections

Create
`db.createCollection("collectionName")`

Delete
`db.collectionName.drop()`

Show
`show collections`

Mark field as 'unique'
`db.users.createIndex({ email: 1 }, { unique: true });`
* 1 for ascending index, -1 for descending index

# Inserting

Insert One
`db.collectionName.insertOne({name:"Josh", last_name:"najera"})` 

We can also insertMany
```mongodb
db.users.insertMany([
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 35 },
  { name: 'Charlie', age: 25 }
]);
```

# Updating

`db.CollectionName.updateOne({someQuery:"value"}, {someReplacement:"value"})`
woops we can't do this, we need to do something extra:
`db.CollectionName.updateOne({someQuery:"value"}, {$set: {someReplacement:"value"}})`

Update Many 
`db.collecionName.updateMany({name:"Josh"}, {$unset: {name:""}})`

# Delete

Delete Database
`db.dropDatabase()`

Delete Entries
`db.collectionName.deleteOne({})`
`db.collectionName.deleteMany({})`

# Searching
- Seems to paginate at 20 items
`db.collectionName.find()` Get all?
`db.collectionName.find({name:"Josh"})` For getting all data from objects
`db.collectionName.find({name:"Josh"}, {address: true, hair_color: true, faborite_food: true})` Filtering for specific fields in return 
`db.collectionName.find({name:"Josh"}).limit(20).skip(20)` Set custom pagination
`db.collectionName.find({name:"josh"}).sort({last_name: 1})` Sort last_name ascending

# Complex Queries
## $in
`db.collectionName.find( {name: {$in: ['Josh', 'Jim, 'Joe'] } } )`