#Roles

##Get Roles

* `GET /roles` Returns all roles.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the role|
|id | Integer|
|name | String|
|description | String|
|internalCostPrice | Decimal|
|externalCostPrice | Decimal|

###Sample JSON Response
```json
[
   {
      "url":"https://api.forecast.it/api/v1/roles/1",
      "id":1,
      "name":"Developer",
      "description":"Developer resources",
      "internalCostPrice":110.00,
      "externalCostPrice":200.00
   }, ...
]
```

##Get Role

* `GET /roles/{roleId}` Returns a specific role.

|Response Fields | Description/Format|
|------------ | -------------|
|url | String, Url to the role|
|id | Integer|
|name | String|
|description | String|
|internalCostPrice | Decimal|
|externalCostPrice | Decimal|

###Sample JSON Response
```json
{
   "url":"https://api.forecast.it/api/v1/roles/1",
   "id":1,
   "name":"Developer",
   "description":"Developer resources",
   "internalCostPrice":110.00,
   "externalCostPrice":200.00
}
```