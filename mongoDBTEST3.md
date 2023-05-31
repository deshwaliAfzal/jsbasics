### Create a collection named "books" in MongoDB.

```
db.createCollection("Books");
```

### Insert a document into the "books" collection with the following details:

```
db.Books.insertMany([
  {
    "tital" : "The Great Gatsby",
    "Author" : "F. Scott Fitzgerald",
    "Year" : 1995
  },
  {
    "Title" : "To Kill a Mockingbird",
    "Author" : "Harper Lee",
    "Year" : 1960
  }
])
```

### Write a query to find all documents in the "books" collection.

```
db.Books.find({});
```

### Write a query to find documents in the "books" collection where the author is "F. Scott Fitzgerald".

```
db.Books.find({author : { $eq : "F. Scott Fitzgerald"}});
```

### Write a query to find documents in the "books" collection where the year is greater than 1950.

 ```
db.Books.find({ Year: { $gt: 1950 } });
 ```

### Write an update query to change the author of the document with the title "To Kill a Mockingbird" to "Harper Lee (edited)".

 ```


 ```

### Write an update query to add a new field "genre" with the value "Fiction" to all documents in the "books" collection.

```
db.Books.updateMany({},{ $set: { genre: "Fiction" }});
```

### Write a query to find documents in the "books" collection where the genre is "Fiction".

``
db.Books.find({genre : { $eq : "Fiction" }});

```

### Write a query to find documents in the "books" collection where the title starts with the letter "T".

```
db.Books.find({},{ title: /^T/ })

```

### Write an update query to increment the year by 1 for all documents in the "books" collection.

```
db.Books.updateMany({}, { $inc: { Year: 1 } })

```

### Write a query to find documents in the "books" collection where the year is between 1950 and 1970.

 ```
db.Books.find({Year : { $gt : 1950 , $lt : 1970}});

 ```

### Write a query to find documents in the "books" collection where the author's name contains the letter "a".

 ```
db.Books.find({},{ author: /a/ });

 ```

### Write an update query to remove the "genre" field from all documents in the "books" collection.

 ```
db.Books.updateMany({}, { $unset: { "genre": " " } })

 ```

### Write a query to find documents in the "books" collection where the author's name ends with the letter "y".

```
db.Books.find({},{ author: /y$/ });

```

### Write an update query to change the title of the document with the author "Harper Lee" to "Go Set a Watchman".

```


```

### Write a query to find documents in the "books" collection where the title contains the word "Great".

```
db.Books.find({},{ title: /Great/ });

```

### Write a query to find documents in the "books" collection where the title is an exact match for "The Great Gatsby".

```
db.Books.find({},{ title: /The Great Gatsby/ });

```

### Write an update query to add an array field named "categories" with the values ["Classic", "Fiction"] to all documents in the "books" collection.

```
db.Books.updateMany({}, { $set: { "categories": ["Classic", "Fiction"] } });

```

### Write a query to find documents in the "books" collection where the "categories" field contains the value "Fiction".

```
db.Books.find({},{ categories: {} "Fiction" })


```

### Write a query to find documents in the "books" collection where the title contains the word "The" in a case-insensitive manner.

```
db.Books.find({ title: /The/ })

```

### Write a query to find documents in the "books" collection where the author's name starts with the letter "J".

```
db.Books.find({ Author: /^J/ });

```

### Write an update query to increment the "year" field by 5 for all documents in the "books" collection.

```
db.Books.updateMany( {}, { $inc :{Year:5 }})

```


### Write a query to find documents in the "books" collection where the title is not equal to "Moby Dick".

```
db.Books.find({ title: { $ne: "Moby Dick" } });


```

### Write a query to find documents in the "books" collection where the author's name is either "J.K. Rowling" or "George R.R. Martin".

```
db.Books.find({$or:[{Author:"J.K.Rowling"}, {Author: "George R.R. Martin"}]})


```
