#Sprints

##Get Sprints

* `GET /projects/{projectId}/sprints` Returns all sprints for a project, including backlog.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the Sprint|
|id | Integer|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {“Active”, “Closed”}|
|tags | List<String>, List of Tag Names|

###Sample JSON Response
```json
[
   {
      "url":"http://api.forecast.it/api/v1/project/1/sprints/1",
      "id":1,
      "title":"Backlog",
      "description":"",
      "startDate":null,
      "endDate":null,
      "status":"Active",
      "tags":[

      ]
   },
   {
      "url":"http://api.forecast.it/api/v1/project/1/sprints/2",
      "id":2,
      "title":"Sprint 1",
      "description":"",
      "startDate":"2013-01-01T00:00:00+01:00",
      "endDate":"2013-01-23T00:00:00+01:00",
      "status":"Closed",
      "tags":[
         “Web”, ...
      ]
   }, ...
]
```

##Get Sprint

* `GET /projects/{projectId}/sprints/{id}` Returns one sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the Sprint|
|id | Integer|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {“Active”, “Closed”}|
|tags | List<JSON (Tag)>|
|userstories | List<JSON (User Story)>|

###Sample JSON Response
```json
{
   "url":"http://api.forecast.it/api/v1/project/1/sprints/2",
   "id":2,
   "title":"Sprint 1",
   "description":"",
   "startDate":"2013-01-01T00:00:00+01:00",
   "endDate":"2013-01-23T00:00:00+01:00",
   "status":"Closed",
   "tags":[

   ],
   "userstories":[ (See JSON for GET User Story), ...
   ]
}
```

##Create Sprint

* `POST /projects/{projectId}/sprints` Creates a new sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|description | (Optional) String|
|startDate | (Required) Date|
|endDate | (Required) Date|
|status | (Required) String {“Active”, “Closed”}|
|tags | (Optional) List<Integer>, List of Tag ids|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/{projectId}/sprints

```json
{
   "title":"Task Title",
   "description":"Task Description",
   "startDate":"2013-01-01T00:00:00+01:00",
   "endDate":"2013-01-23T00:00:00+01:00",
   "status":"Active",
   "tags":[
      432,
      437
   ]
}
```

##Update Sprint

* `PUT /projects/{projectId}/sprints/{id}` Updates a sprint.

|Response Fields | Description/Format|
|------------ | -------------|
|title | String|
|description | String|
|startDate | Date|
|endDate | Date|
|status | String {“Active”, “Closed”}|
|tags | List<Integer>, List of Tag ids|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/{projectId}/sprints/{id}

```json
{
    "description":"Updated Description"
}
```

##Delete Sprint

* `DELETE /projects/{projectId}/sprints/{id}` Delete a sprint.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/{projectId}/sprints/{id}
