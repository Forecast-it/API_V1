#Milestones

##Get Milestones

* `GET /projects/{id}/milestones` Returns all milestones for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the milestones|
|id | Integer|
|title | String|
|description | String|
|deadline | Date|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/projects/1/milestones/1",
      "id":1,
      "title":"The title of the milestone",
      "description":"Description of the element",
      "deadline":"2016-12-31T00:00:00+00:00"
   },...
]
```

##Get Milestone

* `GET /projects/{id}/milestones/{milestoneId}` Returns a milestone for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the milestones|
|id | Integer|
|title | String|
|description | String|
|deadline | Date|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/projects/1/milestones/1",
   "id":1,
   "title":"The title of the milestone",
   "description":"Description of the element",
   "deadline":"2016-12-31T00:00:00+00:00"
}
```

##Create Milestone

* `POST /project/{projectId}/milestones` Creates a milestone.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|description | (Optional) String|
|deadline | (Required) Date|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/milestones

```javascript
{
   "title":"The title of the milestone",
   "description":"description of milestone",
   "deadline":"2016-12-31T00:00:00+00:00"
}
```

##Update Milestone

* `PUT /projects/{projectId}/milestones/{id}` Updates a milestone.

|Response Fields | Description/Format|
|------------ | -------------|
|title | String|
|description | String|
|deadline | Date|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/milestones/1

```javascript
{
   "title":"New title",
   "description":"Updated description"
}
```

##Delete Milestone

* `DELETE /projects/{projectId}/milestones/{id}` Deletes a milestone.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/milestones/1