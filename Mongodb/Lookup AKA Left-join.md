- Must be used in an aggregate function
```javascript
db.leftSideCollectionName.aggregate([{
  {
    $match: {
		// some criteries -- omit for 'all'
		exampleName: "Joy"
    }
  },
  $lookup: {
    from: <rightSideCollection>,
    localField: <field in the leftSideCollection>,
    foreignField: <field in the "from" rightSideCollection>,
    as: <output array name>
  }
}
]);
```

