# CRUD Opeartions

## Create Operations

#### Create a new database called employee_db

![new db](images/image-2.png)

#### Create a collection called employee_info

![Alt text](images/image-3.png)

#### Insert data into our collection

![Alt text](images/image-5.png)

![Alt text](images/image-7.png)

## Counting Record

![Alt text](images/image-6.png)

#### count distinct values

![Alt text](images/image-8.png)

## Filtering on a single field

![Alt text](images/image-9.png)

## Filtering on multiple fields

![Alt text](images/image-10.png)

## Filtering embedded documents

![Alt text](images/image-11.png)

## Projections

![Alt text](images/image-12.png)

## Update Operations

![Alt text](images/image-13.png)

![Alt text](images/image-14.png)

MongoDB offers multiple operators that can be used in its update operations. In the exercise above, we looked at the `$set` operator. 

|Name|Description|
|---|---|
|`$set`|Sets the value of a field in a document|
|`$unset`|Removes the specified field from a document|
|`$currentDate`|Sets the value of a field to current date, either as a Date or a Timestamp|
|`$inc`|Increments the value of a field by a specified amount|
|`$mul`|Multiplies the value of the field by the specified amount|
|`$min`|Only updates the field if the specified value is less than the existing field value.|
|`$max`|Only updates the field if the specified value is greater than the existing field value.|
|`$setOnInsert`|Sets the value of a field if an update results in an insert of a document. Has no effect on update operations that modify existing documents.|
|`$rename`|Renames a field|

## Delete Operations

![Alt text](images/image-15.png)

![Alt text](images/image-16.png)
