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
|startPage | String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Response
```json
[
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
|userName | String|
|dateCreated | Date|
|lastUpdated | Date|
|isAdmin | Boolean|
|active | Boolean|
|externalEmployeeId | String|
|startPage | String {"Dashboard", "SelectProject", "ProjectPortfolio"}|

###Sample JSON Response
```json
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
   "externalEmployeeId":null,
   "startPage":"Dashboard"
}
```