Customers
=========

Get customers
-------------

* `GET /customers` will return all customers.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the customer|
|id | Integer|
|name | String|
|description | String|
|active | Boolean|

```json
[
    {
        "url": "https://api.forecast.it/api/v1/customers/1",
        "id": 1,
        "name": "Customer 1",
        "description": "An active customer",
        "active": true
    },
    {
        "url": "https://api.forecast.it/api/v1/customers/2",
        "id": 2,
        "name": "Customer 2",
        "description": "A disabled customer",
        "active": false
    }, ...
]
```
