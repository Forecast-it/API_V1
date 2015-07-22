#Tasks

##Get Tasks

* `GET /projects/{projectId}/tasks` Returns all tasks for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the task|
|id | Integer|
|title | String|
|description | String|
|estimate | Integer|
|timeLeft | Integer|
|projectPhase | Integer|
|status | Integer, Only used for scrum projects|
|waterfallStatus | String, Only used for waterfall projects {"To Do", "In Progress", "Ready for Review", "Done"}|
|owners | List<Integer>|
|userStory | Integer, Only used for scrum projects|
|deadline | Date, Only used for waterfall projects|
|tags | List<Integer>|
|integrationTimelogTask | Boolean|
|integrationTfsId | Integer|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|
|modifiedOn | Date|
|modifiedBy | Integer|
|createdOn | Date|
|createdBy | Integer|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/projects/1/tasks/1",
      "id":1,
      "title":"Task Title",
      "description":"Task Description",
      "estimate":8,
      "timeLeft":8,
	  "projectPhase": 30,
      "status":20,
	  "waterfallStatus": null,
      "owners":[
	      42
      ],
      "userStory":22,
      "deadline":null,
      "tags":[
         12,
		 13
      ],
	  "integrationTimelogTask": false,
	  "integrationTfsId": null,
	  "integrationTimelogId": null,
      "integrationTimelogGuid": null,
      "modifiedOn": "2015-07-22T11:06:03+02:00",
      "modifiedBy": 20,
      "createdOn": "2015-07-22T11:06:03+02:00",
      "createdBy": 20,
   }, ...
]
```

##Get Task

* `GET /projects/{projectId}/tasks/{id}` Returns one task.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the task|
|id | Integer|
|title | String|
|description | String|
|estimate | Integer|
|timeLeft | Integer|
|projectPhase | JSON (Project Phase)|
|status | JSON (Scrum Stage), Only used for scrum projects|
|waterfallStatus | String, Only used for waterfall projects {"To Do", "In Progress", "Ready for Review", "Done"}|
|owners | List<JSON (User)>|
|userStory | JSON (User Story), Only used for scrum projects|
|deadline | Date, Only used for waterfall projects|
|tags | List<JSON (Tag)>|
|registeredTime | List<JSON (Time)>|
|integrationTimelogTask | Boolean|
|integrationTfsId | Integer|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|
|modifiedOn | Date|
|modifiedBy | Integer|
|createdOn | Date|
|createdBy | Integer|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/projects/1/tasks/1",
   "id":1,
   "title":"Task Title",
   "description":"Task Description",
   "estimate":8,
   "timeLeft":8,
   "projectPhase": (See JSON from GET Project Phase),
   "status": (See JSON from GET Scrum Stage),
   "waterfallStatus": null,
   "owners":[
      (See JSON from GET User)
   ],
   "userStory": (See JSON from GET User Story) ,
   "deadline":null,
   "tags":[
      (See JSON from GET Tag)
   ],
   "registeredTime":[
      (See JSON from GET Time Registrations)
   ],
   "integrationTimelogTask": false,
   "integrationTfsId": 7,
   "integrationTimelogId": null,
   "integrationTimelogGuid": null,
   "modifiedOn": "2015-07-22T11:06:03+02:00",
   "modifiedBy": 20,
   "createdOn": "2015-07-22T11:06:03+02:00",
   "createdBy": 20
}
```

##Create Task

* `POST /projects/{projectId}/tasks` Creates a new task.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|description | (Optional) String|
|estimate | (Optional) Integer|
|timeLeft | (Optional) Integer|
|projectPhase | (Required) Integer, id of the project phase|
|status | (Optional) Integer, id of the Scrum Stage. If not set the first column will be set, Only used for scrum projects|
|waterfallStatus | String, Only used for waterfall projects {"To Do", "In Progress", "Ready for Review", "Done"}|
|owners | (Optional) List<Integer>, id of the users|
|userStory | (Required for scrum) Integer, id of the user story, Only used for scrum projects|
|deadline | (Optional) Date, Only used for waterfall projects|
|tags | (Optional) List<Integer>|
|integrationTimelogTask | (Optional) Boolean|
|integrationTfsId | (Optional) Integer|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/tasks

```javascript
{
   "title":"Task Title",
   "description":"Task Description",
   "estimate":8,
   "timeLeft":8,
   "projectPhase":1,
   "status":4,
   "owner":[42],
   "userStory": 5435,
   "deadline":null,
   "tags":[
      432,
      437
   ]
}
```

##Update Task

* `PUT /projects/{projectId}/tasks/{id}` Updates a task.

|Response Fields | Description/Format|
|------------ | -------------|
|title | String|
|description | String|
|estimate | Integer|
|timeLeft | Integer|
|projectPhase | Integer, id of the project phase|
|status | Integer, id of the scrum stage, Only used for scrum projects|
|waterfallStatus | String, Only used for waterfall projects {"To Do", "In Progress", "Ready for Review", "Done"}|
|owners | List<Integer>, id of the users|
|userStory | Integer, id of the user story, Only used for scrum projects|
|deadline | Date, Only used for waterfall projects|
|tags | List<Integer>|
|integrationTimelogTask | Boolean|
|integrationTfsId | Integer|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/tasks/1

```javascript
{
   "timeLeft":0,
   "status":5
}
```

##Delete Task

* `DELETE /projects/{projectId}/tasks/{id}` Deletes a task.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/tasks/1
