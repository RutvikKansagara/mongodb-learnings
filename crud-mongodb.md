## CRUD Operations


here C -> CREATE , R -> READ , U -> UPDATE , D -> DELETE


### CREATE Operations:


| Method                    | Description                                               |
| -----------               | -----------                                               |
| db.collection.insertOne()	| It is used to insert a single document in the collection. |
| db.collection.insertMany()| It is used to insert multiple documents in the collection.|
| db.createCollection()     | It is used to create an empty collection.                 |



#### Inserting sinlge document using db.collection.insertOne():

```
db.students.insertOne({
  name: "John Doe",
  age: 21,
  branch: "Computer Science",
  course: "Computer Science",
  mode: "online",  
  paid: true,      
  amount: 500.00
});
```

#### Inserting multiple document using db.collection.insertMany():

```
db.students.insertMany([
  {
    name: "John Doe",
    age: 21,
    branch: "Computer Science",
    course: "Computer Science",
    mode: "online",  // or "offline"
    paid: true,      // or false
    amount: 500.00
  },
  {
    name: "Jane Smith",
    age: 22,
    branch: "Electrical Engineering",
    course: "Electrical Engineering",
    mode: "offline",
    paid: false,
    amount: 0.00
  },
]);
```
#### Creating collection with db.createCollection():

```
db.createCollection("users");

```

### READ Operations:

|Method	                | Description                                          |
|------                 | -----------                                          |
|db.collection.find()	| It is used to retrieve documents from the collection.|


to retrieving all students details we can use db.collection.find():

```
db.students.find({})

```

##### output:

```
{
  _id: ObjectId("65279dff2ed013ed0432426a"),
  name: 'John Doe',
  age: 21,
  branch: 'Computer Science',
  course: 'Computer Science',
  mode: 'online',
  paid: true,
  amount: 500
}
{
  _id: ObjectId("6527a4c72ed013ed0432426b"),
  name: 'Jane Doe',
  age: 21,
  branch: 'Computer Science',
  course: 'Computer Science',
  mode: 'online',
  paid: true,
  amount: 500
}
{
  _id: ObjectId("6527a4c72ed013ed0432426c"),
  name: 'Jane Smith',
  age: 22,
  branch: 'Electrical Engineering',
  course: 'Electrical Engineering',
  mode: 'offline',
  paid: false,
  amount: 0
}
```

### UPDATE Operations:

| Method                    | Description                                               |
| -----------               | -----------                                               |
| db.collection.updateOne()	| It is used to update a single document in                 |
|                           |   the collection that satisfy the given criteria.           |
| db.collection.updateMany()| It is used to update multiple documents in the            |
|                           |    collection that satisfy the given criteria.             |
| db.collection.replaceOne()| It is used to replace single document in the              |
|                           |   collection that satisfy the given criteria.              |

#### Updating sinlge document using db.collection.updateOne():

```
db.students.updateOne(
  { name: "John Doe" },
  {
    $set: {
      age: 22,
      mode: "offline",
      amount: 600.00
    }
  }
);
```

#### Updating multiple document using db.collection.updateMany():

```
db.students.updateMany(
  { branch: "Computer Science" },
  {
    $set: {
      mode: "online",
      amount: 550.00
    }
  }
);
```


#### Updating sinlge document using db.collection.replaceOne():

```
db.students.replaceOne(
  { name: "John Doe" },
  {
    name: "John Doe",
    age: 23,
    branch: "Computer Science",
    course: "Advanced Computer Science",
    mode: "online",
    paid: true,
    amount: 650.00
  }
);
```


### DELETE Operations:

| Method                    | Description                                               |
| -----------               | -----------                                               |
|db.collection.deleteOne()	| It is used to delete a single document from the|
|                            |  collection that satisfy the given criteria. |
|db.collection.deleteMany() | It is used to delete multiple documents from the 
|                            | collection that satisfy the given criteria.|


#### deleting a sinlge document using db.collection.deleteOne():


```
db.students.deleteOne(
  { name: "John Doe" }
);
```

#### deleting a multiple document using db.collection.deleteMany():


```
db.students.deleteMany(
  { branch: "Computer Science" }
);
```