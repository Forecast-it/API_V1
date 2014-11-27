#Scrum Stages

##Get Scrum Stages

* `GET /projects/{projectId}/scrumStages` Returns all scrum stages for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the cost type|
|id | Integer|
|title | String, Title of the cost type|
|category | String, {“To Do”, “In Progress”, “Ready For Review”, “Done”}| 
|description | String|

###Sample JSON Response
```json
[
    {
	    "url": "https://api.forecast.it/api/v1/scrumStage/10",
	    "id": 10,
	    "title": "To Do",
	    "category": "To Do",
	    "description": "Tasks that have not yet been started."
    },
    {
		"url": "https://api.forecast.it/api/v1/scrumStage/11",
		"id": 11,
		"title": "In Progress",
		"category": "In Progress",
		"description": "Tasks currently being worked on."
	}, ...
]
```

##Get Project Phase

* `GET /projects/{projectId}/scrumStages/{scrumStageId}` Returns one scrum stage.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the cost type|
|id | Integer|
|title | String, Title of the cost type|
|category | String, {“To Do”, “In Progress”, “Ready For Review”, “Done”}| 
|description | String|

###Sample JSON Response
```json
{
	"url": "https://api.forecast.it/api/v1/scrumStage/10",
	"id": 10,
	"title": "To Do",
	"category": "To Do",
	"description": "Tasks that have not yet been started."
}
```