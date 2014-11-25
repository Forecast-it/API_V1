#Time Tracking/Registration

##Get Time Registrations

* `GET /projects/{projectId}/time` Returns all time registrations on a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the time registration|
|id | Integer|
|description | String|
|date | Date|
|minutes | Integer|
|workerName | String|
|task | String|
|worker | String|
|projectPhase | String|
|costType | String|
|Team | String|

###Sample JSON Response
```json
[
   {
      "url":"https://api.forecast.it/api/v1/project/1/time/1",
      "id":1,
      "description":"Fixed that annoying bug!",
      "date":"2013-01-16T00:00:00+01:00",
      "minutes":180,
      "workerName":"John Smith",
      "task":"Name of the Task",
      "worker":"John Smith (JS)",
      "projectPhase":"Implementation",
      "costType":"Developer",
      "team":"Team Awesome"
   }, ...
]
```

##Get Time Registration

* `GET /projects/{projectId}/time/{timeId}` Returns a specific time registration.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the time registration|
|id | Integer|
|description | String|
|date | Date|
|minutes | Integer|
|workerName | String|
|task | JSON (Task)|
|worker | JSON (User)|
|projectPhase | JSON (Project Phase)|
|costType | JSON (Cost Type)|
|team | JSON (Team)|

###Sample JSON Response
```json
{
   "url":"https://api.forecast.it/api/v1/project/11/time/1",
   "id":1,
   "description":"",
   "date":"2013-01-16T00:00:00+01:00",
   "minutes":360,
   "workerName":"Niels Frederiksen",
   "task":(See JSON for GET Task),
   "worker":(See JSON for GET User),
   "projectPhase":(See JSON for GET Project Phase),
   "costType":(See JSON for GET Cost Type),
   "team":(See JSON for GET Team)
}
```

##Create Time Registration

* `POST /projects/{projectId}/time` Creates a time registration.

|Response Fields | Description/Format|
|------------ | -------------|
|description | (Optional) String|
|date | (Required) Date|
|minutes | (Required) Integer|
|workerName | (Optional) String|
|task | (Optional) Integer, id of the task|
|worker | (Optional) Integer, id of the user|
|projectPhase | (Optional) Integer, id of the project phase|
|costType | (Optional) Integer, id of the cost type|
|team | (Optional) Integer, id of the team|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/time

```json
{
   "description":"",
   "date":"2013-01-16T00:00:00+01:00",
   "minutes":60,
   "workerName":"John Smith",
   "task":526,
   "worker":21,
   "projectPhase":74,
   "costType":65,
   "team":31
}
```

##Update Time Registration

* `PUT /projects/{projectId}/time/{timeId}` Updates a time registration.

|Response Fields | Description/Format|
|------------ | -------------|
|description | String|
|date | Date|
|minutes | Integer|
|workerName | String|
|task | Integer, id of the task|
|worker | Integer, id of the user|
|projectPhase | Integer, id of the project phase|
|costType | Integer, id of the cost type|
|team | Integer, id of the team|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/time/1

```json
{
   "description":"updated description",
   "minutes":120
}
```

##Delete Time Registration

* `DELETE /projects/{projectId}/time/{timeId}` Delete a time registration.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/time/1
