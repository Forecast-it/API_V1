#Project Phases

##Get Project Phases

* `GET /projects/{projectId}/projectPhases` Returns all phases for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project phase|
|id | Integer|
|phase | String, Name of the phase|
|description | String|
|weight | Integer, The weight in percent|
|calculatedWeight | Integer, the calculated weight from Forecast.it|
|order | Integer, The sorting order of the phase|

###Sample JSON Response
```javascript
[
    {
	    "url": "https://api.forecast.it/api/v1/projects/1/projectPhases/10",
	    "id": 10,
	    "phase": "Design",
	    "description": "The design phase.",
	    "weight": 25,
	    "calculatedWeight": 25,
	    "order": 1
    },
	{
	    "url": "https://api.forecast.it/api/v1/projects/1/projectPhases/11",
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

* `GET /projects/{projectId}/projectPhases/{phaseId}` Returns one project phase.

Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project phase|
|id | Integer|
|phase | String, Name of the phase|
|description | String|
|weight | Integer, The weight in percent|
|calculatedWeight | Integer, the calculated weight from Forecast.it|
|order | Integer, The sorting order of the phase|

###Sample JSON Response
```javascript
{
	"url": "https://api.forecast.it/api/v1/projects/1/projectPhases/10",
	"id": 10,
	"phase": "Design",
	"description": "The design phase.",
	"weight": 25,
	"calculatedWeight": 25,
	"order": 1
}
```