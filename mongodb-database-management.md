# Creating and managing databases and collections

Document: A document is a basic unit of storing data into the database. A single record of a collection is also known as a document. Basically, It is a structure that compromises key & value pairs which is similar to the JSON objects. Documents have a great ability to store complex data. For example:

```
const user = {
    firstname:"rk",
    lastname:"patel",
    age:22
    }
```

here firstname , lastname , age is fields and their values are rk , patel , 22.

- #### Database:
  - The MongoDB database is a container for collections and it can store one or more collections. It is not necessary to create a database before you work on it. The show dbs command gives the list of all the databases.

> show dbs command gives us all the databases list

- #### Creating a Database:

  - In MongoDB, we can create a database using the use command.: use users

- #### How to view all the existing database?
  - In MongoDB, we can view all the existing database using the following command:

```
 show dbs
```

- #### Creating a Collection:

      - In MongoDB, a new collection is created when we add one or more documents to it. We can insert documents in the collection using the following methods:

- #### Inserting only one document in the collection

```
db.myNewCollection1.insertOne(
    {
        name:"rk"
         }
          );
```

Here, created a collection named as myNewCollection1 by inserting a document that contains a name field with its value in it using insertOne() method.

- #### Inserting many documents in the collection:

```
db.myNewCollection2.insertMany(
    [
        {
            name:"rk",
             country:"India"
             },
                                {
                                    name:"vk",
                                     age:20
                                     }
                                     ]
                                     );

Here,  created a collection named as myNewCollection2 by inserting two documents using insertMany() method.



- #### How to view all the existing collections in the database?
    - In MongoDB, we can view all the existing collection in the database using the following command:

```

show collections

```

```
