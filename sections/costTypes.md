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
|project | JSON (Project), The project|
|initialInternalCost | Decimal|
|initialExternalCost | Decimal|

###Sample JSON Response
```json
[
    {
	    "url": "https://api.forecast.it/api/v1/projectPhases/10",
	    "id": 10,
	    "phase": "Design",
	    "description": "The design phase.",
	    "weight": 25,
	    "calculatedWeight": 25,
	    "order": 1
    },
	{
	    "url": "https://api.forecast.it/api/v1/projectPhases/11",
	    "id": 11,
	    "phase": "Implementation",
	    "description": "The implementation phase.",
	    "weight": 25,
	    "calculatedWeight": 25,
	    "order": 2
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
|project | JSON (Project), The project|
|initialInternalCost | Decimal|
|initialExternalCost | Decimal|

###Sample JSON Response
```json
{
	"url": "https://api.forecast.it/api/v1/projectPhases/10",
	"id": 10,
	"phase": "Design",
	"description": "The design phase.",
	"weight": 25,
	"calculatedWeight": 25,
	"order": 1
}
```