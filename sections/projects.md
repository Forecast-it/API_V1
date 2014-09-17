#Projects

##Get projects

* `GET /projects` Returns all projects.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the project|
|id | Integer|
|projectIdString | String|
|name | String|
|comment | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | JSON (Project Type)|
|businessUnit | JSON (Business Unit)|
|customer | JSON (Customer)|
|projectOwner | String|
|projectManager | String|
|projectEstimator | String|
|hasParentProject | Boolean|
|parentProject | String|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<String>|

###Sample JSON Response
```json
[
    {  
      "url":"http://api.forecast.it/api/v1/projects/1",
      "id":1,
      "projectIdString":"x001",
      "name":"Example Project 1",
      "comment":"This is an example project",
      "projectStatus":"In Progress",
      "projectType":"Scrum Project Type Example",
      "businessUnit":"Main Business Unit",
      "customer":"An example customer",
      "projectOwner":”John Smith (JS)”,
      "projectManager":”Jane Doe (JD)”,
      "projectEstimator":”Foo Bar (FB)”,
      "hasParentProject":false,
      "parentProject":null,
      "startDate":"2012-11-19T01:00:00",
      "deliveryDate":2013-11-19T01:00:00,
      "useCost":"Internal",
      "tags":[  
         “Web”,
         “Marketing”
      ],
      "excludeFromStatistics":false,
      "useALA":true
   },
   ...
]
```
##Get project

* `GET /projects/{id}` Returns more information on one project.

|Response Fields | Description/Format|
|------------ | -------------|
|url | URL to the project|
|id | Integer|
|projectIdString | String|
|name | String|
|comment | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | JSON (Project Type)|
|businessUnit | JSON (Business Unit)|
|customer | JSON (Customer)|
|projectOwner | JSON (User)|
|projectManager | JSON (User)|
|projectEstimator | JSON (User)|
|hasParentProject | Boolean|
|parentProject |JSON (Project)|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<JSON (Tag)>|

###Sample JSON Response
```json
{  
  "url":"http://api.forecast.it/api/v1/projects/1",
  "id":1,
  "projectIdString":"x001",
  "name":"Example Project 1",
  "projectStatus":"In Progress",
  "projectType":{  
	 "url":"http://api.forecast.it/api/v1/projecttypes/7",
	 "id":7,
	 "name":"Scrum Project Type Example",
	 "description":"This is a Scrum project type.",
	 "developmentModel":"Scrum"
  },
  "businessUnit":{  
	 "url":"http://api.forecast.it/api/v1/businessunits/68",
	 "id":68,
	 "name":"Main Business Unit"
	 ]
  },
  "customer":{  
	 "url":"http://api.forecast.it/api/v1/customers/7",
	 "id":7,
	 "name":"Customer X",
	 "description":"An example customer",
	 "active":true
  },
  "projectOwner":{
      "url":"http://api.forecast.it/api/v1/users/1",
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
  "hasParentProject":false,
  "parentProject":null,
  "startDate":"2012-11-19T01:00:00",
  "deliveryDate":2013-11-19T01:00:00,
  "comment":"This is an example project",
  "useCost":"Internal",
  "tags":[  
	{
         "url":"http://api.forecast.it/api/v1/tags/1",
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
|comment | (Optional) String|
|projectStatus | (Required) String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | (Required) Integer, id of the project type|
|businessUnit | (Required) Integer, id of the business unit|
|customer | (Required) Integer, id of the customer|
|projectOwner | (Required) Integer, id of the user|
|projectManager | (Optional) Integer, id of the user|
|projectEstimator | (Optional) Integer, id of the user|
|hasParentProject | (Optional) Boolean|
|parentProject | (Optional) Integer, id of the project|
|startDate | (Optional) Date|
|deliveryDate | (Optional) Date|
|useCost | (Required) String {“Internal”,”External”}|
|excludeFromStatistics | (Required) Boolean|
|useALA | (Required) Boolean|
|tags | (Optional) List<Integer>, list of tag ids|


###Sample JSON Request
POST https://api.forecast.it/api/v1/customers

```json
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

* `PUT /projects/{id}` Updates a project.

|Response Fields | Description/Format|
|------------ | -------------|
|projectIdString | String|
|name | String|
|comment | String|
|projectStatus | String {“Estimating”, “In progress”, “Completed”, “Halted”, “Cancelled”}|
|projectType | Integer, id of the project type|
|businessUnit | Integer, id of the business unit|
|customer | Integer, id of the customer|
|projectOwner | Integer, id of the user|
|projectManager | Integer, id of the user|
|projectEstimator | Integer, id of the user|
|hasParentProject | Boolean|
|parentProject | Integer, id of the project|
|startDate | Date|
|deliveryDate | Date|
|useCost | String {“Internal”,”External”}|
|excludeFromStatistics | Boolean|
|useALA | Boolean|
|tags | List<Integer>, list of tag ids|

###Sample JSON Request
PUT https://api.forecast.it/api/v1/customers/1

```json
{
    "comment":"Updated Comment",
    "hasParentProject":true,
    "parentProject":2,
}
```

##Delete project

* `DETELE /projects/{id}` Deletes a project.

###Sample JSON Request
DELETE https://api.forecast.it/api/v1/projects/1