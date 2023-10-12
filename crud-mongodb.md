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

```json
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
  name: 'John Doe',
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