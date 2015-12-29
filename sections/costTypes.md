#Cost Types

##Get Cost Types

* `GET /projects/{projectId}/costTypes` Returns all cost types for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the cost type|
|id | Integer|
|name | String, Name of the cost type|
|description | String|
|internalCost | Decimal, The internal cost|
|externalCost | Decimal, The external cost|

###Sample JSON Response
```javascript
[
    {
        "url": "https://api.forecast.it/api/v1/projects/17/costTypes/76",
        "id": 76,
        "name": "Blended Rate",
        "description": "This is the default blended rate for all project roles.",
        "internalCost": 110.5,
        "externalCost": 800
    },
    {
        "url": "https://api.forecast.it/api/v1/projects/17/costTypes/77",
        "id": 77,
        "name": "Developer",
        "description": "Example of a developer role.",
        "internalCost": 110.5,
        "externalCost": 800
    }, ...
]
```

##Get Project Phase

* `GET /projects/{projectId}/costTypes/{costTypeId}` Returns one project phase.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the cost type|
|id | Integer|
|name | String, Name of the cost type|
|description | String|
|internalCost | Decimal, The internal cost|
|externalCost | Decimal, The external cost|

###Sample JSON Response
```javascript
{
    "url": "https://api.forecast.it/api/v1/projects/17/costTypes/76",
    "id": 76,
    "name": "Blended Rate",
    "description": "This is the default blended rate for all project roles.",
    "internalCost": 110.5,
    "externalCost": 800
}
```