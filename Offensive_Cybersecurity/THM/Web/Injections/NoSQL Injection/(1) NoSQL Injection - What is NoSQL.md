#NoSQL #WebInjection 

# SQL VS NoSQL

- MySQL VS MongoDB (and many others...)
- The major exception between both is that the information isn't stored on tables but rather **in documents**.
- It is possible to *group multiple documents* with a similar function together in higher hierarchy structures called **collections**, then grouped in **databases**.

- EX: `{"_id" : ObjectId("5f077332de2cdf808d26cd74"), "username" : "lphillips", "first_name" : "Logan", "last_name" : "Phillips", "age" : "65", "email" : "lphillips@example.com" }`

 ---
# Querying the Database

- *Return only the documents where the last_name is "Sandler" *
- `['last_name' => 'Sandler']`

- *Return only the documents where the gender is male, and the last_name is Phillips*
- `['gender' => 'male', 'last_name' => 'Phillips']`

- *Return documents where the age is less than 50*
- `['age' => ['$lt'=>'50']]`

**We are using the *$lt* operator in a nested array. Operators allow for more complex filters by nesting conditions. : [MongoDB Operator Reference](https://docs.mongodb.com/manual/reference/operator/query/)

## Operators 

| Name                                                                                              | Description                                                         |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [`$eq`](https://www.mongodb.com/docs/manual/reference/operator/query/eq/#mongodb-query-op.-eq)    | Matches values that are equal to a specified value.                 |
| [`$gt`](https://www.mongodb.com/docs/manual/reference/operator/query/gt/#mongodb-query-op.-gt)    | Matches values that are greater than a specified value.             |
| [`$gte`](https://www.mongodb.com/docs/manual/reference/operator/query/gte/#mongodb-query-op.-gte) | Matches values that are greater than or equal to a specified value. |
| [`$in`](https://www.mongodb.com/docs/manual/reference/operator/query/in/#mongodb-query-op.-in)    | Matches any of the values specified in an array.                    |
| [`$lt`](https://www.mongodb.com/docs/manual/reference/operator/query/lt/#mongodb-query-op.-lt)    | Matches values that are less than a specified value.                |
| [`$lte`](https://www.mongodb.com/docs/manual/reference/operator/query/lte/#mongodb-query-op.-lte) | Matches values that are less than or equal to a specified value.    |
| [`$ne`](https://www.mongodb.com/docs/manual/reference/operator/query/ne/#mongodb-query-op.-ne)    | Matches all values that are not equal to a specified value.         |
| [`$nin`](https://www.mongodb.com/docs/manual/reference/operator/query/nin/#mongodb-query-op.-nin) | Matches none of the values specified in an array.                   |
| ...                                                                                               | ...                                                                 |

---

[[(2) NoSQL Injection - Detection & Exploitation|Continue to NoSQL Detection & Exploitation]]