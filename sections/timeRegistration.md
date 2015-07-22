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
|task | Integer|
|worker | Integer|
|projectPhase | Integer|
|costType | Integer|
|Team | Integer|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/projects/1/time/1",
      "id":1,
      "description":"Fixed that annoying bug!",
      "date":"2013-01-16T00:00:00+01:00",
      "minutes":180,
      "workerName":"John Smith",
      "task":12,
      "worker":22,
      "projectPhase":11,
      "costType":17,
      "team":25,
	  "integrationTimelogId":null,
	  "integrationTimelogGuid":null
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
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/projects/1/time/1",
   "id":1,
   "description":"",
   "date":"2013-01-16T00:00:00+01:00",
   "minutes":360,
   "workerName":"Niels Frederiksen",
   "task":(See JSON for GET Task),
   "worker":(See JSON for GET User),
   "projectPhase":(See JSON for GET Project Phase),
   "costType":(See JSON for GET Cost Type),
   "team":(See JSON for GET Team),
   "integrationTimelogId": null,
   "integrationTimelogGuid": null
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
|integrationTimelogId | (Optional) Integer|
|integrationTimelogGuid | (Optional) String|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/time

```javascript
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
|integrationTimelogId | Integer|
|integrationTimelogGuid | (Optional) String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/time/1

```javascript
{
   "description":"updated description",
   "minutes":120
}
```

##Delete Time Registration

* `DELETE /projects/{projectId}/time/{timeId}` Delete a time registration.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/time/1
