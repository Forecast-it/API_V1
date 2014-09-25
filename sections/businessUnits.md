#Business Units

##Get Business Units

* `GET /businessUnits` Returns all business units.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the customer|
|id | Integer|
|name | String|
|description | String|
|active | Boolean|

###Sample JSON Response
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

##Get Customer

* `GET /customers/{customerId}` Returns a specific customer.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the customer|
|id | Integer|
|name | String|
|description | String|
|active | Boolean|
|projects | A List of the projects from this Customer (See GET project for JSON)|

###Sample JSON Response
```json
{
    "url":"http://api.forecast.it/api/v1/customers/1",
    "id":1,
    "name":"Customer 1",
    "description":"Description of customer",
    "active":true,
    "projects":{...}
}
```

##Create Customer

* `POST /customers` Creates a new customer.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String (Required)|
|description | String (Optional)|

###Sample JSON Request
POST https://api.forecast.it/api/v1/customers

```json
{
    "name":"New Customer",
    "description":"Created via API"
}
```

##Update Customer

* `PUT /customers/{customerId}` Updates a customer.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|
|description | String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/customers/1

```json
{
    "description":"Updated Description"
}
```

##Delete Customer

* `DELETE /customers/{customerId}` Deletes/Disables a customer.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/customers/1
