#User Story Types

##Get User Story Types

* `GET /userStoryTypes` Returns all user story types.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL|
|id | Integer|
|name | String|
|description | String|

###Sample JSON Response
```json
[
   {
      "url":"http://api.forecast.it/api/v1/userStoryTypes/1",
      "id":1,
      "name":"Development",
      "description":"This is a regular development user story"
   }, ...
]
```

##GGet User Story Type

* `GET /userstorytypes/{userStoryTypeid}` Returns a specific user story type.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL|
|id | Integer|
|name | String|
|description | String|
|userstories | List<JSON (User Story)>, list of user stories with this type|

###Sample JSON Response
```json
{
   "url":"http://api.forecast.it/api/v1/userStoryTypes/1",
   "id":1,
   "name":"Development",
   "description":"This is a regular development user story",
   "userstories":[
      (See JSON for GET User Story), ...
   ]
}
```

##Create User Story Type

* `POST /userStoryTypes` Creates a new user story type.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String (Required)|
|description | String (Optional)|

###Sample JSON Request
POST https://api.forecast.it/api/v1/userStoryTypes

```json
{
   "name":"Development",
   "description":"This is a regular development user story"
}
```

##Update User Story Type

* `PUT /userStoryTypes/{userStoryTypeId}` Updates a user story type.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|
|description | String|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/userStoryTypes/1

```json
TODO!!!
```

##Delete User Story Type

* `DELETE /userStoryTypes/{userStoryTypeId}` Deletes a user story type.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/userStoryTypes/1
