#Work Breakdown

##Get Work Breakdowns

* `GET /projects/{id}/workBreakdowns` Returns all work breakdowns for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the work breakdowns|
|id | Integer|
|title | String|
|isFolder | Boolean|
|team | Integer|
|projectPhase | Integer|
|minimumHours | Integer|
|likelyHours | Integer|
|maximumHours | Integer|
|predictedHours | Integer|
|role | Integer|
|tags | List<Integer>|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/projects/1/workBreakdowns/1",
      "id":1,
      "title":"The title of the work breakdown",
      "isFolder":false,
      "team":14,
      "projectPhase":1,
      "minimumHours":16,
      "likelyHours":20,
      "maximumHours":22,
      "predictedHours": 19,
      "role": 36,
      "tags":[
         11
      ]
   },...
]
```

##Get Work Breakdown

* `GET /projects/{id}/workBreakdowns/{workBreakdownId}` Returns a work breakdown for a project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the work breakdowns|
|id | Integer|
|title | String|
|isFolder | Boolean|
|team | JSON(Teams)|
|projectPhase | JSON(Project Phases)|
|minimumHours | Integer|
|likelyHours | Integer|
|maximumHours | Integer|
|predictedHours | Integer|
|role | JSON(Roles)|
|tags | List<JSON (Tag)>|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/projects/1/workBreakdowns/1",
   "id":1,
   "title":"The title of the work breakdown",
   "isFolder":false,
   "team":(See JSON for GET Team),
   "projectPhase":(See JSON for GET Project Phase),
   "minimumHours":16,
   "likelyHours":20,
   "maximumHours":22,
   "predictedHours": 19,
   "role": (See JSON for GET Role),
   "tags":[ (See JSON for GET Tag),...]
}
```

##Create Work Breakdown

* `POST /project/{projectId}/workBreakdowns` Creates a work breakdown.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|isFolder | (Required) Boolean|
|team | (Optional) Integer. Only when isFolder is set to false.|
|projectPhase | (Optional) Integer. Only when isFolder is set to false.|
|minimumHours | (Required) Integer. Only when isFolder is set to false.|
|likelyHours | (Required) Integer. Only when isFolder is set to false.|
|maximumHours | (Required) Integer. Only when isFolder is set to false.|
|role | (Optional) Integer. Only when isFolder is set to false.|
|tags | (Optional) List<Integer>. Only when isFolder is set to false.|

###Sample JSON Request
POST https://api.forecast.it/api/v1/projects/1/workBreakdowns

```javascript
{
   "title":"The title of the work breakdown",
   "isFolder":false,
   "team":14,
   "projectPhase":1,
   "minimumHours":16,
   "likelyHours":20,
   "maximumHours":22,
   "role": 36,
   "tags":[
      11
   ]
}
```

##Update Work Breakdown

* `PUT /projects/{projectId}/workBreakdowns/{id}` Updates a work breakdown.

|Response Fields | Description/Format|
|------------ | -------------|
|title | (Required) String|
|team | (Optional) Integer|
|projectPhase | (Optional) Integer|
|minimumHours | (Required) Integer|
|likelyHours | (Required) Integer|
|maximumHours | (Required) Integer|
|role | (Optional) Integer|
|tags | (Optional) List<Integer>|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/projects/1/workBreakdowns/1

```javascript
{
   "title":"New title",
   "minimumHours":45
}
```

##Delete Work Breakdown

* `DELETE /projects/{projectId}/workBreakdowns/{id}` Deletes a work breakdown.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1/workBreakdowns/1