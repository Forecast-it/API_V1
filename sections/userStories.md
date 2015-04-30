#User Stories

##Get User Stories

* `GET /projects/{id}/userStories` Returns all userstories for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the userstory|
|id | Integer|
|title | String|
|description | String|
|type | String|
|acceptanceCriteria | String|
|estimate | Integer|
|epic | String|
|sprint | String|
|status | String|
|owners |List<String>|
|tags | List<String>|
|dependencies | List<String>|
|tasks | List<String>|

###Sample JSON Response
```json
[
   {
      "url":"https://api.forecast.it/api/v1/project/1/userStories/1",
      "id":1,
      "title":"The title of the user story",
      "description":null,
      "type":"Development",
      "acceptanceCriteria":"The acceptance criteria of the user story",
      "estimate":16,
      "epic":"Epic number 2",
      "sprint":"The name of the Sprint",
      "owners":[
         "John Smith (JS)"
      ],
      "tags":[

      ],
      "dependencies":[

      ],
      "tasks":[
         "View data",
         "View persistence",...
      ]
   },...
]
```

##Get User Story

* `GET /project/{id}/userStories/{userStoryId}` Returns a user story for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the user story|
|id | Integer|
|title | String|
|description | String|
|type | String|
|acceptanceCriteria | String|
|estimate | Integer|
|epic | String|
|sprint | JSON (Sprint)|
|status | String|
|owners | List<JSON (User)>|
|tags | List<JSON (Tag)>|
|dependencies | List<JSON (User Story)>|

###Sample JSON Response
```json
{
   "url":"https://api.forecast.it/api/v1/project/1/userStories/1",
   "id":17
   "title":"The title of the user story",
   "description":null,
   "type":{
      "url":"https://api.forecast.it/api/v1/userStoryTypes/1",
      "id":1,
      "name":"Development",
      "description":"This is a development user story"
   },
   "acceptanceCriteria":"The acceptance criteria of the user story",
   "estimate":16,
   "epic":"",
   "sprint":{
      "url":"https://api.forecast.it/api/v1/project/1/sprints/1",
      "id":1,
      "title":"The name of the Sprint",
      "description":"Sprint description",
      "startDate":"2013-01-14T00:00:00+01:00",
      "endDate":"2013-01-21T00:00:00+01:00",
      "status":"Closed",
      "tags":[

      ]
   },
   "owners":[
      {
         "url":"https://api.forecast.it/api/v1/users/1",
         "id":1,
         "firstName":"John",
         "lastName":"Smith",
         "initials":"JS",
         "email":"js@domain.com",
         "userName":"js@domain.com",
         "dateCreated":"2013-01-14T18:46:56+01:00",
         "lastUpdated":"2013-01-14T18:47:58+01:00",
         "isAdmin":true,
         "active":true,
         "externalEmployeeId":null
      },...
   ],
   "tags":[

   ],
   "dependencies":[

   ],
   "tasks":[
      {
         "url":"https://api.forecast.it/api/v1/project/1/tasks/1",
         "id":1,
         "title":"View data",
         "description":"",
         "estimate":6,
         "timeLeft":0,
         "status":"Done",
         "owner":"John Smith (JS)",
         "userStory":"The title of the user story",
         "deadline":null,
         "tags":[

         ]
      },...
   ]
}
```

##Create User Story

* `POST /project/{projectId}/userStories` Creates a user story.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String| 
|description | (Optional) String|
|type | (Required) Integer, id of the user story type|
|acceptanceCriteria | (Optional) String|
|estimate | (Required) Integer|
|epic | (Optional) String|
|sprint | (Required) Integer, id of the sprint or backlog|
|status | (Optional) Integer, id of the scrum column|
|owners | (Optional) List<Integer> list of ids of users|
|tags | (Optional) List<Integer> list of ids of tags|

###Sample JSON Request
POST https://api.forecast.it/api/v1/project/1/userStories

```json
{
   "title":"The title of the user story",
   "type":42,
   "acceptanceCriteria":"The acceptance criteria of the user story",
   "estimate":16,
   "sprint":423,
   "owners":[34]
}
```

##Update User Story

* `PUT /project/{projectId}/userStories/{id}` Updates a user story.

|Response Fields | Description/Format|
|------------ | -------------|
|title | String| 
|description | String|
|type | Integer, id of the user story type|
|acceptanceCriteria | String|
|estimate | Integer|
|epic | String|
|sprint | Integer, id of the sprint or backlog|
|status | Integer, id of the scrum column|
|owners | List<Integer> list of ids of users|
|tags | List<Integer> list of ids of tags|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/project/1/userStories/1

```json
{
   "title":"New title",
   "acceptanceCriteria":"New acceptance criteria"
}
```

##Delete User Story

* `DELETE /project/{projectId}/userStories/{id}` Deletes a user story.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/userStories/1
