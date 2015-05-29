#Sprints

##Get Sprints

* `GET /projects/{projectId}/sprints` Returns all sprints for a project, including backlog.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the Sprint|
|id | Integer|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {"Active", "Closed"}|
|tfsIntegrationId | Integer|
|tags | List<String>, List of Tag Names|
|teams | List<String>, List of Team Names|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/project/1/sprints/1",
      "id":1,
      "title":"Backlog",
      "description":"",
      "startDate":null,
      "endDate":null,
      "status":"Active",
	  "tfsIntegrationId":null,
      "tags":[
      ],
	  "teams":[
	     "Frontend"
      ]
   },
   {
      "url":"https://api.forecast.it/api/v1/project/1/sprints/2",
      "id":2,
      "title":"Sprint 1",
      "description":"",
      "startDate":"2013-01-01T00:00:00+01:00",
      "endDate":"2013-01-23T00:00:00+01:00",
      "status":"Closed",
	  "tfsIntegrationId":4,
      "tags":[
         "Web", ...
      ],
	  "teams":[
	     "Team 1"
      ]
   }, ...
]
```

##Get Sprint

* `GET /projects/{projectId}/sprints/{sprintId}` Returns one sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the Sprint|
|id | Integer|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {"Active", "Closed"}|
|tfsIntegrationId | Integer|
|tags | List<JSON (Tag)>|
|userstories | List<JSON (User Story)>|
|teams | List<JSON (Team)>|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/project/1/sprints/2",
   "id":2,
   "title":"Sprint 1",
   "description":"",
   "startDate":"2013-01-01T00:00:00+01:00",
   "endDate":"2013-01-23T00:00:00+01:00",
   "status":"Closed",
   "tfsIntegrationId":4,
   "tags":[ (See JSON for GET Tag), ...
   ],
   "userstories":[ (See JSON for GET User Story), ...
   ],
   "teams":[ (See JSON for GET Team), ...
   ]
}
```

##Create Sprint

* `POST /projects/{projectId}/sprints` Creates a new sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|description | (Optional) String|
|startDate | (Required) Date|
|endDate | (Required) Date|
|status | (Required) String {"Active", "Closed"}|
|tfsIntegrationId | (Optional) Integer|
|tags | (Optional) List<Integer>, List of Tag ids|
|teams | (Optional) List<Integer>, List of Team ids|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/sprints

```javascript
{
   "title":"Task Title",
   "description":"Task Description",
   "startDate":"2013-01-01T00:00:00+01:00",
   "endDate":"2013-01-23T00:00:00+01:00",
   "status":"Active",
   "tags":[
      432,
      437
   ],
   "teams":[
      22,
      23
   ]
}
```

##Update Sprint

* `PUT /projects/{projectId}/sprints/{sprintId}` Updates a sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {"Active", "Closed"}|
|tfsIntegrationId | (Optional) Integer|
|tags | List<Integer>, List of Tag ids|
|teams | List<Integer>, List of Team ids|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/sprints/1

```javascript
{
   "status":"Closed",
   "tags":[
      432,
      437,
      436
   ]
}
```

##Delete Sprint

* `DELETE /projects/{projectId}/sprints/{sprintId}` Delete a sprint.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/sprints/1
