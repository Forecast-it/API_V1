#Business Units

##Get Business Units

* `GET /businessUnits` Returns all business units.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the business unit|
|id | Integer|
|name | String|

###Sample JSON Response
```javascript
[
    {
        "url": "https://api.forecast.it/api/v1/businessUnits/1",
        "id": 1,
        "name": "Business Unit 1"
    },
    {
        "url": "https://api.forecast.it/api/v1/businessUnits/2",
        "id": 2,
        "name": "Business Unit 2"
    }, ...
]
```

##Get Business Unit

* `GET /businessUnits/{businessUnitId}` Returns a specific business unit.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the business unit|
|id | Integer|
|name | String|
|projectTypes | A List of the project types usable with this business unit. (See GET projectType for JSON)|

###Sample JSON Response
```javascript
{
    "url":"https://api.forecast.it/api/v1/businessUnits/1",
    "id":1,
    "name":"Business Unit 1",
    "projectTypes":{...}
}
```

##Create Business Unit

* `POST /businessUnits` Creates a new business unit.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String (Required)|

###Sample JSON Request
POST https://api.forecast.it/api/v1/businessUnits

```javascript
{
    "name":"New Business Unit"
}
```

##Update Business Unit

* `PUT /businessUnits/{businessUnitId}` Updates a business unit.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/businessUnits/1

```javascript
{
    "name":"New Name"
}
```

##Delete Business Unit

* `DELETE /businessUnits/{businessUnitId}` Deletes a business unit.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/businessUnits/1
