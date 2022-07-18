# Nest + MySQL + TypeScript example integration

1. Install dependencies via `npm install`
2. Run via `npm start:dev`
3. Example API is running on http://localhost:3000

Available routes:

```
GET     /author        finds all authors
GET     /author/:id    finds author by id
POST    /author        creates new author
PUT     /author/:id    updates author by id
```

```
GET     /book          finds all books
GET     /book/:id      finds book by id
POST    /book          creates new book
PUT     /book/:id      updates book by id
```


Use the following structure to create an author with books, publisher and tags.

```
{ 
    "name": "a1",
    "email": "e1", 
    "books": [
      { 
         "title": "b1",
         "publisher":{
            "name":"tech",
            "type":"local"
            },
         "tags":[{
                      "name":"action"
                       },
                    {
                     "name":"horror"
                        }
                ] 
         }, 
         {
             "title": "b2",
             "publisher":{
                  "name":"tech",
                  "type":"local"
                  },
             "tags":[{
                      "name":"action"
                       },
                    {
                     "name":"horror"
                        }
                    ] 
         }
   ]
}
```

To create a book use following structure

```
{ 
    "title": "b1",
    "author": {
        "name": "a1", 
        "email": "e1"
        },
    "tags":[{
        "name":"action"
    }],
    "publisher":{
        "name":"tech",
        "type":"local"
    }
}
```


After adding some data through above api calls we can now try to fetch the details from database.

To fetch the list of all authors hit the following
```
Get /api/author
```

For a particular author copy its objectId from the list and hint the following api with ObjectId as a param
```
Get /api/author/:id
e.g /api/author/62d53570c770402b7983d314
```

To fetch the list of all books hit the following
```
Get /api/book
```

For a particular book copy its objectId from the list and hint the following api with ObjectId as a param
```
Get /api/author/:id
e.g /api/book/62d53570c770402b7983d314
```