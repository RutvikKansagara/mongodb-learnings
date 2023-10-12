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

