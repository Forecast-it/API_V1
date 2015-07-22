#Projects

##Get projects

* `GET /projects` Returns all projects.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the project|
|id | Integer|
|projectIdString | String|
|name | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | Integer|
|businessUnit | Integer|
|customer | Integer|
|projectOwner | Integer|
|projectManager | Integer|
|projectEstimator | Integer|
|parentProject | Integer|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<Integer>|

###Sample JSON Response
```javascript
[
    {  
      "url":"https://api.forecast.it/api/v1/projects/1",
      "id":1,
      "projectIdString":"x001",
      "name":"Example Project 1",
      "projectStatus":"In Progress",
      "projectType":1,
      "businessUnit":2,
      "customer":3,
      "projectOwner":4,
      "projectManager":4,
      "projectEstimator":3,
      "parentProject":1,
      "startDate":"2012-11-19T01:00:00",
      "deliveryDate":"2013-11-19T01:00:00",
      "useCost":"Internal",
      "tags":[  
         33,
         44
      ],
      "excludeFromStatistics":false,
      "useALA":true
   },
   ...
]
```
##Get project

* `GET /projects/{projectId}` Returns more information on one project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the project|
|id | Integer|
|projectIdString | String|
|name | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | JSON (Project Type)|
|businessUnit | JSON (Business Unit)|
|customer | JSON (Customer)|
|projectOwner | JSON (User)|
|projectManager | JSON (User)|
|projectEstimator | JSON (User)|
|parentProject |JSON (Project)|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<JSON (Tag)>|

###Sample JSON Response
```javascript
{  
  "url":"https://api.forecast.it/api/v1/projects/1",
  "id":1,
  "projectIdString":"x001",
  "name":"Example Project 1",
  "projectStatus":"In Progress",
  "projectType":{  
	 "url":"https://api.forecast.it/api/v1/projecttypes/7",
	 "id":7,
	 "name":"Scrum Project Type Example",
	 "description":"This is a Scrum project type.",
	 "developmentModel":"Scrum"
  },
  "businessUnit":{  
	 "url":"https://api.forecast.it/api/v1/businessunits/68",
	 "id":68,
	 "name":"Main Business Unit"
  },
  "customer":{  
	 "url":"https://api.forecast.it/api/v1/customers/7",
	 "id":7,
	 "name":"Customer X",
	 "description":"An example customer",
	 "active":true
  },
  "projectOwner":{
      "url":"https://api.forecast.it/api/v1/users/1",
      "id":1,
      "firstName":"John",
      "lastName":"Smith",
      "initials":"JS",
      "email":"js@domain.com",
      "userName":"js@domain.com",
      "dateCreated":"2012-10-21T15:13:15+02:00",
      "lastUpdated":"2013-05-13T19:32:52+02:00",
      "isAdmin":true,
      "active":true,
      "externalEmployeeId":null
  },
  "projectManager":(See project owner),
  "projectEstimator":(See project owner),
  "parentProject":null,
  "startDate":"2012-11-19T01:00:00",
  "deliveryDate":"2013-11-19T01:00:00",
  "useCost":"Internal",
  "tags":[  
	{
         "url":"https://api.forecast.it/api/v1/tags/1",
         "id":1,
         "name":"Web",
         "active":true
      },...
  ],
  "excludeFromStatistics":false,
  "useALA":true
}
```
##Create project

* `POST /projects` Creates a new project.

|Response Fields | Description/Format|
|------------ | -------------|
|projectIdString | (Optional) String|
|name | (Required) String|
|projectStatus | (Required) String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | (Required) Integer, id of the project type|
|businessUnit | (Required) Integer, id of the business unit|
|customer | (Required) Integer, id of the customer|
|projectOwner | (Required) Integer, id of the user|
|projectManager | (Optional) Integer, id of the user|
|projectEstimator | (Optional) Integer, id of the user|
|parentProject | (Optional) Integer, id of the project|
|startDate | (Optional) Date|
|deliveryDate | (Optional) Date|
|useCost | (Required) String {“Internal”,”External”}|
|excludeFromStatistics | (Required) Boolean|
|useALA | (Required) Boolean|
|tags | (Optional) List<Integer>, list of tag ids|


###Sample JSON Request
POST https://api.forecast.it/api/v1/customers

```javascript
{
    "name":"New Project",
    "projectStatus":"In Progress",
    "projectType": 42,
    "businessUnit": 56,
    "customer": 87,
    "projectOwner": 65,
    "useCost":"Internal",
    "excludeFromStatistics":false,
    "useALA":true,
    "tags":[  
       74,
       76
    ]
}
```

##Update project

* `PUT /projects/{projectId}` Updates a project.

|Response Fields | Description/Format|
|------------ | -------------|
|projectIdString | String|
|name | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | Integer, id of the project type|
|businessUnit | Integer, id of the business unit|
|customer | Integer, id of the customer|
|projectOwner | Integer, id of the user|
|projectManager | Integer, id of the user|
|projectEstimator | Integer, id of the user|
|parentProject | Integer, id of the project|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<Integer>, list of tag ids|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/customers/1

```javascript
{
    "parentProject":2
}
```

##Delete project

* `DETELE /projects/{projectId}` Deletes a project.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1