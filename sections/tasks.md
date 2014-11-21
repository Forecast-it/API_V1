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
|projectPhase | String|
|status | String|
|owners | List<String>|
|userStory | String|
|deadline | Date|
|closed | Boolean|
|tags | List<String>|

###Sample JSON Response
```json
[
   {
      "url":"http://api.forecast.it/api/v1/project/1/tasks/1",
      "id":1,
      "title":"Task Title",
      "description":"Task Description",
      "estimate":8,
      "timeLeft":8,
      "status":"To Do",
      "owner":[
	      "John Smith (JS)"
      ],
      "userStory":"User Story Title",
      "deadline":null,
      "tags":[
         "Web", ...
      ]
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
|projectPhase | String|
|status | String|
|owners | List<JSON (User)>|
|userStory | JSON (User Story)|
|deadline | Date|
|closed | Boolean|
|tags | List<JSON (Tag)>|
|registeredTime | List<JSON (Time)>|

###Sample JSON Response
```json
{
   "url":"http://api.forecast.it/api/v1/project/1/tasks/1",
   "id":1,
   "title":"Task Title",
   "description":"Task Description",
   "estimate":8,
   "timeLeft":8,
   "status":"To Do",
   "owners":[
      (See JSON from GET User)
   ],
   "userStory": (See JSON from GET User Story) ,
   "deadline":null,
   "tags":[
      {
         "url":"http://api.forecast.it/api/v1/tags/32",
         "id":32,
         "name":"Web",
         "active":true
      }, ...
   ],
   "registeredTime":[
      {  
         "url":"http://api.forecast.it/api/v1/project/1/time/1",
         "id":1,
         "description":"Description of registered time",
         "date":"2013-11-08T00:00:00+01:00",
         "minutes":60,
         "workerName":"John Smith",
         "task":"Task Title",
         "worker":"John Smith (JS)",
         "projectPhase":"Implementation",
         "costType":"Developer",
         "team":null
      }, ...
   ]
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
|status | (Optional) Integer, id of the scrum column|
|owners | (Required) List<Integer>, id of the users|
|userStory | (Optional) Integer, id of the user story|
|deadline | (Optional) Date|
|closed | (Optional) Boolean|
|tags | (Optional) List<Integer>|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/tasks

```json
{
   "title":"Task Title",
   "description":"Task Description",
   "estimate":8,
   "timeLeft":8,
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
|status | Integer, id of the scrum column|
|owners | List<Integer>, id of the users|
|userStory | Integer, id of the user story|
|deadline | Date|
|closed | Boolean|
|tags | List<Integer>|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/tasks/1

```json
{
   "timeLeft":0,
   "status":5
}
```

##Delete Task

* `DELETE /projects/{projectId}/tasks/{id}` Deletes a task.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/tasks/1
