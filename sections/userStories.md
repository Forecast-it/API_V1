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
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|
|integrationTfsId | Integer|
|owners |List<String>|
|tags | List<String>|
|dependencies | List<String>|
|tasks | List<String>|

###Sample JSON Response
```javascript
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
	  "status": "To do",
	  "integrationTimelogId": 36,
      "integrationTimelogGuid": "2922204c-efb6-4216-8da2-d724fb1fa51d",
      "integrationTfsId": 3,
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
|type | JSON (User Story Type)|
|acceptanceCriteria | String|
|estimate | Integer|
|epic | String|
|sprint | JSON (Sprint)|
|status | JSON (Scrum Stage)|
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|
|integrationTfsId | Integer|
|owners | List<JSON (User)>|
|tags | List<JSON (Tag)>|
|dependencies | List<JSON (User Story)>|
|tasks | List<JSON (Task)|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/project/1/userStories/1",
   "id":17
   "title":"The title of the user story",
   "description":"",
   "type":(See JSON for GET User Story Type),
   "acceptanceCriteria":"The acceptance criteria of the user story",
   "estimate":16,
   "epic":null,
   "sprint":(See JSON for GET Sprint),
   "status":(See JSON for GET Scrum Stage),
   "integrationTimelogId": 36,
   "integrationTimelogGuid": "2922204c-efb6-4216-8da2-d724fb1fa51d",
   "integrationTfsId": 3,
   "owners":[ (See JSON for GET User),...],
   "tags":[ (See JSON for GET Tag),...],
   "dependencies":[(See JSON for GET User Story),...],
   "tasks":[(See JSON for GET Task),...]
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
|integrationTimelogId | (Optional) Integer|
|integrationTimelogGuid | (Optional) String|
|integrationTfsId | (Optional) Integer|
|status | (Optional) Integer, id of the scrum column|
|owners | (Optional) List<Integer> list of ids of users|
|tags | (Optional) List<Integer> list of ids of tags|

###Sample JSON Request
POST https://api.forecast.it/api/v1/project/1/userStories

```javascript
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
|integrationTimelogId | Integer|
|integrationTimelogGuid | String|
|integrationTfsId | Integer|
|status | Integer, id of the scrum column|
|owners | List<Integer> list of ids of users|
|tags | List<Integer> list of ids of tags|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/project/1/userStories/1

```javascript
{
   "title":"New title",
   "acceptanceCriteria":"New acceptance criteria"
}
```

##Delete User Story

* `DELETE /project/{projectId}/userStories/{id}` Deletes a user story.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/userStories/1
