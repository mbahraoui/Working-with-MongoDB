# MongoDB Operations 

This README provides a guide to the MongoDB operations you can perform on the "books" collection in the "bookstore" database.

## Adding New Documents

### Insert Many Documents

```js
use bookstore
db.createCollection('books')
show collections

db.books.insertMany([
  {
    "title": "The Great Adventure",
    "author": "Jane Smith",
    "publishedYear": 2020,
    "genre": "Adventure"
  },
  {
    "title": "Mystery Mansion",
    "author": "John Doe",
    "publishedYear": 2018,
    "genre": "Mystery"
  }
]);
```

### Insert One Document

```js
db.books.insertOne({
  "title": "The Great Adventure",
  "author": "Jane Smith",
  "publishedYear": 2020,
  "genre": "Adventure"
});
```

## Finding Documents

### Find All Documents

```js
db.books.find();
```

### Find by Author
```js
db.books.find({ author: 'Jane Smith' });
```

### Find by Author and Published Year

```js
db.books.find({ author: 'Jane Smith', publishedYear: 2020 });
```

### Find Specific Fields

```js
db.books.find({ author: 'Jane Smith' }, { title: 1, _id: 0 });
``` 

## Sorting & Limiting Data

### Count Documents

```js
db.books.find().count();
```

### Limit Results

```js
db.books.find().limit(3);
```

### Sort Results

```js
db.books.find().sort({ title: 1 });
```

### Sort and Project

```js
db.books.find({}, { title: 1, _id: 0 }).sort({ title: 1 });
```

## Complex Queries

### OR Condition

```js
db.books.find({
  $or: [{ pages: { $lt: 300 } }, { pages: { $gt: 400 } }]
});
```

### IN Condition

```js
db.books.find({ rating: { $in: [7, 8, 9] } });
```

### NOT IN Condition

```js
db.books.find({ rating: { $nin: [7, 8, 9] } });
```

## Querying Arrays

### Array Contains

```js
db.books.find({ genres: 'magic' });
```

### Exact Array Match

```js
db.books.find({ genres: ['magic'] });
```

### All Elements in Array

```js
db.books.find({ genres: { $all: ['magic', 'fantasy'] } });
```

## Deleting Documents

### Delete One Document

```js
db.books.deleteOne({ _id: ObjectId("64dd1575d436a54b84415cbb") });
```

### Delete Many Documents

```js
db.books.deleteMany({ pages: { $gt: 500 } });
```

## Updating Documents

### Update One Document

```js
db.books.updateOne(
  { _id: ObjectId("64dd163bd436a54b84415cbc") },
  { $set: { rating: 8, pages: 360 } }
);
```

### Update Many Documents

```js
db.books.updateMany(
  { author: "Terry Prachett" },
  { $set: { author: "Terry Prachet" } }
);
```
### Increment Fields

```js
db.books.updateMany({}, { $inc: { pages: 2 } });
```

### Decrement Fields

```js
db.books.updateMany({}, { $inc: { pages: -2 } });
```

### Update Array Elements

```js
db.books.updateOne(
  { _id: ObjectId("64dd163bd436a54b84415cbc") },
  { $pull: { genres: 'Mystery' } }
);
```

### Add to Array

```js
db.books.updateOne(
  { _id: ObjectId("64dd163bd436a54b84415cbc") },
  { $push: { genres: 'Fantasy' } }
);
```

### Add Multiple to Array

```js
db.books.updateOne(
  { _id: ObjectId("64dd163bd436a54b84415cbc") },
  { $push: { genres: { $each: ['test1', 'test2'] } } }
);
```