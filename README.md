# Intro to MongoDB

By [Avionte Williams]

## Intro
MongoDB was created in 2009 by its founder and developer Eliot Horowitz. The name MongoDB is derived from the word "humongous," which means enormous. MongoDB is a database that uses a non-relational document model. This makes it a NoSQL database, which is different from the usual conventional relational databases like MySQL, Microsoft SQL, etc.

## What is MongoDB
First, let's break down what MongoDB is: a database. A database is an organized collection of data on a computer. They are designed for storing and retrieving data effectively. Databases are structured in ways that allow data to be easily managed, accessed, and analyzed. Now that you know what databases are, let's understand the different types of databases. the are many types of individual databases, but they fall into these two broad types: relational and non-relational.  

### relational picture
A relational database is a database that has very bare-bones columns and rows that store data, connecting them by using foreign keys. Some of the most popular relational databases: MySQL, Microsoft SQL, Oracle, etc.

### non-relational picture
A non-relational database, alternatively known as NoSQL databases, is a database that doesn't use the relational model. Instead of structuring their data in rows and columns, they use a document, key-value stores, column-oriented databases, and graphs.  

MongoDB uses a document-oriented database. This means it stores data in a document format similar to JSON. In the MongoDB database, the data is stored in a collection, which has documents inside, and then fields.  
> databases > collections > documents > fields.

```
[
  {
    "_id": ObjectId("60c72b2f9f1b2563f4d3f123"),
    "name": "Avionte",
    "dob": null,
    "age": 25
  },
  {
    "_id": ObjectId("60c72b2f9f1b2563f4d3f124"),
    "name": "Ben",
    "dob": null,
    "age": 30
  }
]
```

**Database**: The outermost container (not shown in the snippet) that stores collections.  
**Collection**: A group of related documents - here, the snippet shows one collection containing multiple user records.  
**Documents**: Each object enclosed in `{}` is a document. In this case, there are two documents, each representing a person.  
**Fields**: Inside each document are key-value pairs like `_id`, `name`, `dob`, and `age`. These are the fields that hold actual data.

## Why MongoDB
MongoDB is used in apps like eBay, Electronic Arts, LinkedIn, Forbes, Uber, and the list goes on. The reason for these companies' choice is MongoDB's flexibility, scalability, and performance. The flexibility comes from the schema-less design. It allows easy storage for the various data types that will be explained later. Unlike relational databases, which have a strict, enforced schema. The flexible schema, along with the BSON (Binary JSON) format, allows great flexibility. Another reason is the replicati...

## How Mongo

### MongoDB syntax
Mongo supports most JSON data types, plus more.  

- String `"name": "Avionte"`  
- Number `"age": 25"`  
- Boolean `"isActive": true"`  
- Date `"dob": new Date()`  
- Array `"skills": ["JS", "Mongo"]"`  
- Object `"address": { "city": "NY" }"`  
- Null `"dob": null"`  
- ObjectId `"_id": ObjectId("...")`

```
{
  name: "Avionte",
  age: 25,
  isActive: true,
  dob: new Date("1999-05-15"),
  skills: ["JavaScript", "MongoDB"],
  address: { city: "Brooklyn", state: "NY" },
  _id: ObjectId("60c72b2f9f1b2563f4d3f123")
}
```

## Navigating Queries
Databases have data, and they use methods to retrieve, add, and delete data. here are the methods that MongoDB used. Heres is the methods used for MongoDB crud. (create, read, update and delete)  

### MongoDB Methods  

- `.find()` - used to select data from the collections  
```
db.users.find({ age: { $gt: 18 } });
```  
- `.sort()` - used to sort data  
```
db.users.find().sort({ age: 1 });
```  
- `.limit()` - used to limit the query to the given integer  
```
db.users.find().limit(5);
```  
- `.findOne()` - returns the document in a collection  
```
db.users.findOne({ name: "Avionte" });
```  
- `.countDocuments()` - counts the number of documents in the collection  
```
db.users.countDocuments({ age: { $gte: 21 } });
```  
- `.updateOne()` - Updates the first document that matches the query.  
```
db.users.updateOne(
  { name: "Avionte" },
  { $set: { age: 26 } }
);
```  
- `.updateMany()` - Updates all documents that match the query.  
```
db.users.updateMany(
  { isActive: false },
  { $set: { isActive: true } }
);
```  
- `.deleteOne()` - Deletes the first document that matches the query.  
```
db.users.deleteOne({ name: "Ben" });
```  
- `.deleteMany()` - Deletes all documents that match the query.  
```
db.users.deleteMany({ age: { $lt: 18 } });
```  

With these database being humongous it takes more then just these methods. within these we have operators to help further navigate these queriees. You see a few used in the examples above. Here's a list of some of the main ones:

- `$gt` Greater than `{ age: { $gt: 18 } }`  
- `$lt` Less than `{ age: { $lt: 30 } }`  
- `$gte` Greater than or equal to `{ age: { $gte: 21 } }`  
- `$lte` Less than or equal to `{ age: { $lte: 65 } }`  
- `$eq` Equal to `{ name: { $eq: "Avionte" } }`  
- `$ne` Not equal to `{ name: { $ne: "Ben" } }`  
- `$in` Value is in array `{ age: { $in: [18, 25, 30] } }`  
- `$not` Negates a query condition `{ age: { $not: { $gt: 18 } } }`  
- `$and` Matches all conditions (AND) `{ $and: [ { age: { $gt: 18 } }, { isActive: true } ] }`  
- `$or` Matches any condition (OR) `{ $or: [ { age: 25 }, { name: "Ben" } ] }`


##In Conclusion
MongoDB stands out as a modern database solution built for flexibility, scalability, and high performance. Its document-based structure and schema-less design make it a powerful tool for handling complex and changing data in real-world applications. From startups to large-scale companies like Uber and LinkedIn, MongoDB has proven to be a reliable database for building fast and responsive applications. Whether you're managing simple user data or scaling massive systems, MongoDB provides the tools and methods, like CRUD operations and advanced query operators, to help you work with your data effectively. As you continue learning and building, MongoDB will remain a valuable part of your backend toolkit.
