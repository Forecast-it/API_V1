#Project People/Resources

##Get Project Resources

* `GET /projects/{projectId}/projectResources` Returns all people/resources for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project resource|
|id | Integer|
|user | String, User initials|
|role | String, Name of the role|
|team | String, Name of the team|
|costType | String, Name of the cost type|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/project/1/projectResources/1",
      "id":1,
      "user":"John Smith (JS)",
      "role":"Master",
      "team":"Team 1",
      "costType":"Developer"
   }, ...
]
```

##Get Project Resource

* `GET /projects/{projectId}/projectResources/{resourceId}` Returns a specific project resource.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project resource|
|id | Integer|
|user | JSON (User)|
|role | JSON (Role)|
|team | JSON (Team)|
|costType | JSON (Cost Type)|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/project/1/projectResources/1",
   "id":1,
   "user":(See JSON for GET User),
   "role":(See JSON for GET Role),
   "team":(See JSON for GET Team),
   "costType":/See JSON for GET Cost Type)
}
```

##Create Project Resource

* `POST /projects/{projectId}/projectResources` Creates a new resource for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|user | (Required) Integer. Id of the user|
|role | (Required) Integer. Id of the role|
|team | (Required) Integer, Id of the team|
|costType | (Optional) Integer, Id of the cost type|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/{projectId}/projectResources

```javascript
{
   "user":23,
   "role":42,
   "team":12,
   "costType":65
}
```

##Update Project Access

* `PUT /projects/{projectId}/projectResources/{resourceId}` Updates a resource for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|user | Integer. Id of the user|
|role | Integer. Id of the role|
|team | Integer, Id of the team|
|costType | Integer, Id of the cost type|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/projectResources/1

```javascript
{
   "role":41,
   "costType":64
}
```

##Delete Project Access

* `DELETE /projects/{projectId}/projectResources/{resourceId}` Deletes a resource for a project.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/projectResources/1
