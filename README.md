# MongoDB $inc operator error with string argument
This example demonstrates an incorrect usage of the `$inc` operator in MongoDB when updating a document. Using a string value instead of a numeric value will result in unexpected results or errors.

## Bug
The following code attempts to increment the `count` field by 1 but uses the string '1' instead of the number 1:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: '1' } });
```
## Solution
The correct way to use `$inc` is to provide a numeric value:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```