# API

## Summary

## Best Practices

#### Use JSON
REST allows using different output formats, like plain text, JSON, CSV, XML, RSS.

#### Use Nouns instead of Verbs
Correct way
```
GET /books/123
DELETE /books/123
POST /books
PUT /books/123
PATCH /books/123
```

vs

Incorrect way
```
GET /addBook123 (by the way, GET should be only used to READ data and never to change its state in any way)
GET /DeleteBooks/123
POST /DeleteAllBooks
POST /books/123/delete
```

#### Name the collections using Plural Nouns
For the collections in REST API development use plural nouns.

```
GET  /cars/123
POST /cars
GET /cars
```

vs

```
GET /car/123
POST /car
GET /car
```

#### Use resource nesting to show relations or hierarchy

```
/users <- user’s list
/users/123 <- specific user
/users/123/orders <- orders list that belongs to a specific user
/users/123/orders/0001 <- specific order of a specific user
```

## Useful links
