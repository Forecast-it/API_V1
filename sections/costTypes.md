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
|initialInternalCost | Decimal|
|initialExternalCost | Decimal|

###Sample JSON Response
```json
[
    {
        "url": "https://api.forecast.it/api/v1/project/17/costTypes/76",
        "id": 76,
        "name": "Blended Rate",
        "description": "This is the default blended rate for all project groups.",
        "internalCost": 110.00,
        "externalCost": 800.00,
        "initialInternalCost": 1242,
        "initialExternalCost": 1206
    },
    {
        "url": "https://api.forecast.it/api/v1/project/17/costTypes/77",
        "id": 77,
        "name": "Developer",
        "description": "Example of a developer role.",
        "internalCost": 110.00,
        "externalCost": 800.00,
        "initialInternalCost": 110,
        "initialExternalCost": 0
    }, ...
]
```

##Get Project Phase

* `GET /projects/{projectId}/costTypes/{phaseId}` Returns one project phase.

Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the cost type|
|id | Integer|
|name | String, Name of the cost type|
|description | String|
|internalCost | Decimal, The internal cost|
|externalCost | Decimal, The external cost|
|initialInternalCost | Decimal|
|initialExternalCost | Decimal|

###Sample JSON Response
```json
{
    "url": "https://api.forecast.it/api/v1/project/17/costTypes/76",
    "id": 76,
    "name": "Blended Rate",
    "description": "This is the default blended rate for all project groups.",
    "internalCost": 110.00,
    "externalCost": 800.00,
    "initialInternalCost": 1242,
    "initialExternalCost": 1206
}
```