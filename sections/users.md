#Users

##Get Users

* `GET /users` Returns all users.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the user|
|id | Integer|
|firstName | String|
|lastName | String|
|initials | String|
|email | String|
|dateCreated | Date| 
|lastUpdated | Date|
|isAdmin | Boolean|
|active | Boolean|
|defaultRole | Integer|
|externalEmployeeId | String|
|startPage | String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/users/1",
      "id":1,
      "firstName":"John",
      "lastName":"Smith",
      "initials":"JS",
      "email":"js@domain.com",
      "dateCreated":"2013-01-14T18:46:56+01:00",
      "lastUpdated":"2013-01-14T18:47:58+01:00",
      "isAdmin":true,
      "active":true,
	  "defaultRole":29,
      "externalEmployeeId":null,
      "startPage":"Dashboard"
   }, ...
]
```

##Get User

* `GET /users/{userId}` Returns a specific user.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the user|
|id | Integer|
|firstName | String|
|lastName | String|
|initials | String|
|email | String|
|dateCreated | Date|
|lastUpdated | Date|
|isAdmin | Boolean|
|active | Boolean|
|defaultRole | JSON (Role)|
|externalEmployeeId | String|
|startPage | String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/users/1",
   "id":1,
   "firstName":"John",
   "lastName":"Smith",
   "initials":"JS",
   "email":"js@domain.com",
   "dateCreated":"2013-01-14T18:46:56+01:00",
   "lastUpdated":"2013-01-14T18:47:58+01:00",
   "isAdmin":true,
   "active":true,
   "defaultRole": (See JSON from GET Role),
   "externalEmployeeId":null,
   "startPage":"Dashboard"
}
```

##Create User

* `POST /users` Creates a new user.

|Response Fields | Description/Format|
|------------ | -------------|
|firstName | (Required) String|
|lastName | (Required) String|
|initials | (Required) String|
|email | (Required) String|
|isAdmin | (Required) Boolean|
|active | (Optional) Boolean|
|defaultRole | (required) Integer, id of the default role|
|externalEmployeeId | (Optional) String|
|startPage | (Required) String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Request
POST https://api.forecast.it/api/v1/users

```javascript
{
   "firstName":"John",
   "lastName":"Smith",
   "initials":"JS",
   "email":"js@domain.com",
   "isAdmin":true,
   "active":true,
   "defaultRole":4,
   "externalEmployeeId":"exId1",
   "startPage":"Dashboard"
}
```

##Update User

* `PUT /users/{userId}` Updates a user.

|Response Fields | Description/Format|
|------------ | -------------|
|firstName | String|
|lastName | String|
|initials | String|
|email | String|
|isAdmin | Boolean|
|active | Boolean|
|defaultRole | Integer, id of the default role|
|externalEmployeeId | String|
|startPage | String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/users/1

```javascript
{
   "firstName":"John",
   "lastName":"Doe"
}
```

##Delete User

* `DELETE /users/{userId}` Deletes a user.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/users/1