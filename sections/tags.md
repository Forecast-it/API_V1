#Tags

##Get Tags

* `GET /tags` Returns all tags.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL for the tag|
|id | Integer|
|name | String|
|active | Boolean, Has the Tag been disabled|

###Sample JSON Response
```javascript
[
   {
      "url":"https://api.forecast.it/api/v1/tags/1",
      "id":1,
      "name":"Web",
      "active":true
   }, ...
]
```

##Get Tag

* `GET /tags/{tagId}` Returns a specific tag.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, URL|
|id | Integer|
|name | String|
|project | Boolean, Can the tag be used on projects|
|threePoint | Boolean, Can the tag be used on three point estimates|
|useCase | Boolean, Can the tag be used on use cases|
|functionPoint | Boolean, Can the tag be used on function point estimates|
|otherCost | Boolean, Can the tag be used on other costs|
|userStory | Boolean, Can the tag be used on user stories|
|scrumTask | Boolean, Can the tag be used on scrum tasks|
|sprints | Boolean, Can the tag be used on scrum sprints|
|waterfallTask | Boolean, Can the tag be used on waterfall tasks|
|useCaseActor | Boolean, Can the tag be used on use case actors|
|active | Boolean, Has the Tag been disabled|

###Sample JSON Response
```javascript
{
   "url":"https://api.forecast.it/api/v1/tags/1",
   "id":1,
   "name":"Web",
   "project":true,
   "threePoint":true,
   "useCase":true,
   "functionPoint":true,
   "otherCost":false,
   "userStory":true,
   "scrumTask":true,
   "sprint":false,
   "waterfallTask":true,
   "useCaseActor":false,
   "active":true
}
```

##Create Tag

* `POST /tags` Creates a new tag.

|Response Fields | Description/Format|
|------------ | -------------|
|name | (Required) String|
|project | (Optional) Boolean, Can the tag be used on projects|
|threePoint | (Optional) Boolean, Can the tag be used on three point estimates|
|useCase | (Optional) Boolean, Can the tag be used on use cases|
|functionPoint | (Optional) Boolean, Can the tag be used on function point estimates|
|otherCost | (Optional) Boolean, Can the tag be used on other costs|
|userStory | (Optional) Boolean, Can the tag be used on user stories|
|scrumTask | (Optional) Boolean, Can the tag be used on scrum tasks|
|sprints | (Optional) Boolean, Can the tag be used on scrum sprints|
|waterfallTask | (Optional) Boolean, Can the tag be used on waterfall tasks|
|useCaseActor | (Optional) Boolean, Can the tag be used on use case actors|

###Sample JSON Request
POST https://api.forecast.it/api/v1/tags

```javascript
{
   "name":"Web",
   "project":true,
   "threePoint":true,
   "useCase":true,
   "functionPoint":true,
   "otherCost":false,
   "userStory":true,
   "scrumTask":true,
   "sprint":false,
   "waterfallTask":true,
   "useCaseActor":false,
}
```

##Update Tag

* `PUT /tags/{tagId}` Updates a tag.

|Response Fields | Description/Format|
|------------ | -------------|
|name | String|
|project | Boolean, Can the tag be used on projects|
|threePoint | Boolean, Can the tag be used on three point estimates|
|useCase | Boolean, Can the tag be used on use cases|
|functionPoint | Boolean, Can the tag be used on function point estimates|
|otherCost | Boolean, Can the tag be used on other costs|
|userStory | Boolean, Can the tag be used on user stories|
|scrumTask | Boolean, Can the tag be used on scrum tasks|
|sprints | Boolean, Can the tag be used on scrum sprints|
|waterfallTask | Boolean, Can the tag be used on waterfall tasks|
|useCaseActor | Boolean, Can the tag be used on use case actors|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/tags/1

```javascript
{
   "name":"Different Name",
   "project":false
}
```

##Delete Tag

* `DELETE /tags/{tagId}` Delete a tag.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/tags/1
