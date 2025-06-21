# Intro to MongoDB

By [Avionte Williams]

(Customize these headings!)

## Introduction

* Why should someone learn the language/framework that you are learning?
* What is it used for? How popular is it? Who is it for (developers or users)?
* Incorporate real-world analogies when appropriate and useful.

## Core syntax/features. 

* For programming languages: data types, variables, code blocks, functions, conditionals, arrays and objects, and iteration. Include code snippets with explanations.

* For frameworks (including React and Express): setup/installation/configurations, core concepts, key methods or approaches. Include code snippets with explanations.

## Compare and Contrast

* For programming languages: What are the key differences between the new language and JavaScript? What are the commonalities?
* For frameworks (including React and Express): What are the alternatives to this framework? Can you compare this framework to anything we've learned in the Core Curriculum? What are the tradeoffs when choosing this framework compared to the alternatives?

## Conclusion & Tips for learning this language/framework.

* Wrap things up
* Provide links to resources that you used to help you learn the language.

# Intro to MongoDB

## Intro

MongoDB was created in 2009 by its founder and developer Eliot Horowitz. The name MongoDB is derived from the word "humongous," which means enormous. MongoDB is a database that uses a non-relational document model. This makes it a NoSQL database, which is different from the usual conventional relational databases like MySQL, Microsoft SQL, etc.

## What is MongoDB

First, let's break down what MongoDB is: a database. A database is an organized collection of data on a computer. They are designed for storing and retrieving data effectively. Databases are structured in ways that allow data to be easily managed, accessed, and analyzed. Now that you know what databases are, let's understand the different types of databases. the are many types of individual databases, but they fall into these two broad types: relational and non-relational.

### relational picture

A relational database is a database that has very bare-bones columns and rows that store data, connecting them by using foreign keys. Some of the most popular relational databases: MySQL, Microsoft SQL, Oracle, etc.

### non-relational picture

A non-relational database, alternatively known as NoSQL databases, is a database that doesn't use the relational model. Instead of structuring their data in rows and columns, they use a document, key-value stores, column-oriented databases, and graphs.

MongoDB uses a document-oriented database. Which means it stores data in a document form similar to JSON. In the MongoDB database, the data is stored in a collection, which has documents inside, and then fields.

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

---

## MongoDB syntax

Mongo supports most JSON data types, plus more.

- **String** `"name": "Avionte"`
- **Number** `"age": 25"`
- **Boolean** `"isActive": true"`
- **Date** `"dob": new Date()"`
- **Array** `"skills": ["JS", "Mongo"]"`
- **Object** `"address": { "city": "NY" }"`
- **Null** `"dob": null"`
- **ObjectId** `"_id": ObjectId("...")`

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

---

## Navigating Queries

### MongoDB Methods
