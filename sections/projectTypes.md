#Project Types

##Get Project Types

* `GET /projectTypes` Returns all project types.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String|
|id | Integer|
|title | String|
|description | String|
|developmentModel | String {“Scrum”, “Waterfall”, “None”}|
|sprintLength | Integer|
|cocomoEnabled | Boolean|
|versionEnabled | Boolean|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/projectTypes/1",
      "id":1,
      "name":"Scrum",
      "description":"Scrum project type.",
      "developmentModel":"Scrum",
      "sprintLength":14,
      "cocomoEnabled":true,
      "versionEnabled":true
   },
   {
      "url":"https://api.forecast.it/api/v1/projectTypes/2",
      "id":2,
      "name":"Waterfall",
      "description":"Waterfall project type",
      "developmentModel":"Waterfall",
      "sprintLength":0,
      "cocomoEnabled":true,
      "versionEnabled":true
   },...
]
```

##Get Project Type

* `GET /projectTypes/{projectTypeId}` Returns all project types.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String|
|id | Integer|
|title | String|
|description | String|
|developmentModel | String {“Scrum”, “Waterfall”, “None”}|
|sprintLength | Integer|
|cocomoEnabled | Boolean|
|versionEnabled | Boolean|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/projectTypes/1",
   "id":1,
   "name":"Scrum",
   "description":"Scrum project type.",
   "developmentModel":"Scrum",
   "sprintLength":14,
   "cocomoEnabled":true,
   "versionEnabled":true
}
```