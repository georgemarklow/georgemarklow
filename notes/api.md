# API

## Summary

| Header      | Description                                                                         |
| ----------- | -----------                                                                         |
| GET         | The resource has been fetched and is transmitted in the message body.               |
| HEAD        | The entity headers are in the message body.                                         |
| PUT or POST | The resource describing the result of the action is transmitted in the message body.|
| TRACE       | The message body contains the request message as received by the server.            |

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

#### Filtering, sorting, paging, and field selection

- Filtering - to narrow down the query results by specific parameters, eg. creation date, or country
- Sorting - allows sorting the results ascending or descending by a chosen parameter or parameters, eg. by date
- Paging - uses “limit” in order to narrow down the number of results shown to a specific number

Filtering:
```
GET /users?country=USA
GET /users?creation_date=2019-11-11
GET /users?creation_date=2019-11-11
```
Sorting:
```
GET /users?sort=birthdate_date:asc
GET /users?sort=birthdate_date:desc
```
Paging:
```
GET /users?limit=100
GET /users?offset=2
```
All together:
```
GET /users?country=USA&creation_date=2019-11-11&sort=birthdate_date:desc&limit=100&offset=2
```

#### Versioning

Examples of endpoint URI versioning:

| Example      | Description                                                                         |
| ----------- | -----------                                                                         |
| https://us6.api.mailchimp.com/3.0/         | major + minor version indication               |
| https://api.stripe.com/v1/         | major version indication only               |
| https://developer.github.com/v3/         | major version indication only               |
| https://us6.api.mailchimp.com/3.0/         | date based indication               |

#### API Documentation

Example: https://docs.deribit.com/v1/

#### Use SSL/TLS


#### HTTP Codes

| Code        | Name| Description |
| ----------- | ----------- | ----------- |
| 200         | OK || The request has succeeded. The meaning of the success depends on the HTTP method |
| 201         | Created | The request has succeeded and a new resource has been created as a result. This is typically the response sent after POST requests, or some PUT requests.        |
| 202 | Accepted | The request has been received but not yet acted upon. It is noncommittal, since there is no way in HTTP to later send an asynchronous response indicating the outcome of the request. |
| 204 | No Content | There is no content to send for this request, but the headers may be useful. |
| 400 | Bad Request | The server could not understand the request due to invalid syntax. |
| 401 | Unauthorized | Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response. |
| 403 | Forbidden | The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401, the client's identity is known to the server. |
| 404 | Not Found | The server can not find the requested resource. |
| 405 | Method Not Allowed | The request method is known by the server but has been disabled and cannot be used. For example, an API may forbid DELETE-ing a resource. The two mandatory methods, GET and HEAD, must never be disabled and should not return this error code. |
| 500  | Internal Server Error | The server has encountered a situation it doesn't know how to handle. |
| 501 | Not Implemented | The request method is not supported by the server and cannot be handled. The only methods that servers are required to support (and therefore that must not return this code) are GET and HEAD. |
| 504  | Gateway Timeout | This error response is given when the server is acting as a gateway and cannot get a response in time. |

## Useful links
- [What Every Web Developer Should Know About HTTP](https://www.amazon.co.uk/Every-Developer-Should-OdeToCode-Programming-ebook/dp/B0076Z6VMI)
- [What Every Developer Must Know About HTTPS](https://www.pluralsight.com/courses/https-every-developer-must-know)
