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
|userName | String|
|dateCreated | Date| 
|lastUpdated | Date|
|isAdmin | Boolean|
|active | Boolean|
|externalEmployeeId | String|
|startPage | String {“Dashboard”, ”SelectProject”,”ProjectPortfolio”}|

###Sample JSON Response
```json
[
   {
      "url":"http://api.forecast.it/api/v1/users/1",
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
      "externalEmployeeId":null,
      "startPage":"Dashboard"
   }, ...
]
```

##Get User

* `GET /users/{id}` Returns a specific user.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL to the user|
|id | Integer|
|firstName | String|
|lastName | String|
|initials | String|
|email | String|
|userName | String|
|dateCreated | Date|
|lastUpdated | Date|
|isAdmin | Boolean|
|active | Boolean|
|externalEmployeeId | String|
|startPage | String {“Dashboard”, ”SelectProject”,”ProjectPortfolio”}|

###Sample JSON Response
```json
{
   "url":"http://api.forecast.it/api/v1/users/1",
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
|externalEmployeeId | (Optional) String|
|startPage | (Required) String {“Dashboard”, ”SelectProject”,”ProjectPortfolio”}|

###Sample JSON Request
POST https://api.forecast.it/api/v1/users

```json
{
   "firstName":"John",
   "lastName":"Smith",
   "initials":"JS",
   "email":"js@domain.com",
   "userName":"js@domain.com",
   "isAdmin":true,
   "active":true,
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
|externalEmployeeId | String|
|startPage | String {“Dashboard”, ”SelectProject”,”ProjectPortfolio”}|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/users/{userId}

```json
TODO!!!
```

##Delete User

* `DELETE /users/{userId}` Deletes a user.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/users/{userId}
