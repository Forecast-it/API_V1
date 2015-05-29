#Teams

##Get Teams

* `GET /teams` Returns all teams.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project resource|
|id | Integer|
|name | String|
|description | String|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/teams/1",
      "id":1,
      "name":"Team Name",
      "description":"A description of the team"
   }, ...
]
```

##Get Team

* `GET /teams/{teamId}` Returns a specific team.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the project resource|
|id | Integer|
|name | String|
|description | String|
|users | List<JSON (User)>, List of users in the team|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/teams/1",
   "id":1,
   "name":"Team Name",
   "description":"A description of the team",
   "users":[
      (See JSON for GET User), ...
   ]
}
```

##Create Team

* `POST /teams` Create a new team.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String (Required)|
|description | String (Optional)|

###Sample JSON Request
POST https://api.forecast.it/api/v1/teams

```javascript
{
   "name":"New Team",
   "description":"A description of the team"
}
```

##Update Team

* `PUT /teams/{teamId}` Updates a team.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|
|description | String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/teams/1

```javascript
{
   "name":"Different Team Name",
   "description":"New description"
}
```

##Delete Team

* `DELETE /teams/{teamId}` Deletes a team.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/teams/1
