# Advanced Queries

#### Aggregations

db.collection.aggregate([
  { $match: { /* Filtering criteria */ } },
  { $group: { /* Grouping criteria */ } },
  { $project: { /* Projection criteria */ } },
  // ... Additional stages
]);

### The $group operator

![Alt text](images/image03.png)

Count the number of films by genre:

![Alt text](images/image03-1.png)

Find the average runtime of films released in each year:

![Alt text](images/image03-2.png)

Find the top 5 directors with the most films

![Alt text](images/image03-3.png)